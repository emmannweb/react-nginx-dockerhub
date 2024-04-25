#FROM chainguard/node-lts
FROM  chainguard/node-lts as build

WORKDIR /app

COPY package.json .
COPY package-lock.json .

# Same as npm install
RUN npm ci

COPY . .
RUN npm run build 

FROM chainguard/nginx
COPY --from=build /app/build /usr/share/nginx/html  



