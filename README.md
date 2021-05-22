# lerna-workshop
lerna-workshop
```
yarn config set workspaces-experimental true
```
```
yarn init --private
```
```
yarn add lerna --dev
```
```
yarn lerna init --independent
```
```
mkdir -p packages/{alpha,beta,usage}
```
```
(cd packages/alpha&&yarn init -yp&&echo "module.exports = 'alpha'" > index.js)
(cd packages/beta&&yarn init -yp&&echo "module.exports = 'beta'">index.js)
(cd packages/usage&&yarn init -yp)
```
```
tree -I 'node_modules'
```
```
yarn lerna ls
```

# Adding a “common” dependency to ALL packages
```
yarn add jest  --dev -W
yarn add husky  --dev -W
yarn add prettier  --dev -W
```

# Install `alpha` in all modules except `alpha`
yarn lerna add alpha

# Install `beta` in `usage`
yarn lerna add beta --scope=usage


yarn lerna bootstrap

(cd packages/usage/&&echo "console.log(require('alpha')+' '+require('beta'))">index.js)
