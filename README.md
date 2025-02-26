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
# 2. FISH SPEECH:

## Build the image:
```
docker build -t fish-speech --file dockerfile-fish-speech https://github.com/procrastinando/dockerfile-nvidia-collection.git#main:.
```
### Deploy Option 1: by command:
```
docker run --gpus all -d -p 7862:7860 fish-speech
```
### Deploy Option 2: as stack:
```
services:
  app:
    image: fish-speech
    deploy:
      resources:
        reservations:
          devices:
            - driver: nvidia
              count: all
              capabilities: [gpu]
    ports:
      - "7862:7860"
    restart: unless-stopped
```
## Force update:
```
docker rm -f fish-speech
docker rmi -f fish-speech
docker build --no-cache --pull -t fish-speech --file dockerfile-fish-speech https://github.com/procrastinando/dockerfile-nvidia-collection.git#main:.
```

# 3. STYLETTS:

## Build the image:
```
docker build -t styletts --file dockerfile-styletts https://github.com/procrastinando/dockerfile-nvidia-collection.git#main:.
```
### Deploy Option 1: by command:
```
docker run --gpus all -d -p 7863:7860 styletts
```
### Deploy Option 2: as stack:
```
services:
  app:
    image: styletts
    deploy:
      resources:
        reservations:
          devices:
            - driver: nvidia
              count: all
              capabilities: [gpu]
    ports:
      - "7863:7860"
    restart: unless-stopped
```
## Force update:
```
docker rm -f styletts-app-1
docker rmi -f styletts
docker build --no-cache --pull -t styletts --file dockerfile-styletts https://github.com/procrastinando/dockerfile-nvidia-collection.git#main:.
```

# 4. TORTOISE-TTS:

## Build the image:
```
docker build -t tortoise --file dockerfile-tortoise https://github.com/procrastinando/dockerfile-nvidia-collection.git#main:.
```
### Deploy Option 1: by command:
```
docker run --gpus all -d -p 7863:7860 tortoise
```
### Deploy Option 2: as stack:
```
services:
  app:
    image: tortoise
    deploy:
      resources:
        reservations:
          devices:
            - driver: nvidia
              count: all
              capabilities: [gpu]
    ports:
      - "7863:7860"
    restart: unless-stopped
```
## Force update:
```
docker rm -f tortoise-app-1
docker rmi -f tortoise
docker build --no-cache --pull -t tortoise --file dockerfile-tortoise https://github.com/procrastinando/dockerfile-nvidia-collection.git#main:.
```