FROM node:latest

ENV APP_ROOT=/app APP_PORT=3000 

# create APP_ROOT and cd in
WORKDIR ${APP_ROOT}

# copy the files and directory into image
ADD main.js .
ADD package.json .
ADD package-lock.json .

ADD public public
ADD views views

# install the dependencies
RUN npm install

# tell what port we are using
EXPOSE ${APP_PORT}

ENTRYPOINT [ "node", "main.js" ]

CMD [ "${APP_PORT}" ]