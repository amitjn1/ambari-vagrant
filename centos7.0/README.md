INSTALLATION 

  If Ambari falied to register nodes with default configurations

  the ambari-agent logs showed:

  ERROR 2019-02-13 17:03:13,563 NetUtil.py:96 - EOF occurred in violation of protocol (_ssl.c:618)
  ERROR 2019-02-13 17:03:13,563 NetUtil.py:97 - SSLError: Failed to connect. Please check openssl library versions.

  and nodes did not appear.

  This can be fixed by adding:

  [security]
  force_https_protocol=PROTOCOL_TLSv1_2

  in

  /etc/ambari-agent/conf/ambari-agent.ini


  Reference: https://github.com/adaltas/jumbo/issues/12

SQOOP
  MSSQL driver install
    download sqljdbc_6.2.2.1_enu.tar.gz from microsoft
    $ gzip -d sqljdbc_6.2.2.1_enu.tar.gz
    $ tar xf sqljdbc_6.2.2.1_enu.tar
    $ sudo cp sqljdbc_6.2/enu/mssql-jdbc-6.2.2.jre8.jar /usr/hdp/3.1.4.0-315/sqoop/lib/
    $ sqoop list-databases --connect jdbc:sqlserver://<IP address>:1433 --username <User> --password <Password>
    
    

