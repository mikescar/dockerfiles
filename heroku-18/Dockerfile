FROM heroku/heroku:18

# Install global terminal preferences
#   Put here instead of /root since we will/should be an unprivileged user
ENV PREFERENCES_DIR /usr/local/bin/preferences

WORKDIR /tmp
RUN git clone https://github.com/mikescar/dotfiles.git
RUN mkdir -p $PREFERENCES_DIR
RUN echo "source $PREFERENCES_DIR/.bash_profile" >> /etc/bash.bashrc
RUN cp dotfiles/linux/.bash_profile $PREFERENCES_DIR/
RUN cp dotfiles/bin/colors.sh $PREFERENCES_DIR/
RUN cp dotfiles/bin/aliases.sh $PREFERENCES_DIR/
RUN cp dotfiles/.psqlrc /etc/psqlrc

# Do not source default .bashrc
RUN mv /root/.bashrc /root/.bashrc-default

