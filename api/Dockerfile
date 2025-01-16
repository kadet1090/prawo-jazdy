FROM docker.cui.pg.gda.pl/base/node:18

WORKDIR /docker/www

COPY . .
RUN npm ci
RUN npm run build

COPY --chown=appserver:appserver \
    ./bin/docker-entrypoint.sh.d/*.sh \
    /docker/bin/docker-entrypoint.sh.d

CMD ["npm", "run", "start"]