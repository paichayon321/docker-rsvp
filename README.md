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
networks: <br>
  rsvpnet:<br>
    driver: bridge<br>
    ipam:<br>
     config:<br>
       - subnet: 10.5.0.0/16 <br>
         gateway: 10.5.0.1 <br>
