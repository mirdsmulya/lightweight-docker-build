# lightweight-docker-build

# A Simple Docker-based Golang Application 

This project sets up a Docker environment for running a Golang application that utilizes the [Gin Web Framework](https://github.com/gin-gonic/gin). It serves a simple message on a GET request at the root endpoint.

This project follows a multi-stage Docker build process. The Docker build is split into two stages: the build stage and the runtime stage. The build stage uses a Golang alpine image to compile the code, and the runtime stage uses the scratch image (a minimal Docker image) to run the compiled binary.

## Getting Started

### Dependencies

* Docker
* Golang 1.20 (in case you wish to run the application outside Docker)

### Installing

1. Clone this repository:
    ```
    git clone https://github.com/<your-username>/<repository-name>.git
    cd <repository-name>
    ```

### Running the application

#### Using Docker

1. Build the Docker image:
    ```
    docker build -t my-golang-app .
    ```

2. Run the Docker container:
    ```
    docker run -p 8080:8080 my-golang-app
    ```

#### Without Docker

1. Download Go dependencies:
    ```
    go mod download
    ```

2. Run the application:
    ```
    go run main.go
    ```

After running the application (either using Docker or directly), navigate to `http://localhost:8080` on your browser or use a tool like curl or Postman. You should see a JSON response with the message: `{"message":"Hello, Docker World!"}`.

## File Structure

* Dockerfile: Contains Docker instructions to build the image for this application.
* main.go: The main Go application file. It creates a default Gin router and sets up a GET endpoint at the root path ("/") that responds with a JSON message.


