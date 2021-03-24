How to move docker data directory to another location on Ubuntu
===============================================================

* * * * *

[ADMINISTRATION SYSTÈME](https://lesasdushell.fr/posts/category/administration-systeme/) / LUNDI, FÉVRIER 1ST, 2021

[Docker](https://www.docker.com/) is a popular container management platform that can dramatically speed up your development workflow. It is available as a package on major Linux distributions, including Ubuntu.

The standard data directory used for docker is /var/lib/docker, and since this directory will store all your images, volumes, etc. it can become quite large in a relative small amount of time.

If you want to move the docker data directory on another location you can follow the following simple steps.

### 1\. Stop the docker daemon

sudo service docker stop

### 2\. Add a configuration file to tell the docker daemon what is the location of the data directory

Using your preferred text editor add a file named **daemon.json** under the directory **/etc/docker**. The file should have this content:

{
   "graph": "/path/to/your/docker"
}

of course you should customize the location "/path/to/your/docker" with the path you want to use for your new docker data directory.

### 3\. Copy the current data directory to the new one

sudo rsync -aP /var/lib/docker/ /path/to/your/docker

### 4\. Rename the old docker directory

sudo mv /var/lib/docker /var/lib/docker.old

This is just a sanity check to see that everything is ok and docker daemon will effectively use the new location for its data.

### 5\. Restart the docker daemon

sudo service docker start

### 6\. Test

If everything is ok you should see no differences in using your docker containers. When you are sure that the new directory is being used correctly by docker daemon you can delete the old data directory.

sudo rm -rf /var/lib/docker.old

Follow the previous steps to move docker data directory and you won't risk any more to run out of space in your root partition, and you'll happily use your docker containers for many years to come.

### 7\. Extra step: remote debug on your Docker container!

Do you know that you can remote debug your application running on a Docker container? Check out my tutorial on [Remote debugging a Django project in VS Code](https://www.guguweb.com/2020/04/20/remote-debugging-a-django-project-in-vs-code/)! It uses Django as an example, but the Docker related part is general.