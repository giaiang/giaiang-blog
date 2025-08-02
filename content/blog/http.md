+++
title = "HTTP"
date = "2025-07-16T21:52:49+08:00"

#
# description is optional
#
# description = "An optional description for SEO. If not provided, an automatically created summary will be used."

tags = ["github","hugo","os",]
+++

HTTP状态码

RFC规范，GET是安全且幂等的，因为它是“只读”的
POST是“新增或提交数据”的操作，会修改服务器上的数据，是不安全和不幂等的

HTTP缓存技术
- 强制缓存：浏览器判断缓存没过期就使用浏览器本地缓存。（在HTTP响应头加入过期时间）
- 协商缓存：发起请求后，由服务端判断是否可以使用本地缓存，是的话响应304。（基于Last-Modified最后修改时间/基于ETag唯一标识）
- 
