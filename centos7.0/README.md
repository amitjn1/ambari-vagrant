Ambari falied to register with default configurations

the ambari-agent logs showed:

ERROR 2019-02-13 17:03:13,563 NetUtil.py:96 - EOF occurred in violation of protocol (_ssl.c:618)
ERROR 2019-02-13 17:03:13,563 NetUtil.py:97 - SSLError: Failed to connect. Please check openssl library versions.

and nodes did not appear.

This can be fixed by adding:

[security]
force_https_protocol=PROTOCOL_TLSv1_2

in

/etc/ambari-agent/conf/ambari-agent.ini
