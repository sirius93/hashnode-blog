## How to enable TLS1.2 in Rserve

About two years back when I first took up the task of enabling TLS 1.2 in some of the components in our technology stack. it felt like a very tough job because of two major reasons listed below.

1.  I belong to the fraternity of Front End Developers who are majorly known for their lack of in-depth knowledge of *DevOps* and *backend*.
2.  There was a lack of proper documentation and I had to do a lot of googling around because most of the famous tech platforms cover very little about these less known topics or otherwise blame it on poor SEO measures taken by those bloggers who cover topics like this.

we can’t blame them because **SEO** is something that has more to do with front-end development than backend or DevOps.

I will be noting down a list of basic tasks to perform in order to enable TLS in Rserve. also, I will be adding more posts to give you an insight into some sub-topics i.e. (how to generate private/public key, how to test if tls1.2 is enabled, etc.).

P.S: Please note that these steps are for ***Rserve*** on Linux.

Here we go…..

Step 1: Generate a **private key** and self-signed certificate (i will be covering this in another post soon).

Step 2: install **libssl-dev** first in your Linux machine and then install Rserve, So Rserve is compiled with TLS support.

Step 3: Edit or Add */etc/Rserv.conf* file, and following parameters.

> remote enable  
>  plaintext disable  
>  encoding utf8  
>  qap.tls.port <port for SSL/TLS channel> // 6311 by default  
>  tls.key <private key KEY file>  
>  tls.cert <server certificate CERT file>  
>  gid 1001  
>  uid 1001  
>  qap disable  
>  maxinbuf 4194304

Step 4: Start Rserve. With this action, a server is created to listen to the TLS port.

Step 5: Run the following OpenSSL command to test

> openssl s\_client -connect localhost:6311 -tls1\_2

This should help you successfully enable **TLS 1.2** in your Rserve application. feel free to write to me or comment below in case you are facing any issues.