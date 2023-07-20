# create self sign certificate with openssl command and check it
## certificate location
CERT_LOCATION=./nginx/certs

## generate key and cert
openssl req -x509 -nodes -newkey \
rsa:4096 -days 365 \
-keyout $CERT_LOCATION/key.pem \
-subj "/C=IR/ST=Iran/L=Tehran/O=DockerMe/OU=IT/CN=DockerMe.ir/emailAddress=rafiee1001@gmail.com" \
-out $CERT_LOCATION/cert.pem 

## cehck certificate
openssl x509 -text -noout -in $CERT_LOCATION/cert.pem

## check nginx directory
tree nginx
