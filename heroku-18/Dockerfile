FROM heroku/heroku:18

# Install global terminal preferences
#   Put here instead of /root since we will/should be an unprivileged user
ENV PREFERENCES_DIR /usr/local/bin/preferences

WORKDIR /tmp

RUN git clone https://github.com/mikescar/dotfiles.git && \
  mkdir -p $PREFERENCES_DIR && \
  echo "source $PREFERENCES_DIR/.bash_profile" >> /etc/bash.bashrc && \
  cp dotfiles/linux/.bash_profile $PREFERENCES_DIR && \
  cp dotfiles/bin/colors.sh $PREFERENCES_DIR/ && \
  cp dotfiles/bin/aliases.sh $PREFERENCES_DIR/ && \
  cp dotfiles/.psqlrc /etc/psqlrc && \
  # Do not source default bashrc
  mv /root/.bashrc /root/.bashrc-default && \
  rm -rf dotfiles

