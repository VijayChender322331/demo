FROM node:16.13.1

WORKDIR /usr/src/app
COPY simple/package.json ./
RUN npm install 
COPY simple/src ./src
EXPOSE 3000
CMD npm start
