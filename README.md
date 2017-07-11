# woosungchu

> woosungchu portfolio

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# deploy to AWS S3
npm run build
cd dist
copy : $ aws s3 cp . s3://woosung.ch/ --recursive
move : $ aws s3 mv . s3://woosung.ch/ --recursive
```

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
