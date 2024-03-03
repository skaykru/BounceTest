FROM node:20-alpine
WORKDIR /app/client
ADD package.json .
RUN npm i
ADD . .
CMD [ "npm","run","start" ]
EXPOSE 4000