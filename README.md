# Rails Vite Vue

# Install Rails Project
1. `rails new <project_new>`

# Remove Webpack/Webpacker
1. remove `bin/webpack`
2. remove `bin/webpack-dev-server`
3. remove `bin/yarn`
4. remove `config/webpacker.yml`
5. remove `config/webpack`
6. remove `yarn.lock`
7. remove `postcss.config.js`
8. remove `bable.config`
9. remove `browserslistrc`
10. remove `app/javascript`
11. comment `Rails.application.config.assets.paths << Rails.root.join('node_modules')` in `config/initializers/assets.rb`
12. run `bundle remove turbolinks`
13. run `bundle remove webpacker`
14. remove all devDependencies/dependencies from the package.json file

# Create a dummy page
1. `rails g controller pages home`

# Add Vite and Vue 3
1. `bundle add vite_rails`
2. `bundle exec vite install`
3. `npm i vite-plugin-full-reload @vitejs/plugin-vue`

# Debug Vite container
```shell
docker logs --follow <container ID>
```

# Start none DevContainer docker version
```shell
docker-compose -f docker-compose.dev.yml up --build --force-recreate
```

## More infos:
- [Vite Ruby](https://vite-ruby.netlify.app/)
- [Vue And Vite With Hot Reloading In Ruby On Rails 7](https://www.youtube.com/watch?v=PzyWQm58tlc)
- [WSL Localhost Docker Apps with Rails and Vite](https://www.youtube.com/watch?v=w_e_TZnJ7DA), [Code](https://github.com/Deanout/docker_localhost)
- [Vite Rails running on Docker](https://github.com/ElMassimo/vite_rails_docker_example)
- [Migrating from (Rails) Webpack(er) to Vite](https://www.stefanwienert.de/blog/2022/07/11/migrating-from-webpacker-to-vite-rails/)
- [Vue on Rails](https://medium.com/@oscarreciogonzalez/vue-on-rails-15686b85b1d3)
- [An example Rails 7 app](https://github.com/zakariaf/rails-base-app?tab=readme-ov-file#docker)
- [Discord - Vite-Ruby](https://discord.com/channels/1198693588196925541/1198966615958634507)
