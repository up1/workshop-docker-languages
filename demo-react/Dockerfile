FROM node:17-alpine3.14 as builder
WORKDIR /src
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

FROM nginx:1.21.6-alpine
COPY --from=builder /src/build/ /usr/share/nginx/html/