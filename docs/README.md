## 安全规范

一. 签名算法
- 对需签名的请求（有一个标准头信息和特定的消息体，都是json格式），msg=[方法名称][请求json字符串]

```text
例如： 
签名串：
create_account{"addr":"hc1Ecm4cHhijf3mgCcPkN6g7Jpx8FMwzBWfb","ts":1519353391,"note":"Test Create Account3"}
签名结果：
2035495fd495d1013b2d05a58f4366c72d51d1012bd49dbbcfb0dc4d3f56633a6a1ee843a4c7f6d9c3600542e237d07cb8079d8921f3030490c8217568e188929c,1f861a081dee2391409ea3bfba4ec0e00c04ec137a4f965293fdb8f2624ec726760ae59e86d0fcce1020f727f96709c253ed2e056a11628c31c5b727273d7b6fe3
```

- 区块链上的查询方法无需签名的请求，不用考虑签名串的拼接

