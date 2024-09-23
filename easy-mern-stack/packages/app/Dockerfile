# packages/client/Dockerfile
FROM node:16 AS build
WORKDIR /app
COPY packages/client/package.json packages/client/yarn.lock ./
RUN yarn install
COPY packages/client ./
RUN yarn build

FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
