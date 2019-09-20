FROM balenalib/raspberrypi3-node:10.10

# install required packages, in one command
RUN apt-get update  && \
    apt-get install -y  python-dev

ENV PYTHON /usr/bin/python2

# Install Node-RED Globally
# install node-red
RUN apt-get install -y build-essential && \
    npm install -g --unsafe-perm  node-red && \
    apt-get autoremove -y build-essential

# Install generic extension for Node-RED
RUN npm install -g node-red-dashboard

# Update settings
# All containers will use the same file to store flows. You will not lose your flows when you remove then re-run a container 
RUN sed -i "/\/\/flowFile:/ i\flowFile: 'flows.json'," /usr/local/lib/node_modules/node-red/settings.js && \
    sed -i "/\/\/userDir:/ i\userDir: '\/root\/node-red\/'," /usr/local/lib/node_modules/node-red/settings.js && \
    sed -i "/\/\/nodesDir:/ i\nodesDir: '\/root\/nodes\/'," /usr/local/lib/node_modules/node-red/settings.js

# Create volume for Node-RED storage
VOLUME ["/data"]

# Expose port 1880
EXPOSE 1880

# Setup start command
ENTRYPOINT ["node-red-pi","-v","--max-old-space-size=128"]