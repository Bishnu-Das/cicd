FROM node:20-alpine

WORKDIR /app

# Copy only dependency files first
COPY package.* ./

# Install only production dependencies
RUN npm install --omit=dev

# Copy app source code
COPY src ./src

ENV NODE_ENV=production
EXPOSE 5921

CMD ["node", "src/gateway.js"]





# FROM node:20-alpine
# WORKDIR /app
# COPY package.json ./
# RUN npm install --omit=dev
# COPY . .
# ENV NODE_ENV=production
# EXPOSE 5921
# CMD ["node", "src/gateway.js"]
