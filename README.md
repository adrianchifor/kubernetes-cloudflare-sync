# kubernetes-cloudflare-sync

Watches and synchronises k8s node IPs with A records on Cloudflare.

### Configuration
Arguments:
```
-cloudflare-api-email string
  	the email address to use for cloudflare
-cloudflare-api-key string
  	the key to use for cloudflare
-cloudflare-proxy string
  	enable cloudflare proxy on dns (default false)
-cloudflare-ttl string
  	ttl for dns (default 120)
-dns-name string
  	the dns name for the nodes, comma-separated for multiple (same root)
```

Equivalent environment variables:
```
CF_API_EMAIL
CF_API_KEY
CF_PROXY
CF_TTL
DNS_NAME
```

### Deploy

Only for GKE:
```
kubectl create clusterrolebinding cluster-admin-binding --clusterrole cluster-admin --user your@email.com
```

Then fill in `deploy.yaml` and apply:
```
kubectl apply -f deploy.yaml
```
