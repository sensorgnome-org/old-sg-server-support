# Old Sensorgnome Server Support

Docker infrastructure to run the legacy sensorgnome server.

Once running, the SensorgnomeServer process listens on ports 59022,59023, 59024, 59025, 59026, 59027 for connections to/from the various sensorgnomes.

The webserver listens on port 80 and 443 (currently set to 10080 and 10443 for testing).

Hugo has no externally accessible ports, but does internally listen on 443 and 1313 for the live stats page.

## Running

Pre-requisites:

- Docker
- docker-compose
- SSL certificates

If this is a re-install of an existing setup, additionally required are:

- The various SSH keys for the receivers.
- The existing sqlite db `sg_remote.sqlite`.

Steps to get running:

1. Run `docker-compose build` to create the required containers and images.
2. Place ssl certificates in `docker-volumes/nginx/etc/ssl`, the public one in `/public` and the private in `/private`.

If this is a re-install, there are additional stpe:

3. Place the sqlite database in `docker-volumes/sensorgnome-server/database`
4. Place the SSH keys in `docker-volumes/sensorgnome-server/ssh-keys`

And finally:

5. Run `docker-compose up` to start the docker containers and services.

## Logs Locations

- SensorgnomeServer logs are in `docker-volumes/sensorgnome-server/logs`
- Hugo logs are in `docker-volumes/hugo/logs`
- nginx logs are in `docker-volumes/nginx/logs`
