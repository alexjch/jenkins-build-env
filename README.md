## Jenkings builder environment

Basic jenkins + builder infrastructure configuration.

# Usage

To start using the environment we need to build the environment, start it, and
finalize the environment configuration.

```
# Build environment

AGENT_PASSWORD=worker AGENT_USER=worker docker-compose build --force-rm

# Run newly create enironment

AGENT_USER=worker AGENT_PASSWORD=worker docker-compose up

# Message after successful Jenkins start

jenkins_1  | *************************************************************
jenkins_1  | *************************************************************
jenkins_1  | *************************************************************
jenkins_1  | 
jenkins_1  | Jenkins initial setup is required. An admin user has been created and a password generated.
jenkins_1  | Please use the following password to proceed to installation:
jenkins_1  | 
jenkins_1  | 3aed00a32f164c52907daeee16c279cc
jenkins_1  | 
jenkins_1  | This may also be found at: /var/jenkins_home/secrets/initialAdminPassword
jenkins_1  | 
jenkins_1  | *************************************************************
jenkins_1  | *************************************************************
jenkins_1  | *************************************************************
```

# Post setup

After the environment is up and running the worker node needs to be added to
Jenkins.

```
Name:                     builder
Remote root directory:    /home/worker
Host:                     builder
Credentials:              worker/worker
Host Key Verification Strategy: No verifying Verification Strategy

```
