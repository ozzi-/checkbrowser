# Basic Browser Checking
The following ressources will allow you to check if your clients support a specific TLS version as well as specific Ciphers.

## Prerequisites
You will need to servers (two vhosts on the same server will not suffice, this is due to a bug, see https://serverfault.com/questions/637344/is-it-possible-to-set-an-sslprotocol-in-apache-for-a-single-virtualhost-poodle)
Server A will be the page your clients will visit.
Server B will be the vhost that only allows the specified connection parameters.

## How this works
check.html on Server A will do a XHR request to index.html hosted on Server B.
Due to Server B's htaccess file, the cross origin request will be permitted.
If the XHR request succeeds and the response body contains "Success", the client
is capable of the TLS version and ciphers defined in vhost.conf on Server B.