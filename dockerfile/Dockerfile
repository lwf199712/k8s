FROM node:16.13.0 AS build

RUN mkdir -p /app

WORKDIR /app

COPY . /app

RUN npm install
RUN npm install -g serve
RUN npm run build

#EXPOSE 3000

CMD echo "dashboard service start" && \
	serve -s dist

#####STAGE 2######
FROM docker.io/library/nginx:1-alpine
COPY --from=build /app/dist /usr/share/nginx/html/
EXPOSE 80
ENTRYPOINT ["nginx","-g","daemon off;"]
