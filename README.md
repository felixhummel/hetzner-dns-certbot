# Usage
```
apt install curl jq certbot
cat > /etc/hetzner-dns-token  # https://dns.hetzner.com/settings/api-token
curl -Ss https://raw.githubusercontent.com/felixhummel/hetzner-dns-certbot/master/certbot-hetzner-auth.sh > /usr/local/bin/certbot-hetzner-auth.sh
curl -Ss https://raw.githubusercontent.com/felixhummel/hetzner-dns-certbot/master/certbot-hetzner-cleanup.sh > /usr/local/bin/certbot-hetzner-cleanup.sh
chmod +x /usr/local/bin/certbot-hetzner-auth.sh
chmod +x /usr/local/bin/certbot-hetzner-cleanup.sh
certbot certonly --manual --preferred-challenges=dns --manual-auth-hook /usr/local/bin/certbot-hetzner-auth.sh --manual-cleanup-hook /usr/local/bin/certbot-hetzner-cleanup.sh \
    -d example.com -d '*.example.com'
```
