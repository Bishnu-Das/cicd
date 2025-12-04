FROM node:20-alpine AS build
WORKDIR /app

# Install build deps and compile TypeScript
COPY package.json tsconfig.json ./
COPY src ./src
RUN npm install
RUN npm run build

FROM node:20-alpine
WORKDIR /app
COPY package.json ./
RUN npm install --omit=dev
COPY --from=build /app/dist ./dist
ENV NODE_ENV=production
EXPOSE 3847
CMD ["node", "dist/index.js"]
