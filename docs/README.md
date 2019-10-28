## 阅读对象

商户系统对接区块存证API方式，所涉及的技术架构师，研发工程师，测试工程师，系统运维工程师。

## 接口规则

<table data-hy-role="doctbl">
    <tr>
        <th>规则</th>
        <th>描述</th>   
    </tr>
    <tr>
        <td>传输方式</td>
        <td>为保证交易安全性，采用HTTPS传输</td>
    </tr>
    <tr>
        <td>提交方式</td>
        <td>采用POST方法提交</td>
    </tr>
    <tr>
        <td>字符编码</td>
        <td>统一采用UTF-8字符编码</td>
    </tr>
    <tr>
        <td>签名算法</td>
        <td>MD5，后续会兼容SHA1、SHA256、HMAC等。</td>
    </tr>
    <tr>
        <td>签名要求</td>
        <td>请求和接收数据均需要校验签名，详细方法请参考：MD5签名规则。</td>
    </tr>
    <tr>
        <td>判断逻辑</td>
        <td>先判断协议字段返回，再判断业务返回，最后判断交易状态</td>
    </tr>
</table>

## 签名规则

1. 把字典按Key的字母顺序排序；
- 把所有参数名和参数值串在一起；
- 在第二步生成的参数串后加入KEY;
- 讲第三步得到的参数串进行MD5加密；
- 将MD5串转大写。


例如：
```
APP_KEY：5498C4A5CCC54206A1F0BFVR
```

请求参数（除sign外）：
```javascript
{
    "method":"heechain.sign.add",
    "version":"1.0",
    "app_id":"hyp1710121002500000027081FEFBBA4",
    "mch_uid":"1002501974599",
    "charset":"utf-8",
    "sign_type":"MD5",
    "timestamp":"20191021170832",
    "biz_content={"data_type":"存证","out_trade_no":"73220C42A75348EB98D573E96C352EF4","data_key":"10001","data":"864D4DE15097B3A2D0508A0D5CC724F4","note":"创建合同"}",
    "sign":"e9774123a03acfa7e6c0dfe5e91d12f4"
}
```

根据规则应生成MD5签名串：
```text
app_id=hyp1710121002500000027081FEFBBA4&biz_content={"data_type":"存证","out_trade_no":"73220C42A75348EB98D573E96C352EF4","data_key":"10001","data":"864D4DE15097B3A2D0508A0D5CC724F4","note":"创建合同"}&charset=utf-8&mch_uid=1002501974599&method=heechain.account.register&sign_type=MD5&timestamp=20191021170832&version=1.0&key=5498C4A5CCC54206A1F0BFVR
```

MD5签名转大写后：

```javascript
{
    "sign":"e9774123a03acfa7e6c0dfe5e91d12f4"
}
```
