FROM node:18.19.1-alpine3.19
EXPOSE 8080
# WORKDIR /opt/server
# ENV MONGO=true
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
WORKDIR /opt/server
# ENV MONGO=true We will pass it from kubernetes as configMap
RUN chown roboshop:roboshop /opt/server
USER roboshop
COPY package.json /opt/server/
RUN npm install
COPY server.js /opt/server/
CMD ["node", "server.js"]