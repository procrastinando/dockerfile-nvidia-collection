# 1. F5-E2-TTS:

## Build the image:
```
docker build -t f5-e2-tts --file dockerfile-f5-e2-tts https://github.com/procrastinando/dockerfile-nvidia-collection.git#main:.
```
### Deploy Option 1: by command:
```
docker run --gpus all -d -p 7861:7860 f5-e2-tts
```
### Deploy Option 2: as stack:
```
services:
  app:
    image: f5-e2-tts
    deploy:
      resources:
        reservations:
          devices:
            - driver: nvidia
              count: all
              capabilities: [gpu]
    ports:
      - "7861:7860"
    restart: unless-stopped
```
## Force update:
```
docker rm -f f5-e2-tts
docker rmi -f f5-e2-tts
docker build --no-cache --pull -t f5-e2-tts --file dockerfile-f5-e2-tts https://github.com/procrastinando/dockerfile-nvidia-collection.git#main:.
```
