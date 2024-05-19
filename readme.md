# Spotify Analysis 
Spotify data analysis - https://www.kaggle.com/datasets/meeraajayakumar/spotify-user-behavior-dataset

## Build Instructions

1. Clone or download the repository containing the Dockerfile.
2. Navigate to the directory containing the Dockerfile in your terminal or command prompt.

```bash
cd path/to/dockerfile_directory
```

3. Build the Docker image by running the following command:
```bash
docker build . -t spotify_analysis
```

## Running the Container

1. Run the Docker container with the following command:
```bash
docker run --rm -it --ipc=host -p 8888:8888 -v .:/home spotify_analysis
```

- `--rm`: This flag removes the container automatically after it exits. This is useful for temporary containers that you don't want to leave behind after they've completed their task.

- `--ipc=host`: This option shares the IPC namespace with the host system. IPC (Inter-Process Communication) namespace isolation is disabled, meaning processes inside the container can communicate with processes outside the container using IPC mechanisms.

- `-p 8888:8888`: This flag maps port 8888 on the host system to port 8888 within the container. It allows traffic on port 8888 of the host to be forwarded to the same port inside the container, enabling access to services running inside the container from the host system.

- `-v .:/home`: This flag mounts the current directory (denoted by `.`) on the host system to the `/home` directory inside the container. This allows files and directories in the current directory to be accessible from within the container.

- `spotify_analysis`: This is the name of the Docker image that the container is based on. Presumably, this image contains the necessary environment and dependencies to perform some analysis related to Spotify.


