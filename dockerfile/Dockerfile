FROM node:16.13.0

RUN mkdir -p /home/www/dashboard
WORKDIR /home/www/dashboard

COPY . /home/www/dashboard

RUN npm install
RUN npm install -g serve
RUN npm run build

EXPOSE 3000

CMD echo "dashboard service start" && \
	serve -s dist
