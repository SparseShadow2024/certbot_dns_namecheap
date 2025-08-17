# Usage

## namecheap.ini
```ini
dns_namecheap_username=my-username
dns_namecheap_api_key=my-api-key
```

## Python

* Install the plugin into the same python environment like `certbot`:
```sh
git clone https://github.com/SparseShadow2024/certbot_dns_namecheap.git
pip install certbot-dns-namecheap/
```

* Check that `certbot` discovers the plugin:
```sh
certbot plugins
```

* Now run the command:
```sh
certbot certonly \
  -a dns-namecheap \
  --dns-namecheap-credentials=./namecheap.ini \
  --agree-tos \
  --email "examplemain@mail.com" \
  -d "www.exampledomain.com" \
  --test-cert
```

* After a successful run, remove the last parameter `--test-cert` which enabled [staging server](https://letsencrypt.org/docs/staging-environment/) and run again.