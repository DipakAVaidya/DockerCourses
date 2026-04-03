FROM node:22-alpine

RUN addgroup app && adduser -S -G app app 

USER app

WORKDIR /app 

COPY package*.json ./

USER root

RUN chown -R app:app .

USER app

RUN npm install 

COPY . .

ENV CHOKIDAR_USEPOLLING=true
ENV CHOKIDAR_INTERVAL=300

EXPOSE 5173

CMD ["npm", "run", "dev"]
