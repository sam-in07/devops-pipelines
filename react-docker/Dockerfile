# Set the base image to create the image for the React app
FROM node:20-alpine

# Create a non-root system user and group to run the application securely
# -S creates a system user, and -G adds the user to a group
# Running as non-root prevents vulnerabilities from potentially granting host access
RUN addgroup app && adduser -S -G app app

# Set the active user context to the newly created non-root user
USER app

# Set the working directory inside the container to /app
WORKDIR /app

# Copy package configuration files first to leverage Docker's caching mechanism
# This ensures dependencies are only re-installed if these files change
COPY package*.json ./

# Switch back temporarily to the root user to adjust file ownership permissions
USER root

# Change ownership of the /app directory and its contents to the app user/group
# This avoids EACCES permission denied errors when the non-root user attempts access
RUN chown -R app:app .

# Switch the user context back to the non-root app user
USER app

# Install the application dependencies inside the container
RUN npm install

# Copy the rest of the application source code into the working directory
COPY . .

# Expose port 5173 to inform Docker that the container listens on this port at runtime
EXPOSE 5173

# Define the default command to start and run the development application
CMD npm run dev