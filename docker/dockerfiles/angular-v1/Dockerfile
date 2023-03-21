# stage 1
FROM node:14.17.3-alpine as build

LABEL maintainer="your.email@example.com"

LABEL environment="{dev,test,pre-prod,prod}"

WORKDIR /app

COPY . .

RUN npm install

RUN npm run build --prod

# stage 2
FROM nginx:alpine

COPY --from=build /app/dist/* /usr/share/nginx/html

EXPOSE 80 
