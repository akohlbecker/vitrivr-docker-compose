FROM nginx

ARG VERSION=v2.9.0

RUN apt-get update && apt-get install -y curl unzip && apt-get clean && curl -L -o vitrivr-ng.zip https://github.com/vitrivr/vitrivr-ng/releases/download/$VERSION/vitrivr-ng-$VERSION.zip && rm /usr/share/nginx/html/index.html && unzip vitrivr-ng.zip -d /usr/share/nginx/html

EXPOSE 80
