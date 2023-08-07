# Use an official Node.js runtime as the base image
FROM node:18.17.0-alpine3.17

# Copy the entire app directory into the container
COPY . ./app
# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Build the React app
RUN npm run build

RUN adduser \
    --disabled-password \
    --no-create-home \
    react-user
USER react-user
# Specify the command to run when the container starts
CMD ["npm", "start"]
