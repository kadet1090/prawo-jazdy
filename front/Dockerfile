FROM docker.cui.pg.gda.pl/base/node:18 AS build

WORKDIR /docker/www

COPY package.json package-lock.json ./
RUN npm ci

COPY . .
RUN npm run build

FROM docker.cui.pg.gda.pl/base/node:18

WORKDIR /docker/www

COPY package.json package-lock.json next.config.ts ./
RUN npm ci --production

COPY --from=build /docker/www/build ./build/
COPY --from=build /docker/www/public ./public/

CMD ["npm", "run", "start"]