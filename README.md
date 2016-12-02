# docker_reverse_proxy
The intention of this container is to provide rever proxy to the multiple other containers/services you might have running in your machine.

Using this proxy you can access them all via default ports 80 and 443

# adding your sites
just add a new file into nginx/sites-enabled and save the file with the `.conf` extension. There is a `template` file there that can be used as a starting point.
All files created there are gitingored

# container
`./up` to start the container
`./down` to stop the container
`./bash` to run bash on the container

# is it working?
http://localhost should show `docker_reverse_proxy worked`

# ssl
This repo is shipped with a fake ssl certificate with a expiration date in 1000 years. I hope somebody submit a PR
to improve it before it expires.

# logs
The folder local folder `logs/nginx` is a mount to `/var/log/nginx` in the container. All logs should be there, as long as your `.conf` file point the logs to /var/log/nginx/yourdomain.com.log 