FROM node:10 as base

WORKDIR /src
COPY package*.json ./
EXPOSE 5010

FROM base as production
ENV NODE_ENV=production
RUN npm ci
COPY . ./
CMD ["node", "bin/www"]

FROM base as dev
ENV NODE_ENV=development
RUN npm install -g nodemon && npm install
COPY . ./
CMD ["nodemon", "bin/www"]
