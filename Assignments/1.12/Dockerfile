#docker build . -t frontend-project && docker run -p 5000:5000 frontend-project

#get oldish node
FROM node:14

#Expose correct port
EXPOSE 5000

#Create workdir
WORKDIR /usr/src/app

#get necessary packages
RUN apt-get update
RUN apt-get -y install curl
RUN npm install -g serve

#Copy files
COPY . .

#After 1.14
ENV REACT_APP_BACKEND_URL=http://localhost:8080

RUN npm install

RUN npm run build

CMD ["serve", "-s", "-l", "5000", "build"]