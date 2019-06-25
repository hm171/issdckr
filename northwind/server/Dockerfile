
FROM node:latest

ENV DB_HOST=nwdb DB_PORT=3306 DB_USER=root DB_PASSWORD=changeit
ENV APP_PORT=3000 APP_DIR=/app

WORKDIR ${APP_DIR}}

#copy files to APP_DIR
ADD main.js .
ADD package.json .

#directory musthave a target name
ADD config config
ADD public public
ADD views views

RUN npm install

##run

EXPOSE ${APP_PORT}

HEALTHCHECK --interval=30s --timeout=30s --retries=3 \
  CMD curl -f -s http://localhost:${APP_PORT}/health || exit 1

ENTRYPOINT ["node","main.js"]



#const DB_HOST = process.env.DB_HOST || config.db_host || 'localhost'
#const DB_PORT = parseInt(process.env.DB_PORT) || config.db_port || 3306
#const DB_USER = process.env.DB_USER || config.db_user || 'fred'
#const DB_PASSWORD = process.env.DB_PASSWORD || config.db_password || 'fred'
#const INSTANCE_IP_ADDRESS = process.env.INSTANCE_IP_ADDRESS || 'ip not set'
#const RETRIES = parseInt(process.env.APP_RETRIES) || config.app_retries || 3
#const RETRY_INTERVAL = (parseInt(process.env.APP_RETRY_INTERVAL) || config.app_retry_interval || 15) * 1000
#const EXIT_ON_ERROR = !!process.env.APP_EXIT_ON_ERROR || false;
