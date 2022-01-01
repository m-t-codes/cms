# cms

- Installed Laravel using curl
- Added following lines to the docker-compose
        phpmyadmin:
            image: phpmyadmin/phpmyadmin:5
            ports:
                - 8080:80
            links:
                - mysql
            environment:
                PMA_HOST: mysql
                PMA_PORT: 3306
            depends_on:
                mysql:
                    condition: service_healthy
            networks:
                - sail
- docker-compose.yml changed the volume line for the mysql to:
    - './mysql:/var/lib/mysql'
- sail up -d
- created a git repo and pushed it to GitHub 