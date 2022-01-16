#stage:1 build stage
FROM node:14.16.0-alpine3.13 AS build-stage
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
ENV REACT_APP_API_URL=http://af8a1f8f35b414ba492ef235c767c6ec-590077233.ap-south-1.elb.amazonaws.com:3001/api
ENTRYPOINT [ "npm", "start" ]
# RUN npm run build

# #stage:2 production stage
# FROM nginx:1.12-alpine
# COPY --from=build-stage /app/build /usr/share/nginx/html
# # COPY web.conf /etc/nginx/conf.d/default.conf
# EXPOSE 80
# ENTRYPOINT [ "nginx", "-g", "daemon off;" ]