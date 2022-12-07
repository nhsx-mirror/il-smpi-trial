FROM node:18-bullseye AS build


WORKDIR /app
COPY . .
RUN npm ci
RUN npm run build

FROM nginx AS serve

COPY --from=build /app/build /usr/share/nginx/html
