# packages/server/Dockerfile
FROM node:16
WORKDIR /app
COPY packages/server/package.json packages/server/yarn.lock ./
RUN yarn install
COPY packages/server ./
COPY packages/shared ./shared  
EXPOSE 5000
CMD ["yarn", "start"]
