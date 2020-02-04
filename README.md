## Jenkins builder environment

Containerized CI infrastructure to test pipelines locally. To start using
the environment we need to build it first. Assuming that docker-compose is
available in the system start by cloning the *infrastructure code*:

```
# Clone infrastructure definition code
https://github.com/alexjch/jenkins-build-env.git

cd jenkins-build-env

# Build environment
AGENT_USER=<a user> AGENT_PASSWORD=<a password> docker-compose build --force-rm
```

```AGENT_PASSWORD``` and ```AGENT_USER``` are credentials used for the builder
node, make a note of the values used in these fields for later. Once the
environment is done building we start it with:

```
# Run newly created environment
AGENT_USER=<a user> AGENT_PASSWORD=<the password> docker-compose up
```

The source provides an .env file with defaults for ```AGENT_USER``` and 
```AGENT_PASSWORD``` if none is provided.


### References
* https://hub.docker.com/r/jenkins/jenkins
* https://docs.01.org/clearlinux/latest/
* https://jenkins.io/projects/jcasc/
