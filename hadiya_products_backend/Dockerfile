# Step 1: Use an official Node.js image as a base image
FROM node:16

# Step 2: Set the working directory inside the container
WORKDIR /app

# Step 3: Copy package.json and package-lock.json to the container
COPY package*.json ./

# Step 4: Install dependencies (including PM2 if it's in your package.json)
RUN npm install

# Step 5: Copy the rest of the application code into the container
COPY . .

# Step 6: Install PM2 globally (if not included in package.json)
RUN npm install -g pm2

# Step 7: Expose the port that the app will run on (port 3000)
EXPOSE 3000

# Step 8: Run the backend using PM2 and keep the container running
CMD ["sh", "-c", "pm2 start src/index.js --name hadiya-api --no-daemon && tail -f /dev/null"]
