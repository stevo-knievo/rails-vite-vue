# [Choice] Ruby version:
# https://hub.docker.com/_/microsoft-devcontainers-ruby
ARG VARIANT=3.1

# Debian GNU/Linux 12 (Bookworm)"
FROM mcr.microsoft.com/devcontainers/ruby:${VARIANT}-bookworm

# Install common packages
RUN apt update && export DEBIAN_FRONTEND=noninteractive \
    && apt -y install --no-install-recommends dirmngr ca-certificates software-properties-common apt-transport-https lsb-release curl gnupg2

####### Start install Node 20
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -

RUN apt update && export DEBIAN_FRONTEND=noninteractive \
    && apt -y install --no-install-recommends nodejs
####### End install Node 20

####### Start install postgresql-client-16
# Install postgresql-client-16 here since it doesn't work with devcontainers features ->ghcr.io/devcontainers-contrib/features/apt-packages
RUN curl -fsSl https://www.postgresql.org/media/keys/ACCC4CF8.asc | gpg --dearmor | sudo tee /usr/share/keyrings/postgresql.gpg > /dev/null

RUN echo "deb [arch=amd64,arm64,ppc64el signed-by=/usr/share/keyrings/postgresql.gpg] http://apt.postgresql.org/pub/repos/apt/ $(lsb_release -cs)-pgdg main" | sudo tee /etc/apt/sources.list.d/postgresql.list

RUN apt update && apt -y install postgresql-client-16
####### End install postgresql-client-16

# Install Rails
RUN su vscode -c "gem install rails:6.1.7.7"

# Update to the latest Rubygems version
RUN su vscode -c "gem update --system"

RUN su vscode -c "echo 'alias rstart=\"cd /workspaces/rails-vite-vue && rm -rf tmp/pids/server.pid && bundle install && bundle exec rdbg -n --open --host 0.0.0.0 --port 12345 -c -- bin/rails server -p 3000 -b 0.0.0.0\"' >> ~/.bashrc"
RUN su vscode -c "echo 'alias rrestart=\"cd /workspaces/rails-vite-vue && kill -9 \`cat tmp/pids/server.pid\` && rm -rf tmp/pids/server.pid && bundle install && bundle exec rdbg -n --open --host 0.0.0.0 --port 12345 -c -- bin/rails server -p 3000 -b 0.0.0.0\"' >> ~/.bashrc"
RUN su vscode -c "echo 'alias rkill=\"kill -9 \`cat /workspaces/rails-vite-vue/tmp/pids/server.pid\`\"' >> ~/.bashrc"
RUN su vscode -c "echo 'alias ll=\"ls -lah\"' >> ~/.bashrc"

COPY package* ./
RUN npm install

COPY Gemfile* ./
RUN su vscode -c "bundle install"
