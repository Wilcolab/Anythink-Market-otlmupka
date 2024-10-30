# Simple Express Server

This project sets up a simple Express server that listens on port 8001. The server does not define any endpoints.

## Getting Started

### Prerequisites

- Node.js
- Yarn

### Installation

1. Clone the repository:
   ```
   git clone <repository-url>
   cd simple-express-server
   ```

2. Install dependencies:
   ```
   yarn install
   ```

### Running the Server

To start the server with automatic reloading, use:
```
yarn start
```

The server will listen on [http://localhost:8001](http://localhost:8001).

### Docker

To build and run the Docker image, use the following commands:

1. Build the Docker image:
   ```
   docker build -t simple-express-server .
   ```

2. Run the Docker container:
   ```
   docker run -p 8001:8001 simple-express-server
   ```

The server will be accessible at [http://localhost:8001](http://localhost:8001).