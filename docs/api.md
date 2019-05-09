## 区块存证接口

- 简要描述：

区块存证接口，为合同管理提供非中心化的数据存储与读取，保证数据的绝对安全，不可抵赖。

> 请求URL:``

> 请求方式:`POST`   

> 是否需要证书：`否`

> method：`heechain.evidence.create`

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
	<td>heechain.create.evidence</td>
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
	<td>外部流水号</td>
	<td>T201821521512</td>
</tr>
<tr>
    <td>operate_type</td>
    <td>String</td>
	<td>是</td>
	<td>20</td>
	<td>操作类型</td>
	<td>123</td>
</tr>
<tr>
    <td>contract_no</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>合同编号</td>
	<td>G2018022812A231</td>
</tr>
<tr>
    <td>data</td>
    <td>String</td>
	<td>是</td>
	<td>500</td>
	<td>其他数据,json串查询时原样输出</td>
	<td>md5</td>
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

- 响应参数：

<table data-hy-role="doctbl"> 
    <th>参数</th>
    <th>类型</th>
	<th>是否必填</th>
	<th>最大长度</th>
	<th>描述</th>
	<th>示例值</th>
</tr>
<tr>
    <td>has_error</td>
    <td>String</td>
	<td>是</td>
	<td>16</td>
	<td>返回状态码 true/false</td>
	<td>false</td>
</tr>
<tr>
    <td>message</td>
    <td>String</td>
	<td>是</td>
	<td>1000</td>
	<td>返回状态码描述</td>
	<td>json串</td>
</tr>
</table>

- message响应参数：

<table data-hy-role="doctbl"> 
    <th>参数</th>
    <th>类型</th>
	<th>是否必填</th>
	<th>最大长度</th>
	<th>描述</th>
	<th>示例值</th>
</tr>
<tr>
    <td>hash</td>
    <td>String</td>
	<td>是</td>
	<td>64</td>
	<td>交易hash</td>
	<td>5649d0e06baa10bb195b5e</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
	<td>是</td>
	<td>128</td>
	<td>外部流水号</td>
	<td>T201821521512</td>
</tr>
<tr>
    <td>operate_type</td>
    <td>String</td>
	<td>是</td>
	<td>20</td>
	<td>操作类型</td>
	<td>123</td>
</tr>
<tr>
    <td>contract_no</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>合同编号</td>
	<td>G2018022812A231</td>
</tr>
<tr>
    <td>status</td>
    <td>int</td>
	<td>是</td>
	<td>1</td>
	<td>执行状态</td>
	<td>0=处理中，1=成功，-1=失败</td>
</tr>
<tr>
    <td>data</td>
    <td>String</td>
	<td>是</td>
	<td>500</td>
	<td>其他数据，json串 原样返回</td>
	<td>{json串}</td>
</tr>
</table>


## 合同查询接口

- 简要描述：

区块存证接口查询，根据外部流水号、合同号、操作类型等关键字，查询区块链上的信息。

> 请求URL:``

> 请求方式:`POST`   

> 是否需要证书：`否`

> 数据格式：`form表单`

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
    <td>evidence_address</td>
    <td>String</td>
	<td>是</td>
	<td>64</td>
	<td>存证地址</td>
	<td>da4yWWszCaBy7pfhoQpu7HTXuaQQ9xS</td>
</tr>
<tr>
    <td>out_trade_no</td>
    <td>String</td>
	<td>是</td>
	<td>20</td>
	<td>外部流水号</td>
	<td>T201821521512</td>
</tr>
<tr>
    <td>operate_type</td>
    <td>String</td>
	<td>是</td>
	<td>20</td>
	<td>操作类型</td>
	<td>123</td>
</tr>
<tr>
    <td>agreement_no</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>合同编号</td>
	<td>G2018022812A231</td>
</tr>
</table>

- 响应参数：

<table data-hy-role="doctbl"> 
    <th>参数</th>
    <th>类型</th>
	<th>是否必填</th>
	<th>最大长度</th>
	<th>描述</th>
	<th>示例值</th>
</tr>
<tr>
    <td>has_error</td>
    <td>String</td>
	<td>是</td>
	<td>16</td>
	<td>返回状态码 true/false</td>
	<td>false</td>
</tr>
<tr>
    <td>ret_data</td>
    <td>String</td>
	<td>是</td>
	<td>1000</td>
	<td>返回数据</td>
	<td>json串</td>
</tr>
</table>

- ret_data响应参数：

<table data-hy-role="doctbl"> 
    <th>参数</th>
    <th>类型</th>
	<th>是否必填</th>
	<th>最大长度</th>
	<th>描述</th>
	<th>示例值</th>
</tr>
<tr>
    <td>hash</td>
    <td>String</td>
	<td>是</td>
	<td>64</td>
	<td>交易hash</td>
	<td>5649d0e06baa10bb195b5e</td>
</tr>
<tr>
    <td>out_bill_no</td>
    <td>String</td>
	<td>是</td>
	<td>128</td>
	<td>外部流水号</td>
	<td>T201821521512</td>
</tr>
<tr>
    <td>agreement_no</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>合同编号</td>
	<td>G2018022812A231</td>
</tr>
<tr>
    <td>operate_type</td>
    <td>String</td>
	<td>是</td>
	<td>20</td>
	<td>操作类型</td>
	<td>0=123</td>
</tr>
<tr>
    <td>evidence_address</td>
    <td>String</td>
	<td>是</td>
	<td>64</td>
	<td>存证地址</td>
	<td>da4yWWszCaBy7pfhoQpu7HTXuaQQ9xS</td>
</tr>
<tr>
    <td>status</td>
    <td>int</td>
	<td>是</td>
	<td>1</td>
	<td>执行状态</td>
	<td>0=处理中，1=成功，-1=失败</td>
</tr>
<tr>
    <td>message</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>描述</td>
	<td>test</td>
</tr>
<tr>
    <td>data</td>
    <td>String</td>
	<td>是</td>
	<td>500</td>
	<td>其他数据，json串 原样返回</td>
	<td>0={json串}</td>
</tr>
<tr>
    <td>ctime</td>
    <td>String</td>
	<td>是</td>
	<td>500</td>
	<td>链上操作完成创建时间</td>
	<td>yyyyMMddHHmmss	</td>
</tr>
</table>


## 交易查询接口

- 简要描述：

区块存证接口查询，根据交易ID（存证提交时，返回的txt_id）查询区块链上的信息。

> 请求URL:``

> 请求方式:`POST`   

> 是否需要证书：`否`

> 数据格式：`form表单`

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
    <td>hash</td>
    <td>String</td>
	<td>是</td>
	<td>64</td>
	<td>区块交易hash</td>
	<td>da4yWWszCaBy7pfhoQpu7HTXuaQQ9xS</td>
</tr>
</table>

- 响应参数：

<table data-hy-role="doctbl"> 
    <th>参数</th>
    <th>类型</th>
	<th>是否必填</th>
	<th>最大长度</th>
	<th>描述</th>
	<th>示例值</th>
</tr>
<tr>
    <td>has_error</td>
    <td>String</td>
	<td>是</td>
	<td>16</td>
	<td>返回状态码 true/false</td>
	<td>false</td>
</tr>
<tr>
    <td>ret_data</td>
    <td>String</td>
	<td>是</td>
	<td>1000</td>
	<td>返回数据</td>
	<td>json串</td>
</tr>
</table>

- ret_data响应参数：

<table data-hy-role="doctbl"> 
    <th>参数</th>
    <th>类型</th>
	<th>是否必填</th>
	<th>最大长度</th>
	<th>描述</th>
	<th>示例值</th>
</tr>
<tr>
    <td>hash</td>
    <td>String</td>
	<td>是</td>
	<td>64</td>
	<td>交易hash</td>
	<td>5649d0e06baa10bb195b5e</td>
</tr>
<tr>
    <td>out_bill_no</td>
    <td>String</td>
	<td>是</td>
	<td>128</td>
	<td>外部流水号</td>
	<td>T201821521512</td>
</tr>
<tr>
    <td>agreement_no</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>合同编号</td>
	<td>G2018022812A231</td>
</tr>
<tr>
    <td>operate_type</td>
    <td>String</td>
	<td>是</td>
	<td>20</td>
	<td>操作类型</td>
	<td>0=123</td>
</tr>
<tr>
    <td>evidence_address</td>
    <td>String</td>
	<td>是</td>
	<td>64</td>
	<td>存证地址</td>
	<td>da4yWWszCaBy7pfhoQpu7HTXuaQQ9xS</td>
</tr>
<tr>
    <td>status</td>
    <td>int</td>
	<td>是</td>
	<td>1</td>
	<td>执行状态</td>
	<td>0=处理中，1=成功，-1=失败</td>
</tr>
<tr>
    <td>message</td>
    <td>String</td>
	<td>是</td>
	<td>50</td>
	<td>描述</td>
	<td>test</td>
</tr>
<tr>
    <td>data</td>
    <td>String</td>
	<td>是</td>
	<td>500</td>
	<td>其他数据，json串 原样返回</td>
	<td>0={json串}</td>
</tr>
<tr>
    <td>ctime</td>
    <td>String</td>
	<td>是</td>
	<td>500</td>
	<td>链上操作完成创建时间</td>
	<td>yyyyMMddHHmmss	</td>
</tr>
</table>
