FROM node:23.11-alpine3.21

# Install required dependencies
RUN apk add --no-cache \
    ca-certificates \
    bzip2 \
    curl \
    fontconfig

# Install PhantomJS globally
RUN yarn global add phantomjs-prebuilt

# Set working directory
WORKDIR /app

# Copy everything allowed by .dockerignore
COPY . .

# Make test script executable
RUN chmod +x tests.sh

# Run the test script
CMD ["/app/tests.sh"]
