FROM node:23-alpine AS production

ENV NODE_ENV=production

WORKDIR /usr/src/api

COPY package*.json .

RUN npm install

# Install TypeScript globally
RUN npm install -g typescript pm2

COPY . .     
# Copy all files from the current directory which is all the files in the api to the WORKDIR  first . means current directory second . means the WORKDIR

RUN npm run build 
# This command will run the build script in the package.json file

EXPOSE 3000  
# Expose port 3000 to the outside world this is the port that the api will run on

CMD ["sh", "-c" , "npm run start:production"]