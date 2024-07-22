FROM node:16-alpine AS base

WORKDIR /usr/src/app
COPY . .
RUN npm install

FROM base AS build

WORKDIR /usr/src/app
RUN npm run build

FROM node:16-alpine

WORKDIR /usr/src/app
EXPOSE 5000
ENV REACT_APP_BACKEND_URL="http://localhost:8080"
COPY --from=build /usr/src/app/build ./build
RUN npm install -g serve
ENTRYPOINT ["serve", "-s", "-l", "5000", "build"]
