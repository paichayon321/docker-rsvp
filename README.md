# docker-rsvp

# To User docker-compose-param.yml
git clone https://github.com/paichayon321/docker-rsvp.git

cd docker-rsvp/

## Prepare demo image
docker pull paichayon/rsvp

docker tag paichayon/rsvp paichayon/rsvp:2

# Create and Update image on docker compose

export webimage=paichayon/rsvp && docker-compose -f docker-compose-param.yml build --build-arg=webimage=$webimage rsvpweb

docker-compose -f docker-compose-param.yml config

docker-compose -f docker-compose-param.yml up -d

# Update image on running commpose

export webimage=paichayon/rsvp:2 && docker-compose -f docker-compose-param.yml build --build-arg=webimage=$webimage rsvpweb

docker-compose -f docker-compose-param.yml config

docker-compose -f docker-compose-param.yml up -d

# Custom docker compose network subnet
See sample in docker-compose-customnet.yml

# Use docker compose with existing docker network
First manual Create docker netowrk <br>
docker network create --ip-range=192.168.5.0/24 --subnet=192.168.5.0/24 --gateway=192.168.5.1 fixnet <br>
See sample in docker-compose-fixnet.yml
