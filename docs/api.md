## 存证


> 请求URL:`https://api.heemoney.com/heechain/v1/depositadd`

> 请求方式:`POST`   

> method：`heechain.deposit.add`

> 数据格式：`json串`

- 公共参数


<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
	<th>是否必填</th>
	<th>最大长度</th>
	<th>描述</th>
	<th>示例值</th>
</tr>
<tr>
    <td>version</td>
    <td>String</td>
	<td>否</td>
	<td>10</td>
	<td>版本号，默认1.0</td>
	<td>V1.0</td>
</tr>
<tr>
    <td>app_id</td>
    <td>String</td>
	<td>是</td>
	<td>32</td>
	<td>应用ID，商户的应用id</td>
	<td>Ap22512545</td>
</tr>
<tr>
    <td>mch_uid</td>
    <td>String</td>
	<td>是</td>
	<td>32</td>
	<td>商户统一编号</td>
	<td>276952</td>
</tr>
<tr>
    <td>method</td>
    <td>String</td>
	<td>是</td>
	<td>128</td>
	<td>业务名称</td>
	<td>heechain.deposit.add</td>
</tr>
<tr>
    <td>charset</td>
    <td>String</td>
    <td>否</td>
    <td>10</td>
    <td>编码格式默认为UTF-8</td>
    <td>UTF-8,GBK,GB2312</td>
</tr>
<tr>
    <td>sign_type</td>
    <td>String</td>
	<td>是</td>
	<td>10</td>
	<td>商户生成签名字符串所使用的签名算法类型</td>
	<td>md5</td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
	<td>是</td>
	<td>256</td>
	<td>商户请求参数的签名串</td>
	<td>详见示例</td>
</tr>
<tr>
    <td>timestamp</td>
    <td>String</td>
	<td>是</td>
	<td>19</td>
	<td>发送请求的时间</td>
	<td>Json格式</td>
</tr>
<tr>
    <td>biz_content</td>
    <td>String</td>
	<td>是</td>
	<td>不限</td>
	<td>请求参数集合，Json格式，长度不限，具体参数见如下业务参数</td>
	<td>Json格式</td>
</tr>
</table>

- 业务参数

<table data-hy-role="doctbl"> 
    <th>参数</th>
    <th>类型</th>
	<th>是否必填</th>
	<th>最大长度</th>
	<th>描述</th>
	<th>示例值</th>
</tr>
<tr>
    <td>data_content</td>
    <td>String</td>
	<td>是</td>
	<td>1000</td>
	<td>存证内容,建议将原始数据摘要后作为存证内容</td>
	<td>864D4DE15097B3A2D0508A0D5CC724F4</td>
</tr>
<tr>
    <td>data_key</td>
    <td>String</td>
	<td>是</td>
	<td>60</td>
	<td>本次存证唯一标识，可以为商户业务系统订单号</td>
	<td>10001</td>
</tr>
<tr>
    <td>notify_url</td>
    <td>String</td>
	<td>是</td>
	<td>-</td>
	<td>异步通知地址,由商户侧指定</td>
	<td></td>
</tr>
</table>

- 公共响应参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>return_code</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>返回状态码</td>
    <td>SUCCESS</td>
</tr>
<tr>
    <td>return_msg</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>返回状态码描述</td>
    <td>ok</td>
</tr>
</table>



以下字段在return_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>result_code</td>
    <td>String</td>
    <td>否</td>
    <td>16</td>
    <td>业务状态码</td>
    <td>SUCCESS</td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>签名结果</td>
    <td>565656565</td>
</tr>
</table>


以下字段在return_code为SUCCESS时，result_code为FAIL时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>error_code</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>详见错误列表</td>
    <td>0</td>
</tr>
<tr>
    <td>error_msg</td>
    <td>String</td>
    <td>否</td>
    <td>128</td>
    <td>结果不明确，不处理单据，状态=Unknow</td>
    <td>ok</td>
</tr>
</table>

- 响应参数

以下字段在return_code为SUCCESS时，result_code为SUCCESS时返回


<table data-hy-role="doctbl"> 
    <th>参数</th>
    <th>类型</th>
	<th>是否必填</th>
	<th>最大长度</th>
	<th>描述</th>
	<th>示例值</th>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
	<td>是</td>
	<td>64</td>
	<td>汇元订单号</td>
	<td>1007</td>
</tr>
<tr>
    <td>data_key</td>
    <td>String</td>
	<td>是</td>
	<td>60</td>
	<td>本次存证唯一标识，可以为商户业务系统订单号</td>
	<td>10001</td>
</tr>
<tr>
    <td>tx_id</td>
    <td>String</td>
	<td>是</td>
	<td>100</td>
	<td>交易hash</td>
	<td>3944c64372c2c4</td>
</tr>
<tr>
    <td>data_content</td>
    <td>String</td>
	<td>是</td>
	<td>1000</td>
	<td>存证内容,建议将原始数据摘要后作为存证内容</td>
	<td>864D4DE15097B3A2D0508A0D5CC724F4</td>
</tr>
<tr>
    <td>trade_status</td>
    <td>int</td>
	<td>是</td>
	<td>1</td>
	<td>存证状态，Undeal=未处理，InPack=打包中，PartConfirm=部分确认，Success=已完成，Fail=失败</td>
	<td>InPack</td>
</tr>
</table>


## 存证查询接口

- 简要描述：

区块存证接口查询，可根据data_key、汇元单号，查询区块链上的信息。

> 请求URL:`https://api.heemoney.com/heechain/v1/depositquery `

> 请求方式:`POST`   

> method：`heechain.deposit.query`

> 数据格式：`json串`

- 公共参数

<table data-hy-role="doctbl"> 
    <th>参数</th>
    <th>类型</th>
	<th>是否必填</th>
	<th>最大长度</th>
	<th>描述</th>
	<th>示例值</th>
</tr>
<tr>
    <td>method</td>
    <td>String</td>
	<td>是</td>
	<td>128</td>
	<td>业务名称</td>
	<td>heechain.deposit.query</td>
</tr>
<tr>
    <td>version</td>
    <td>String</td>
	<td>否</td>
	<td>10</td>
	<td>版本号，默认1.0</td>
	<td>V1.0</td>
</tr>
<tr>
    <td>app_id</td>
    <td>String</td>
	<td>是</td>
	<td>32</td>
	<td>应用ID，商户的应用id</td>
	<td>Ap22512545</td>
</tr>
<tr>
    <td>mch_uid</td>
    <td>String</td>
	<td>是</td>
	<td>32</td>
	<td>商户统一编号</td>
	<td>276952</td>
</tr>
<tr>
    <td>charset</td>
    <td>String</td>
    <td>否</td>
    <td>10</td>
    <td>编码格式默认为UTF-8</td>
    <td>UTF-8,GBK,GB2312</td>
</tr>
<tr>
    <td>sign_type</td>
    <td>String</td>
	<td>是</td>
	<td>10</td>
	<td>商户生成签名字符串所使用的签名算法类型</td>
	<td>md5</td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
	<td>是</td>
	<td>256</td>
	<td>商户请求参数的签名串</td>
	<td>详见示例</td>
</tr>
<tr>
    <td>timestamp</td>
    <td>String</td>
	<td>是</td>
	<td>19</td>
	<td>发送请求的时间</td>
	<td>Json格式</td>
</tr>
<tr>
    <td>biz_content</td>
    <td>String</td>
	<td>是</td>
	<td>不限</td>
	<td>请求参数集合，Json格式，长度不限，具体参数见如下业务参数</td>
	<td>Json格式</td>
</tr>
</table>

- 业务参数

<table data-hy-role="doctbl"> 
    <th>参数</th>
    <th>类型</th>
	<th>是否必填</th>
	<th>最大长度</th>
	<th>描述</th>
	<th>示例值</th>
</tr>
<tr>
    <td>data_key</td>
    <td>String</td>
	<td>否</td>
	<td>60</td>
	<td>商户订单号</td>
	<td>T201821521512</td>
</tr>
<tr></tr>
    <td>hy_bill_no</td>
    <td>String</td>
	<td>否</td>
	<td>50</td>
	<td>汇元订单号</td>
	<td>G2018022812A231</td>
</tr>
</table>
汇元单号或data_key必须提供一个，以汇元单号优先


- 公共响应参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>return_code</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>返回状态码</td>
    <td>SUCCESS</td>
</tr>
<tr>
    <td>return_msg</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>返回状态码描述</td>
    <td>ok</td>
</tr>
</table>



以下字段在return_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>result_code</td>
    <td>String</td>
    <td>否</td>
    <td>16</td>
    <td>业务状态码</td>
    <td>SUCCESS</td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>签名结果</td>
    <td>565656565</td>
</tr>
</table>


以下字段在return_code为SUCCESS时，result_code为FAIL时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>error_code</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>详见错误列表</td>
    <td>0</td>
</tr>
<tr>
    <td>error_msg</td>
    <td>String</td>
    <td>否</td>
    <td>128</td>
    <td>结果不明确，不处理单据，状态=Unknow</td>
    <td>ok</td>
</tr>
</table>

- 响应参数

以下字段在return_code为SUCCESS时，result_code为SUCCESS时返回


<table data-hy-role="doctbl"> 
    <th>参数</th>
    <th>类型</th>
	<th>是否必填</th>
	<th>最大长度</th>
	<th>描述</th>
	<th>示例值</th>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>汇元订单号</td>
	<td>1004</td>
</tr>
<tr>
    <td>tx_id</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>交易hash</td>
	<td>4e716a....29cf37</td>
</tr>
<tr>
    <td>data_content</td>
    <td>String</td>
	<td>是</td>
	<td>1000</td>
	<td>存证内容,建议将原始数据摘要后作为存证内容</td>
	<td>864D4DE15097B3A2D0508A0D5CC724F4</td>
</tr>
<tr>
    <td>data_key</td>
    <td>String</td>
	<td>是</td>
	<td>60</td>
	<td>本次存证唯一标识，可以为商户业务系统订单号</td>
	<td>10001</td>
</tr>

<tr>
    <td>trade_status</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>存证状态，Undeal=未处理，InPack=打包中，PartConfirm=部分确认，Success=已完成，Fail=失败</td>
	<td>Success</td>
</tr>
</table>


## 交易查询接口

- 简要描述：

区块存证接口查询，根据交易ID（存证提交时，返回的txt_id）查询区块链上的信息。

> 请求URL:`https://api.heemoney.com/heechain/v1/depositquerytxhash`

> 请求方式:`POST`  

> method：`heechain.deposit.query.txhash`

> 数据格式：`json串`

- 公共参数

<table data-hy-role="doctbl"> 
    <th>参数</th>
    <th>类型</th>
	<th>是否必填</th>
	<th>最大长度</th>
	<th>描述</th>
	<th>示例值</th>
</tr>
<tr>
    <td>version</td>
    <td>String</td>
	<td>否</td>
	<td>10</td>
	<td>版本号，默认1.0</td>
	<td>V1.0</td>
</tr>
<tr>
    <td>method</td>
    <td>String</td>
	<td>是</td>
	<td>128</td>
	<td>业务名称</td>
	<td>heechain.deposit.query.txhash</td>
</tr>
<tr>
    <td>app_id</td>
    <td>String</td>
	<td>是</td>
	<td>32</td>
	<td>应用ID，商户的应用id</td>
	<td>Ap22512545</td>
</tr>
<tr>
    <td>mch_uid</td>
    <td>String</td>
	<td>是</td>
	<td>32</td>
	<td>商户统一编号</td>
	<td>276952</td>
</tr>
<tr>
    <td>sign_type</td>
    <td>String</td>
	<td>是</td>
	<td>10</td>
	<td>商户生成签名字符串所使用的签名算法类型</td>
	<td>md5</td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
	<td>是</td>
	<td>256</td>
	<td>商户请求参数的签名串</td>
	<td>详见示例</td>
</tr>
<tr>
    <td>timestamp</td>
    <td>String</td>
	<td>是</td>
	<td>19</td>
	<td>发送请求的时间</td>
	<td>Json格式</td>
</tr>
<tr>
    <td>biz_content</td>
    <td>String</td>
	<td>是</td>
	<td>不限</td>
	<td>请求参数集合，Json格式，长度不限，具体参数见如下业务参数</td>
	<td>Json格式</td>
</tr>
</table>

- 业务参数

<table data-hy-role="doctbl"> 
    <th>参数</th>
    <th>类型</th>
	<th>是否必填</th>
	<th>最大长度</th>
	<th>描述</th>
	<th>示例值</th>
</tr>
<tr>
    <td>tx_hash</td>
    <td>String</td>
	<td>是</td>
	<td>64</td>
	<td>区块交易hash</td>
	<td>02450f3da7b7877463041badeea459785b373d86db78ec03616cb344c63e5f60</td>
</tr>
</table>

- 公共响应参数

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>return_code</td>
    <td>String</td>
    <td>是</td>
    <td>16</td>
    <td>返回状态码</td>
    <td>SUCCESS</td>
</tr>
<tr>
    <td>return_msg</td>
    <td>String</td>
    <td>是</td>
    <td>128</td>
    <td>返回状态码描述</td>
    <td>ok</td>
</tr>
</table>



以下字段在return_code为SUCCESS时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>result_code</td>
    <td>String</td>
    <td>否</td>
    <td>16</td>
    <td>业务状态码</td>
    <td>SUCCESS</td>
</tr>
<tr>
    <td>sign</td>
    <td>String</td>
    <td>是</td>
    <td>32</td>
    <td>签名结果</td>
    <td>565656565</td>
</tr>
</table>


以下字段在return_code为SUCCESS时，result_code为FAIL时返回

<table data-hy-role="doctbl">
    <th>参数</th>
    <th>类型</th>
    <th>是否必填</th>
    <th>最大长度</th>
    <th width="220">描述</th>
    <th width="163">示例值</th>
</tr>
<tr>
    <td>error_code</td>
    <td>int</td>
    <td>是</td>
    <td></td>
    <td>详见错误列表</td>
    <td>0</td>
</tr>
<tr>
    <td>error_msg</td>
    <td>String</td>
    <td>否</td>
    <td>128</td>
    <td>结果不明确，不处理单据，状态=Unknow</td>
    <td>ok</td>
</tr>
</table>

- 响应参数

以下字段在return_code为SUCCESS时，result_code为SUCCESS时返回


<table data-hy-role="doctbl"> 
    <th>参数</th>
    <th>类型</th>
	<th>是否必填</th>
	<th>最大长度</th>
	<th>描述</th>
	<th>示例值</th>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>汇元订单号</td>
	<td>1004</td>
</tr>
<tr>
    <td>tx_hash</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>交易hash</td>
	<td>4e716a....29cf37</td>
</tr>
<tr>
    <td>data_content</td>
    <td>String</td>
	<td>是</td>
	<td>1000</td>
	<td>存证内容,建议将原始数据摘要后作为存证内容</td>
	<td>864D4DE15097B3A2D0508A0D5CC724F4</td>
</tr>
<tr>
    <td>data_key</td>
    <td>String</td>
	<td>是</td>
	<td>60</td>
	<td>本次存证唯一标识，可以为商户业务系统订单号</td>
	<td>10001</td>
</tr>
<tr>
    <td>trade_status</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>存证状态，Undeal=未处理，InPack=打包中，PartConfirm=部分确认，Success=已完成，Fail=失败</td>
	<td>Success</td>
</tr>
</table>
