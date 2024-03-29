## asd-alipay-sdk 
## 安装

```sh
$ npm install asd-alipay-sdk --save 
```

## 支付宝小程序 SDK 基础说明

#### 快速集成
##### 引入sdk模块并初始化
```js

import AnalysysAgent from "asd-alipay-sdk"

// 引入加密模块(非必须)
import AnalysysEncryption  from 'asd-alipay-sdk/dist/AnalysysAgent_encryption.min.js';
AnalysysAgent.encrypt = AnalysysEncryption;

//初始化
AnalysysAgent.init({
  appkey: '',
  uploadURL: ''
})
```

##### 初始化参数说明 

参数 | 是否必须| 类型 | 默认值 | 说明
--- | :--- | :--- | :--- | :---
appkey | 是 | string | - |  在网站获取的AppKey
uploadURL | 是 | string | - | 自定义上传地址
debugMode | 否 | number | 0 |  0: 关闭调试模式；1 - 开启调试模式，数据不入库；2 - 开启调试模式，数据入库
autoProfile | 否 | boolean | true | 设置是否追踪新用户的首次属性
encryptType | 否 | number | 0 | 设置是否对上传数据加密：0 - 对上传数据不加密(默认)；1 - 对上传数据进行AES 128位ECB加密；2 对上传数据进行AES 128位CBC加密
allowTimeCheck | 否 | boolean | false | 设置是否开启时间校准
maxDiffTimeInterval | 否 | number | 30 | 设置最大时间校准分为：30s(默认) ，当设置的时间差值小于他，将不开启校准。否则将会进行时间校准。假如设置成为负值，将默认为 30s。
autoTrack | 否 | boolean | false | 设置是否开启全埋点，开启全埋点将会上报所有绑定（支持tab、longtab、longpress）事件,并上报$user_click 事件,设置data-content为采集的 $element_content、data-type为采集的 $element_type、data-name为采集的$element_name、id为采集的$element_id。不设置采集不到。不支持系统方法包括生命周期事件的上报，如果要采集tabbar切换，务必在注册Page的时候注册OnTabItemTap方法，否则采集不到。
autoCompleteURL | 否 | boolean | true | 设置是否采集完整URL，true - 采集URL包括参数；false - 采集URL不包括参数
autoPageViewDuration | 否 | boolean | false | 是否采集页面离开事件
sendDataTimeout | 否 | number | 10000 | 上报数据超时时间






