FROM mikescar/heroku-18

# Only pull the build tools and dev headers we need
#   This saves a lot of disk space over using heroku-18:build image
RUN apt-get update && \
  apt-get install -y build-essential libpq-dev nodejs python-pip ruby2.5-dev zlib1g-dev && \
  pip install awscli

