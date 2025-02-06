---
created: 2024-11-01 23:03
last_modified: 2024-11-01 23:03
tags:
---
### nginx.conf
- /etc/nginx/nginx.conf
- vim //etc/nginx/sites-available/node-server
### .key -> .pem 변환
`openssl rsa -in www_dgst.site-2.key > www_dgst.site-2.pem`
### .crt -> .pem 변환
`openssl x509 -inform PEM -in www_dgst.site_cert-2.crt > www_dgst.site_cert-2.pem`
