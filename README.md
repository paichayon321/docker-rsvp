# docker-rsvp

# To User docker-compose-param.yml
git clone https://github.com/paichayon321/docker-rsvp.git
cd docker-rsvp/

## Prepare demo image
docker pull paichayon/rsvp
docker tag paichayon/rsvp paichayon/rsvp:2
export webimage=paichayon/rsvp && docker-compose build --build-arg=webimage=$webimage rsvpweb
docker-compose config
docker-compose up -d

