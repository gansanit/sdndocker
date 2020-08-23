# Run docker
docker run -d --name gansansdnui -p 3443:3443 \
    -v /path/to/zerotier_config/:/var/lib/zerotier-one/ \
    -v /path/to/ztncui_config/:/opt/ztncui/src/etc/  \
    gansanit/sdn

# Generate keys
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout ms/tls/privkey.pem -out ms/tls/fullchain.pem -config build/openssl.cnf
