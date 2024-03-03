FROM node:20-alpine AS build
WORKDIR /app/server
ADD package.json .
RUN npm i
ADD . .
RUN npm run build 

FROM node:20-alpine 
WORKDIR /app/server
COPY --from=build /app/server/dist ./dist
COPY --from=build /app/server/package.json .
RUN npm i --production
CMD [ "npm", "run", "start:prod" ]
EXPOSE 3000
