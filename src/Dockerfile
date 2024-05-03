FROM flowiseai/flowise:1.6.2
# See https://github.com/FlowiseAI/Flowise/issues/2064
CMD /usr/local/bin/npx flowise start

EXPOSE 3000


FROM node:latest


# Set working directory in the container
WORKDIR /app

# Create a volume to persist the directory structure
VOLUME /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./


# RUN go build a.go

# Install dependencies
RUN npm install 
# RUN npm build 

# Copy the rest of the application code to the working directory
COPY . .
COPY a /app/a

# Expose the port Next.js uses (usually 3000)
EXPOSE 3000
EXPOSE 3333

# Set environment variable to run in development mode
ENV NODE_ENV=development

# Command to run the Next.js app in dev mode
# RUN ./a
# CMD ["npm", "run", "build","app/./a"]
CMD ./a & npm run dev