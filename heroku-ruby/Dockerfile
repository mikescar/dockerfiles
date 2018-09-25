FROM mikescar/heroku-18

# Install azure cli, is worth it.
# Much cleaner than doing big curl JSON requests
ENV AZURE_DEB_REPO https://packages.microsoft.com/repos/azure-cli/

RUN echo "deb [arch=amd64] $AZURE_DEB_REPO $(lsb_release -cs) main" | \
    tee /etc/apt/sources.list.d/azure-cli.list

RUN curl -L https://packages.microsoft.com/keys/microsoft.asc | apt-key add -

# Only pull the build tools and dev headers we need
#   This saves a lot of disk space over using heroku-18:build image
RUN apt-get update && \
    apt-get --no-install-recommends install -y apt-transport-https azure-cli \
      build-essential libpq-dev nodejs python-pip python-setuptools python-wheel \
      ruby2.5-dev zlib1g-dev && \
    apt-get clean && \
    gem install bundler --no-document && \
    pip install awscli
