# This file is generated by Nx.
#
# Build the docker image with `npx nx docker-build users`.
# Tip: Modify "docker-build" options in project.json to change docker build args.
#
# Run the container with `docker run -p 3000:3000 -t users`.
FROM docker.io/node:lts-alpine

ENV HOST=0.0.0.0
ENV PORT=3300

WORKDIR /app

RUN addgroup --system api-users && \
          adduser --system -G api-users api-users

COPY dist/apps/users api-users
RUN chown -R api-users:api-users .

# You can remove this install step if you build with `--bundle` option.
# The bundled output will include external dependencies.
RUN npm --prefix api-users --omit=dev -f install

CMD [ "node", "api-users" ]
