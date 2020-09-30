# docker-stuff
Stuff I find useful for docker


The docker-phpmyadmin.service file is an example of how I use SystemD to manage my Docker containers. 
If you place the file in /etc/systemd/system/, make any changes to fit your system,
then run "sudo systemctl daemon-reload", you'll have a service that will start and stop phpmyadmin like
any other system service.

So "sudo systemctl enable docker-phpmyadmin" will force docker to start the container at boot time.

The nice thing about managing containers this way is that every time the container starts, it is updated
and uses the most up-to-date version of the image.

NOTE: The container is destroyed every time the service starts/restarts. Be sure your container stores its
data outside of the container itself. (This is how Docker is supposed to work anyway, but if you don't think
of Docker containers as ephemeral, you can pretty easily shoot yourself in the foot!)
