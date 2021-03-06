# Connect to SQL Server with updated certificate

Tune SQL Server configuration to read the new key files, and force encryption only from client
* Set the network.tlscert configuration variable to point to the public key
    * `/opt/mssql/bin/mssql-conf set network.tlscert /etc/ssl/certs/mssql.pem`{{execute T1}} 
* Set the network.tlskey configuration variable to point to the private key
    * `/opt/mssql/bin/mssql-conf set network.tlskey /etc/ssl/private/mssql.key`{{execute T1}} 
* Set the network.forceencryption configuration variable to 0 (initiated by client)
    * `/opt/mssql/bin/mssql-conf set network.forceencryption 0`{{execute T1}} 

Restart the SQL Server service
`systemctl restart mssql-server.service`{{execute T1}}

Now that the service certificates comply with the policy, the client should be able to connect
without any issue, and the connection should be encrypted

`/opt/mssql-tools/bin/sqlcmd -S localhost -U sa -P Redhat1! -N -C -Q "select session_id, encrypt_option from sys.dm_exec_connections where session_id = @@spid"`{{execute T1}}

<pre class="file">
session_id  encrypt_option
----------- ----------------------------------------
         XX TRUE

(1 rows affected)
</pre>
