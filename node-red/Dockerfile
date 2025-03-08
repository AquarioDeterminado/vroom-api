FROM nodered/node-red:latest

# Set timezone
ENV TZ=Europe/Amsterdam

# Set working directory
WORKDIR /data

# Ensure package.json exists before running npm install
RUN [ ! -f "/data/package.json" ] || npm install

# Expose Node-RED port
EXPOSE 1880

# Start Node-RED
CMD ["npm", "start", "--", "--userDir", "/data"]
