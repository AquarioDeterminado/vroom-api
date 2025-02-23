FROM nodered/node-red:latest

# Set timezone
ENV TZ=Europe/Amsterdam

# Expose port
EXPOSE 1880

# Set working directory
WORKDIR /data

# Copy existing Node-RED configuration (optional)
COPY settings.js /data/settings.js

# Install dependencies if needed
RUN npm install

CMD ["npm", "start", "--", "--userDir", "/data"]
