# docker-rsvp

# To User docker-compose-param.yml
export webimage=paichayon/rsvp && docker-compose build --build-arg=webimage=$webimage rsvpweb
docker-compose config
docker-compose up -d
