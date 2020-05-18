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
        <td>MD5</td>
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

1. 把参数按Key的ASCII顺序由小到大进行排序,并以key=value&方式进行拼接；
- 在步骤一生成的参数串后加入MD5签名KEY,并进行MD5摘要;
- 将MD5摘要后的串转大写。


例如：

根据规则应生成MD5签名串：
```text
app_id=hyp17041910025000000101470B1F3AC&biz_content={"data_key":"test_2020515004","data_content":"testerewr345sdfsdfdgfgfgfffe","notify_url":"http://localhost/TestMergepay/Api/RecNotifyUrl.aspx"}&charset=utf-8&mch_uid=1002501974599&method=heechain.deposit.add&sign_type=MD5&timestamp=20200515092008&version=1.0&key=099E0DB65F1F4EAFA0EBA529
```

MD5签名转大写后：

```javascript
"sign":"1CF6638552C314A51D4A520C3453B6D9"
```

请求参数:
```javascript
{
    "method":"heechain.deposit.add",
    "version":"1.0",
    "app_id":"hyp17041910025000000101470B1F3AC",
    "mch_uid":"1002501974599",
    "charset":"utf-8",
    "sign_type":"MD5",
    "timestamp":"20200515092008",
    "biz_content"="{\"data_key\":\"test_2020515004\",\"data_content\":\"e9774123a03acfa7e6c0dfe5e91d12f4\",\"notify_url\":\"http://localhost/TestMergepay/Api/RecNotifyUrl.aspx\"}",
    "sign":"1CF6638552C314A51D4A520C3453B6D9"
}
```
