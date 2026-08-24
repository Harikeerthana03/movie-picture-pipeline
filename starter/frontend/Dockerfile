FROM public.ecr.aws/docker/library/node:18.14.2-alpine3.17

WORKDIR /app

# Copy dependency files
COPY package*.json ./

# Install dependencies
RUN npm ci

# Copy application code
COPY . .

# Build the application
ARG REACT_APP_MOVIE_API_URL
ENV REACT_APP_MOVIE_API_URL=${REACT_APP_MOVIE_API_URL}
RUN npm run build

# Expose port
EXPOSE 3000

# Start application
CMD ["npm", "run", "serve"]