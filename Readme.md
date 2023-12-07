# Docker Compose

## How to handle git submodules

### Cloning
1. `git clone git@github.com:xmravec3/DockerCompose.git`
2. `cd DockerCompose` 
3. `git submodule update --init --recursive`
4. `git submodule update --recursive --remote`

### Updating submodules
1. `cd DockerCompose`
2. `git submodule update --recursive --remote`

## Docker

### Volumes

> Warning: Keep in ming that your local directories, used in volumes, must have enough permissions (755 at least)

- climber-videos
  - `docker volume create climber-videos --opt type=none --opt device=<absolute_path_to_videos_directory> --opt o=bind`
- climber-api-source
  - `docker volume create climber-api-source --opt type=none --opt device=/path/to/DockerCompose/climberAPI/src --opt o=bind`

## Environments

### DEV

- Build
  - `docker compose -f docker-compose.dev.yml build`
- Up
  - `docker compose -f docker-compose.dev.yml up -d`
- Down
  - `docker compose -f docker-compose.dev.yml down`

### PROD

- Build
  - `docker compose build`
- Up
  - `docker compose up`
- Down
  - `docker compose down`