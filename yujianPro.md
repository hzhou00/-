## 项目接触
### 一、问题
> 搭建vue 2.9.3项目中引入.css报错
 解决办法：
1. ```npm install css css-loader --save```
2. 在build文件下的webpack.base.conf.js中加入以下代码
    ```module.exports = {
      module: {
        rules: [
          {
            test: /\.css$/,
            use: ['style-loader', 'css-loader'],
          },
        ],
      },
    };```
    
 > webpack import css文件的环境配置遇到的Module build failed: Unknown word 报错
  - [填坑vue.cli+ElementUI遇到的各种坑](https://www.jianshu.com/p/8419f15f9161)

> [vue项目中使用md5加密](https://blog.csdn.net/skyblacktoday/article/details/80255348)

> Axios请求中的data和params
 - 在post请求中如果遇到一些必要请求参数的，不能放在data请求体里面的，把参数放在params里面
 ```
   this.$axios({
      method: "post",
      headers: { "content-type": "application/json" },  //局部更改
      url: `/kujiale/v2/login`,
      data:{ //请求参数 在请求体的参数会以json格式发送请求
          name : "yujian",                       
      },
      params:{ //必选参数 会以 ? 拼接在api请求后面
          appkey: `${appkeyStr}`,
          appsecret: `${appsecretStr}`,
          timestamp: `${timestampStr}`,
          appuid : `${appuidStr}`,
          sign : `${signStr}`
      }
  })
  .then((res) => {
      console.log(res);
  })
  .catch((err)=>{
      console.log(err);
  })
  ```
  
> postman调试api请求
  - postman脚本
  - appkeyStr、timestampStr、appsecretStr、signStr四个必选参数放在params里面，
  - 请求体发送的参数appuidStr放在Body里面,注意选择成JSON
  ```
  var appkeyStr = "";
  var timestampStr = Math.round(new Date().getTime()); //获取时间戳
  var appsecretStr = "";
  var signStr = appsecretStr + appkeyStr + appuidStr + timestampStr; 
  
  var appuidStr = "yujian";

  postman.setEnvironmentVariable('appuid',appuidStr);
  postman.setEnvironmentVariable('appkey',appkeyStr);
  postman.setEnvironmentVariable('sign',CryptoJS.MD5(signStr)); //MD5加密请求
  postman.setEnvironmentVariable('timestamp',Math.round(new Date().getTime()));
  ```
 
> 鼠标放在结构上的光标形状
  - ```cursor:crosshair; //一只手```
  
  

  
  
  
  

