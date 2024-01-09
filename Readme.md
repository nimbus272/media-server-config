 **** This configuration is heavily based on https://github.com/navilg/media-stack and configured for my own personal use ****
1. create docker network "mynetwork"
   
2. ensure the file structure shown in the volume mounts for docker-compose.yml exists
    2a. It is important to set up the proper file structure and hardlink your downloads so as not to take up double space
        there are good guides out there to learn how to do this properly

3. After cloning the repository run both docker compose up commands from docker-commands.txt.
    3a. Ensure Jellyfin is configured with "/jellyfin" as it's path
    3b. ensure you provide your nordvpn credentials where marked in docker-compose.yml

4. update nginx.conf with correct domain and subdomain names where marked

5. docker cp nginx.conf nginx:/etc/nginx/conf.d/default.conf

6. docker exec -it nginx /bin/sh

7. apk add certbot certbot-nginx

8. (you may need to navigate to /etc/nginx/conf.d/) certbot --nginx

9. generate certs for all sites and follow the instructions for auto update in the command output

10. nginx -s reload

11. exit container

12. restart all containers


