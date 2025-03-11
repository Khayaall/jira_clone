FROM node:23-alpine AS production

ENV NODE_ENV=production

WORKDIR /usr/src/api

COPY package.json .
COPY package-lock.json .

RUN npm install

# Install TypeScript globally
RUN npm install -g typescript

COPY . .     
# Copy all files from the current directory which is all the files in the api to the WORKDIR  first . means current directory second . means the WORKDIR

RUN npm run build 
# This command will run the build script in the package.json file

CMD ["sh", "-c" , "npm run start:production"]