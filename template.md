```
version: '3'
services:
  diyhue:
    container_name: diyhue
    image: diyhue/core:beta
    volumes:
      - /opt/hue-emulator/config:/opt/hue-emulator/config
    restart: always
    network_mode: host
    privileged: true
    environment:
      - MAC=dc:a6:32:ea:0d:3f
      - TZ=Europe/Vienna
```