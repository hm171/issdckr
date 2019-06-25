#DOCKER BUILD

FROM node:latest

#define environment variables
ENV APP_PORT=5000 APP_DIR=/fortune

#create workdir and CD
WORKDIR ${APP_DIR}


#copy files to APP_DIR
ADD main.js .
ADD package.json .

#directory musthave a target name
ADD public public
ADD views views


#install libraries from package.json
RUN npm install

#DOCKER RUN

EXPOSE ${APP_PORT}

HEALTHCHECK --interval=60s --timeout=5s --start-period=5s --retries=3 \
  CMD curl -f -s http://localhost:${APP_PORT}/health || exit 1

#how should the image be executed
ENTRYPOINT ["node","main.js"]


#CMD ["3000"]








