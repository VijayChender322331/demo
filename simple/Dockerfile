FROM node:16.13.1 as builder

WORKDIR /usr/src/app
COPY simple/package.json ./
RUN npm run build --prod --output-path=/dist
COPY simple/src ./src

FROM nginx:alpine
EXPOSE 3000
EXPOSE 80
RUN rm -rf /usr/share/nginx/html/*
COPY --from=builder /dist /usr/share/nginx/html
ENTRYPOINT ["nginx", "-g", "daemon off;"]
