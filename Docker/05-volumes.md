# Docker Volumes

- Volumes are used to persist data outside the container filesystem.
- Create a volume with `docker volume create <name>`.
- Mount a volume with `-v <volume>:/path/in/container`.
- Useful for databases and app data.
