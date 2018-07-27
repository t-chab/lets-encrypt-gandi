# Description

This is a small wrapper, written in bash, with minimal dependencies to create/renew easily Let'encrypt certificates using dns challenge and Gandi Live DNS API.

This wrapper is composed of two scripts : 

- _run.sh_ : main script which does some background check, then call dehydrated to create / renew Let's encrypt certs 
- _hook.sh_ : [Dehydrated](https://dehydrated.io) hook to handle Gandi Live DNS API.

This scripts can be used from minimal environment like OpenWRT router for example.

# Dependencies

- [bash](https://www.gnu.org/software/bash)
- [curl](https://curl.haxx.se)
- [Dehydrated](https://dehydrated.io) (automatically downloaded from Github if missing)
- [openssl](https://www.openssl.org)
- [diffutils](http://www.gnu.org/software/diffutils)
- A [Gandi Live DNS API key](https://doc.livedns.gandi.net)

# Usage

Create a directory to store configuration, then launch *run.sh*, passing configuration through environment variables 

```
git clone https://github.com/tchabaud/lets-encrypt-gandi
cd lets-encrypt-gandi
mkdir data # To store configuration and certs
WORKDIR=data DOMAIN='*.mydomain.tld' API_KEY="Your_Gandi_Live_DNS_API_KEY" ./run.sh
```

Enjoy, and feel free to open [issues](https://github.com/tchabaud/lets-encrypt-gandi/issues) if you encounter problems.
