# YunGouOS-PAY-SDK

![https://yungouos.oss-cn-shanghai.aliyuncs.com/YunGouOS/logo/merchant/logo.png](https://yungouos.oss-cn-shanghai.aliyuncs.com/YunGouOS/logo/merchant/logo.png)


# 关于我们

YunGouOS微信支付官方合作伙伴,YunGouOS-PAY是徐州市云宝网络科技有限公司研发的支付产品。

过去我们只将支付提供给自身系统使用，我们对市面上各种第四方支付深感痛恨 我们深知一些个人用户对支付的渴望。

为此，我们开放了重量级产品，YunGouOS旗下“微信个人支付”正式对外开放。

为更多开发者、个体户、个人创业者、小公司提供正规的个人支付产品支持个人、个体户、企业申请签约，资金由微信结算。

# 用户疑惑

很多用户对官方个人支付持有怀疑等态度，表示理解，过去市场上出现了大量的所谓个人支付 基本采取以下几种方式：

第一种 普通的微信号的收款码。这个不支持信用卡支付、受限于个人账户20万每年的限额、同时官方对这方面不提供接口回调。

有些第三方通过外挂挂机等形式完成 稳定性不高。

第二种 二次清算，某企业与微信签约。与使用者二次清算（ps：其中风险自行衡量）

我们提供的则与官网相差无异，我们是微信支付合作伙伴，拥有直接开户权限，支持个人开户、个体户开户、企业开户。

我们并非使用某种外挂等形式完成支付，与普通企业申请一样，提交资料-》微信审核-》审核通过后微信下发商户号-》根据官网文档完成API对接

个人开户支持接口：扫码支付、JSAPI支付、付款码支付、小程序支付、查询、退款等微信官方接口。单日限额30万。

个体户开户支持接口：扫码支付、JSAPI支付、付款码支付、查询、退款等微信官方接口。可使用微信官方营销产品。无限额。

企业开户支持接口：扫码支付、JSAPI支付、付款码支付、小程序支付、APP支付。可使用所有微信官方营销产品。无限额。

# 流程图

![开户流程](https://yungouos.oss-cn-shanghai.aliyuncs.com/YunGouOS/merchant/images/step.png)

# 如何使用

在官网提交资料，由微信审核，审核通过后下发商户号，对接使用。

# 相关地址

官网地址：[http://merchant.yungouos.com](http://merchant.yungouos.com "http://merchant.yungouos.com")

接口文档：[http://open.pay.yungouos.com](http://open.pay.yungouos.com "http://open.pay.yungouos.com")

SDK文档：[https://apidoc.gitee.com/YunGouOS/YunGouOS-PAY-SDK/](https://apidoc.gitee.com/YunGouOS/YunGouOS-PAY-SDK/ "https://apidoc.gitee.com/YunGouOS/YunGouOS-PAY-SDK/")


# 小程序支付

针对小程序支付，我们在文档中使用大量的示例代码以及开源了一个小程序支付集成的Demo，希望帮助小程序开发者快速接入。

同时我们针对小程序也开发了小程序端的SDK，详情请看小程序内的SDK说明。只需要简单几句代码，即可接入。

小程序支付文档地址：[http://open.pay.yungouos.com/#/api/api/pay/wxpay/minPay](http://open.pay.yungouos.com/#/api/api/pay/wxpay/minPay "http://open.pay.yungouos.com/#/api/api/pay/wxpay/minPay")

小程序SDK地址：[https://gitee.com/YunGouOS/YunGouOS-PAY-SDK/tree/master/YunGouOS-WxApp-SDK](https://gitee.com/YunGouOS/YunGouOS-PAY-SDK/tree/master/YunGouOS-WxApp-SDK "https://gitee.com/YunGouOS/YunGouOS-PAY-SDK/tree/master/YunGouOS-WxApp-SDK")


## 在线体验

![https://yungouos.oss-cn-shanghai.aliyuncs.com/YunGouOS/merchant/mindemo/minapp.jpg](https://yungouos.oss-cn-shanghai.aliyuncs.com/YunGouOS/merchant/mindemo/minapp.jpg)




# 快速开始

方式一：maven添加依赖

  		<dependency>
			<groupId>com.yungouos.pay</groupId>
			<artifactId>YunGouOS-JAVA-SDK</artifactId>
			<version>1.0.1</version>
		</dependency>

方式二：下载jar手动导入

[https://github.com/YunGouOS/YunGouOS-PAY-SDK/tree/master/YunGouOS-JAVA-SDK/build](https://github.com/YunGouOS/YunGouOS-PAY-SDK/tree/master/YunGouOS-JAVA-SDK/build "https://github.com/YunGouOS/YunGouOS-PAY-SDK/tree/master/YunGouOS-JAVA-SDK/build")

# 示例代码


## 微信扫码支付

返回二维码地址或微信支付二维码连接（需自行生成二维码）

    String result = WxPay.nativePay(System.currentTimeMillis() + "", "0.01", "1529637931", "测试", null, null, null, null, "6BA371F4CFAB4465AA04DAEADBAC4161");



## 微信公众号支付

返回 返回JSSDK需要的支付jspackage

	String jspackage = WxPay.jsapi(System.currentTimeMillis() + "", "0.01", "1529637931", "测试", "o-_-itxeWVTRnl-iGT_JJ-t3kpxU", null, null, null, "6BA371F4CFAB4465AA04DAEADBAC4161");


没错就是这么简单，就可以快速的接入微信官方支付。

# 其他接口

## 订单查询接口
	WxPayOrder wxPayOrder =WxPay.getOrderInfoByOutTradeNo("1556267522899", "1529637931", "6BA371F4CFAB4465AA04DAEADBAC4161");

返回结果说明：[http://open.pay.yungouos.com/#/api/api/pay/wxpay/getWxPayOrderInfo](http://open.pay.yungouos.com/#/api/api/pay/wxpay/getWxPayOrderInfo "http://open.pay.yungouos.com/#/api/api/pay/wxpay/getWxPayOrderInfo")


## 发起退款接口

	RefundOrder refundOrder = WxPay.orderRefund("1556267522899", "1529637931", "0.1", "6BA371F4CFAB4465AA04DAEADBAC4161");

返回结果说明：[http://open.pay.yungouos.com/#/api/api/pay/wxpay/refundOrder](http://open.pay.yungouos.com/#/api/api/pay/wxpay/refundOrder "http://open.pay.yungouos.com/#/api/api/pay/wxpay/refundOrder")

## 查询微信退款结果接口

	RefundSearch refundSearch = WxPay.getRefundResult("R17200911248111", mchId, key);

返回结果说明：[http://open.pay.yungouos.com/#/api/api/pay/wxpay/getRefundResult](http://open.pay.yungouos.com/#/api/api/pay/wxpay/getRefundResult "http://open.pay.yungouos.com/#/api/api/pay/wxpay/getRefundResult")

# 方法说明

## 微信扫码支付

    WxPay.nativePay(订单号,支付金额,微信支付商户号,商品描述,返回类型，附加数据，异步回调地址,同步回调地址,商户密钥)

## 微信公众号支付

	 WxPay.jsapi(订单号,支付金额,微信支付商户号,商品描述,用户openid，附加数据，异步回调地址,同步回调地址,商户密钥)

## 订单查询

	WxPay.getOrderInfoByOutTradeNo(订单号, 微信支付商户号, 商户密钥);

## 发起退款

	WxPay.orderRefund(订单号, 微信支付商户号, 退款金额, 商户密钥);
	
## 查询微信支付退款结果
	
	WxPay.getRefundResult(退款单号（发起退款接口返回）,微信支付商户号, 商户密钥);
	
	
## 签名工具
	 WxPaySignUtil.createSign([类型Map]签名参数,商户密钥)

	
	