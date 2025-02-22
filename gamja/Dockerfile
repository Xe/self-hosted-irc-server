FROM node:alpine AS build
RUN apk -U add git && git clone https://codeberg.org/emersion/gamja /app
WORKDIR /app
RUN npm install --include=dev \
  && npm run build

FROM caddy
COPY --from=build /app/dist /usr/share/caddy