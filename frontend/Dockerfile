# syntax=docker/dockerfile:1

ARG NODE_VERSION=23

FROM node:${NODE_VERSION}-alpine

WORKDIR /frontend

COPY package*.json .

RUN --mount=type=bind,source=package.json,target=package.json \
    --mount=type=bind,source=package-lock.json,target=package-lock.json \
    --mount=type=cache,target=/root/.npm \
    npm ci --omit=dev

COPY . .

EXPOSE 5173

CMD ["npm","run","dev","--","--host","--port","5173"]
