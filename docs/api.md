## 区块存证接口

- 简要描述：

区块存证接口，为合同管理提供非中心化的数据存储与读取，保证数据的绝对安全，不可抵赖。

> 请求URL:`https://api.heemoney.com/heechain/v1/signadd`

> 请求方式:`POST`   

> method：`heechain.sign.add`

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
	<td>heechain.sign.add</td>
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
    <td>out_trade_no</td>
    <td>String</td>
	<td>是</td>
	<td>20</td>
	<td>商户订单号</td>
	<td>T201821521512</td>
</tr>
<tr>
    <td>data_type</td>
    <td>String</td>
	<td>是</td>
	<td>20</td>
	<td>存证类型，自定义参数</td>
	<td>签约、存证</td>
</tr>
<tr>
    <td>data_key</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>存证编号，自定义参数</td>
	<td>10001</td>
</tr>
<tr>
    <td>data</td>
    <td>String</td>
	<td>是</td>
	<td>-</td>
	<td>存证内容，合同MD5摘要结果</td>
	<td>864D4DE15097B3A2D0508A0D5CC724F4</td>
</tr>
<tr>
    <td>note</td>
    <td>String</td>
	<td>否</td>
	<td>255</td>
	<td>备注</td>
	<td>创建合同</td>
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
    <td>out_trade_no</td>
    <td>String</td>
	<td>是</td>
	<td>128</td>
	<td>商户订单号</td>
	<td>T201821521512</td>
</tr>
<tr>
    <td>tx_id</td>
    <td>String</td>
	<td>是</td>
	<td>20</td>
	<td>交易hash</td>
	<td>3944c64372c2c4</td>
</tr>
<tr>
    <td>address</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>存证账户地址</td>
	<td>hy13JuhgwZS</td>
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

区块存证接口查询，根据商户订单号、汇元单号，查询区块链上的信息。

> 请求URL:`https://api.heemoney.com/heechain/v1/signquery`

> 请求方式:`POST`   

> method：`heechain.sign.query`

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
	<td>heechain.sign.query</td>
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
    <td>out_trade_no</td>
    <td>String</td>
	<td>否</td>
	<td>20</td>
	<td>商户订单号</td>
	<td>T201821521512</td>
</tr>
<tr>
    <td>hy_bill_no</td>
    <td>String</td>
	<td>否</td>
	<td>50</td>
	<td>汇元订单号</td>
	<td>G2018022812A231</td>
</tr>
</table>
汇元单号或商户订单号必须提供一个，以汇元单号优先


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
    <td>out_bill_no</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>商户订单号</td>
	<td>T201821521512</td>
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
    <td>data_key</td>
    <td>String</td>
	<td>是</td>
	<td>20</td>
	<td>存证编号</td>
	<td>10001</td>
</tr>
<tr>
    <td>data_type</td>
    <td>String</td>
	<td>是</td>
	<td>64</td>
	<td>存证类型，原样返回</td>
	<td>签约、存证</td>
</tr>
<tr>
    <td>data</td>
    <td>int</td>
	<td>是</td>
	<td>1</td>
	<td>存证内容，合同MD5摘要结果</td>
	<td>864D4DE15097B3A2D0508A0D5CC724F4</td>
</tr>
<tr>
    <td>trade_status</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>存证状态，Undeal=未处理，InPack=打包中，PartConfirm=部分确认，Success=已完成，Fail=失败</td>
	<td>Success</td>
</tr>
<tr>
    <td>address</td>
    <td>String</td>
	<td>是</td>
	<td>500</td>
	<td>存证地址</td>
	<td>hy1e5EhWc4xqMHRqZCufhZu5MsjYfvBdTtv</td>
</tr>
</table>


## 交易查询接口

- 简要描述：

区块存证接口查询，根据交易ID（存证提交时，返回的txt_id）查询区块链上的信息。

> 请求URL:`https://api.heemoney.com/heechain/v1/signquerybytxid`

> 请求方式:`POST`  

> method：`heechain.sign.query.txid`

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
	<td>heechain.sign.query.txid</td>
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
    <td>tx_id</td>
    <td>String</td>
	<td>是</td>
	<td>64</td>
	<td>区块交易hash</td>
	<td>da4yWWszCaBy7pfhoQpu7HTXuaQQ9xS</td>
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
    <td>out_bill_no</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>商户订单号</td>
	<td>T201821521512</td>
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
    <td>data_key</td>
    <td>String</td>
	<td>是</td>
	<td>20</td>
	<td>存证编号</td>
	<td>10001</td>
</tr>
<tr>
    <td>data_type</td>
    <td>String</td>
	<td>是</td>
	<td>64</td>
	<td>存证类型，原样返回</td>
	<td>签约、存证</td>
</tr>
<tr>
    <td>data</td>
    <td>int</td>
	<td>是</td>
	<td>1</td>
	<td>存证内容，合同MD5摘要结果</td>
	<td>864D4DE15097B3A2D0508A0D5CC724F4</td>
</tr>
<tr>
    <td>trade_status</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>存证状态，Undeal=未处理，InPack=打包中，PartConfirm=部分确认，Success=已完成，Fail=失败</td>
	<td>Success</td>
</tr>
<tr>
    <td>address</td>
    <td>String</td>
	<td>是</td>
	<td>500</td>
	<td>存证地址</td>
	<td>hy1e5EhWc4xqMHRqZCufhZu5MsjYfvBdTtv</td>
</tr>
</table>
