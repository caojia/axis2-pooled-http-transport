Axis2 Pooled Http Transport
==========================

The default http transport implementation (CommonsHTTPTransportSender) use apache commons' MultiThreadedHttpConnectionManager, which defaults to 2 connections per host and 20 connections in total, which is not enough in some cases. 

So we decided to extend the default implementation to create a configurable connection pool with larger connections limit.

Usage
-----
```
<transportSender name="http" class="com.creditease.bdp.axis2.transport.http.PooledHTTPTransportSender">
        <parameter name="PROTOCOL">HTTP/1.1</parameter>
        <parameter name="Transfer-Encoding">chunked</parameter>
        <parameter name="transport.http.max_connections_per_host">20</parameter>
        <parameter name="transport.http.max_connections_total">100</parameter>
</transportSender>
```
