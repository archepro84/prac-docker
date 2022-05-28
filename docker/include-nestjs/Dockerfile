FROM node:16
LABEL version='1.0.0'

USER root

SHELL [ "/bin/bash", "-l", "-c" ]

# Create and Move work directory
# WORKDIR /app

# Create /app directory
RUN mkdir -p /app

# Copy server/express project
COPY . /app

# Move work directory
WORKDIR /app/nestjs

# Install express project node packages
RUN npm install

# Nest js Build To dist directory
RUN npx nest build

# Docker start script
CMD npm run start:prod