FROM node:14-alpine
# note we can use node:alpine, but changed this to make the Dockerfile and Dockerfile.prod more similar.

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 3000

CMD [ "npm", "start" ]