# docker-jenkinsci
Docker-compose file for jenkinsci using "letsencrypt-nginx-proxy" to serve it (on port 80) at a subdomain of your choice

# How to use?

Clone this repo

```
git clone git@github.com:asimzeeshan/docker-jenkinsci.git
cd docker-jenkinsci
cp .env.example .env
```

**Change the details in `.env` especially making sure the hostname you specify is a valid domain name with a valid DNS entry. Also make sure to change `webproxy` to your network created in [letsencrypt-nginx-proxy-companion](https://github.com/evertramos/docker-compose-letsencrypt-nginx-proxy-companion)**


```
docker-compose up -d
```

To view the password, either enter the container to view this file `/var/jenkins_home/secrets/initialAdminPassword` OR do `docker-compose logs -f` and you'll see something like this


```
jenkinsci    | *************************************************************
jenkinsci    | *************************************************************
jenkinsci    | *************************************************************
jenkinsci    | 
jenkinsci    | Jenkins initial setup is required. An admin user has been created and a password generated.
jenkinsci    | Please use the following password to proceed to installation:
jenkinsci    | 
jenkinsci    | 3c891302e27547ca97714105f688e511
jenkinsci    | 
jenkinsci    | This may also be found at: /var/jenkins_home/secrets/initialAdminPassword
jenkinsci    | 
jenkinsci    | *************************************************************
jenkinsci    | *************************************************************
jenkinsci    | *************************************************************
```

Access your new docker container at the URL you specified in `.env` file (make sure you have the DNS entry already added). 

- ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) **Note:** A host entry is not the same as DNS entry

## Pre-requisities

- docker & docker-compose already installed on the system
- git package already installed
- [letsencrypt-nginx-proxy-companion](https://github.com/evertramos/docker-compose-letsencrypt-nginx-proxy-companion)
