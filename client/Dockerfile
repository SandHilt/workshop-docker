FROM node:16-slim

# Environment of npm log
ENV NPM_CONFIG_LOGLEVEL error

# Create user and add to user group
RUN useradd --user-group --create-home --shell /bin/false app

# Environment of home directory
ENV HOME=/home/app

# Create the app directory
RUN mkdir -p ${HOME}/client

# Copy dependencies
COPY package*.json $HOME/client/

# Permission fix for the app folder
RUN chown -R app:app $HOME/*

USER root
WORKDIR ${HOME}/client
RUN npm install

CMD [ "npm", "run", "start" ]