# TeemIP Docker Setup

This repo contains a working TeemIP setup using docker-compose.  
Using a neat volume trick to share data between nginx and php-fpm.

Required PHP extensions:  
(Will be installed in container automatically)
- gd
- ldap
- mysqli
- soap
- zip

To get startet:
1. Clone the repo
2. Run `docker compose build`
3. Run `docker compose up -d`
4. Navigate to `http://<ip of install server>` and follow setup wizard
   1. Database IP is teemip-db
   2. Database User is teemip
   3. Database PW is teemip
   4. Use existing teemip DB
5. Maybe put behind reverse proxy for SSL support

Gotchas:
If your rename the databsae container or the teemip container the setup breaks.  
Renaming of the teemip container is supported and can be changed by setting `TEEMIP_CONTAINER_NAME` variable on nginx container.  
I don't know how the database connection URL is changed in TeemIP. Good luck.

Since I didn't like TeemIP in the end this repo is not going to be maintained.
