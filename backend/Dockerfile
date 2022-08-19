FROM node:14-alpine

WORKDIR /app

COPY package.json .

RUN npm install
RUN mkdir -p /app/logs \
 && chown -R node:node /app/logs \
 && chmod 755 /app/logs

COPY . .

ARG DEFAULT_PORT=80

ENV PORT ${DEFAULT_PORT}
ENV MONGODB_USERNAME root
ENV MONGODB_PASSWORD password

EXPOSE $PORT

CMD ["npm", "start" ]