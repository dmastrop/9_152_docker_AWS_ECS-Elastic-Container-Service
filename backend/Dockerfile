FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

ENV MONGODB_USERNAME=root
ENV MONGODB_PASSWORD=secret
# will override these in AWS ECS

ENV MONGODB_URL=mongodb
# need to add MONGODB_URL here as well. Added to backend.env already. This env var is used in the app.js
# the vaule will be set to localhost for deployment to AWS ECS. For development it is mongodb.
# these (above) are default values that are overridden at runtime via docker run or docker-compose in development
# in AWS ECS override with Task definition of container.

ENV MONGODB_NAME=goals-dev
# this is added for atlas mongodb configuration so that name can be used for development vs. production.
# default will be goals-dev and production will overwrite this with goals.

CMD ["npm", "start"]
# need to override this command on the ECS Task container definition with node app.js.  We do not need npm start (nodeman app.js) for deployment, only for development.