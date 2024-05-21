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
12. run `bundle remove tubrolinks`
13. run `bundle remove webpacker`
14. remove all devDependencies/dependencies from the package.json file

# Create a dummy page
1. `rails g controller pages home`

# Add Vite and Vue 2
1. `bundle add vite_rails`
2. `bundle exec vite install`
3. `npm i vite-plugin-full-reload @vitejs/plugin-vue2 vue@2.7.16`
