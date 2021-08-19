FROM node:12-alpine

WORKDIR /app/frontend

COPY package.json yarn.lock ./

RUN yarn
RUN yarn global add @quasar/cli

# git and bash needed for running linters
RUN set -x \
  && apk add --no-cache bash git \
  && mkdir -p .git/hooks \
  && yarn install

EXPOSE 8080

COPY babel.config.js jest.config.js jsconfig.json quasar.conf.js quasar.extensions.json quasar.testing.json .eslint* .postcssrc.js .quasar .babelrc .editorconfig ./
COPY public public
COPY src src

ENTRYPOINT ["quasar"]
CMD ["dev"]

