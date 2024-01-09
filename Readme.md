 **** This configuration is heavily based on https://github.com/navilg/media-stack and configured for my own personal use ****

1. ensure the file structure shown in the volume mounts for docker-compose.yml exists
    1a. It is important to set up the proper file structure and hardlink your downloads so as not to take up double space
        there are good guides out there to learn how to do this properly

2. After cloning the repository run both docker compose up commands from docker-commands.txt.
    2a. Ensure Jellyfin is configured with "/jellyfin" as it's path
    2b. ensure you provide your nordvpn credentials where marked in docker-compose.yml

3. update nginx.conf with correct domain and subdomain names where marked

4. docker cp nginx.conf nginx:/etc/nginx/conf.d/default.conf

5. docker exec -it nginx /bin/sh

6. apk add certbot certbot-nginx

7. (you may need to navigate to /etc/nginx/conf.d/) certbot --nginx

8. generate certs for all sites and follow the instructions for auto update in the command output

9. nginx -s reload

10. exit container

11. restart all containers


