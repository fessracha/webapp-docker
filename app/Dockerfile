# pull the Node.js Docker image
FROM node:alpine

# create the directory inside the container
WORKDIR /usr/src/app

# copy the package.json files from local machine to the workdir in container
COPY ./package*.json ./

# run npm install in our local machine
RUN npm install && npm run build

# copy the generated modules and all other files to the container
COPY . .

FROM nginx:1.18-alpine

COPY nginx.conf /etc/nginx/conf.d/default.conf
COPY dist /usr/share/nginx/html


