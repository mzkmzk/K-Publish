# K-Qiniu

After the packaged webpack file upload to seven Qiniu

# Install

npm:

```
  npm install  --save k-qiniu
```


# Use

> 1. Set webpack 

```
  var QiniuPlugin = reqiure('k-qiniu');
    

  // Webpack 配置文件
  module.exports = {
    plugins: [
      new QiniuPlugin({

          // 七牛云的两对密匙 Access Key & Secret Key
          accessKey: 'accessKey',
        
          secretKey: 'secretKey',
        
          // 七牛云存储空间名称
          bucket: 'test',
          
          // 上传到七牛后保存的文件名
          // name is package.json name
          //version is package.json version
          //asset is file name
          path: 'static/[name]/[version]/[asset]'

        })
      // ...
    ]
    // ...
  };

```

> 2. Set publicPath

publish 

```javascript
var package = require('./package')
const publicPath = 'http://publish.404mzk.com/static/' + package.name + "/" + package.version +"/"

module.exports = {
  ...
   output: {
    
    publicPath: publicPath,

  },
}
```


