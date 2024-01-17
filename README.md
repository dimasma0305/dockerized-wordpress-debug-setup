# Dockerized Wordpress Debug Setup
This project is a Dockerized WordPress development environment with two configurations, one using Nginx and the other using Apache. It includes Xdebug for debugging purposes and provides flexibility for developers to choose their preferred web server.

## Usage

1. Choose either the Nginx or Apache setup by selecting the corresponding Docker Compose file.

2. Start the chosen environment by running:

    ```sh
    # For Nginx
    docker-compose -f docker-compose.nginx.yaml up

    # or for Apache
    docker-compose -f docker-compose.apache.yaml up
    ```

3. After starting the environment, download WordPress using the following commands:

    ```sh
    # Replace <your_preferred_server> with either nginx or apache
    docker-compose -f docker-compose.<your_preferred_server>.yaml exec wordpress wp core download

    # To download a specific WordPress version, replace <wp_version_to_download>
    docker-compose -f docker-compose.<your_preferred_server>.yaml exec wordpress wp core download --version=<wp_version_to_download>
    ```

4. For your convenience, you can also activate or deactivate plugins using these commands:

    ```sh
    # Replace <your_plugin> with the desired plugin name
    docker-compose -f docker-compose.nginx.yaml exec wordpress wp plugin deactivate <your_plugin>

    docker-compose -f docker-compose.nginx.yaml exec wordpress wp plugin activate <your_plugin>
    ```

For more information about the usage of wp-cli, you can refer to the [official documentation](https://wp-cli.org/).
