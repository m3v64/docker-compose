# Welcome

![animation](./ayaya.gif)

## Intro

Welcome to my github repo, here i save my docker compose setup from across my multiple devices, each containing various services, i hope you find what you need!

## Structure

The parent compose file includes the app compose files. app-specific env files are only used where they are actually used. If an app does not have its own `.env`, it just inherits from the parent `.env`.

```txt
.
├── README.md
├── ayaya.gif
└── <device>
    ├── .env
    ├── .env.example
    ├── docker-compose.yml
    └── <app>
        ├── .env
        ├── .env.example
        └── docker-compose.<app>.yml
```

## Conventions

### Container definition

I’m trying to keep the compose files consistent and easy to maintain, so the container definition usually follows this order when the field is actually used:

- image
- container_name
- restart
- cpus
- tty
- stdin_open
- pid
- user
- privileged
- cap_add
- depends_on
- healthcheck
- command
- links
- environment
- devices
- volumes
- ports
- networks

### Environment variables

For environment variables, variables live in the parent `.env` when they’re used across multiple containers, and app-specific values stay in that app’s own `.env`.

Currently that’s things like `TZ`, `PUID`, `PGID`, `DATA_ROOT`, `MEDIA_ROOT`, `COMPOSE_ROOT`, and `DOMAIN`.
