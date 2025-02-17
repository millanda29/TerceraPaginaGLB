
# 🧩 PHP Word Search Puzzle 🐘

This project is a web-based word search puzzle, developed in PHP, that lets users find specific words in a randomly generated grid of letters. The application includes an interactive interface to select letters and displays a victory message when all words are found. It's designed to run in a Docker container, using Apache as the web server.

![Alt text][id]

## 📂 File Structure

```
TerceraPagina/
├── index.php               # Main file of the word search puzzle
├── img/
│   └── fondo.jpg           # Background image
├── Dockerfile              # Docker file to configure the environment
└── README.md               # Project documentation
```

## 🔧 Prerequisites

- 🐋 **Docker** and Docker Compose installed on your machine.
- 🌐 Internet access to download the required Docker images.

## 🚀 Setup and Installation

### Step 1: Clone the Repository

Clone this repository to your local machine:

```bash
git clone https://github.com/kmamaguana/TerceraPagina
cd TerceraPagina
```

### Step 2: Prepare the Docker Environment

Make sure the `Dockerfile` is properly configured. This file defines a Docker image that uses PHP and Apache to run the application.

#### 🐳 Dockerfile

```dockerfile

FROM php:8.1-apache


WORKDIR /var/www/html


COPY . /var/www/html

RUN chown -R www-data:www-data /var/www/html

RUN a2enmod rewrite

EXPOSE 80

CMD ["apache2-foreground"]
```

### Step 3: 🛠️ Build the Docker Image

Run the following command to build the Docker image:

```bash
docker build -t TerceraPagina.
```

### Step 4: 🏃 Run the Container

Once the image is built, run the container with this command:

```bash
docker run -d -p 8080:80 TerceraPagina
```

This will start the application, which will be accessible at `http://localhost:8080`.

> **Note**: If you're using `docker-compose`, just run `docker-compose up -d` to build and start all configured services.

## 🎮 Usage

1. Access the application in your web browser at `http://localhost:8080`.
2. Interact with the word search by clicking letters to select them.
3. When you find all the words, a message **"You've found all the words!"** will appear 🎉

## 🛠️ Customization

To customize the application, you can modify the `index.php` file to:

- ✏️ Change the words to be found in the word search.
- 🎲 Adjust the size of the grid.
- 🎨 Modify the CSS styles for a custom design.

## 🚢 Deployment in Production

To deploy this application in production:

1. 📤 Upload the Docker image to Docker Hub (optional):
   ```bash
   docker tag word-search kmamaguana/TerceraPagina
   docker push kmamaguana/TerceraPagina
   ```

2. Deploy to your production server using orchestration tools like Kubernetes or a cloud hosting service.

## 🏅 Credits

This project was developed as an implementation example in PHP and Docker.

[id]: https://octodex.github.com/images/dojocat.jpg "The Dojocat"
