# 1. F5-TTS: A Fairytaler that Fakes Fluent and Faithful Speech with Flow Matching

## Build the image:
```
docker build -t f5-tts --file dockerfile-f5-tts https://github.com/procrastinando/F5-TTS-dockerfile.git#main:.
```
### Deploy Option 1: by command:
```
docker run --gpus all -d -p 7861:7860 f5-tts
```
### Deploy Option 2: as stack:
```
services:
  app:
    image: f5-tts
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
docker rm -f f5-tts
docker rmi -f f5-tts
docker build --no-cache --pull -t f5-tts https://github.com/procrastinando/F5-TTS-dockerfile.git#main:.
```
