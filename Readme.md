# forticlient

Connect to a FortiNet VPNs through docker

## Usage

The container uses the forticlientsslvpn_cli linux binary to manage ppp interface and squid forwards HTTP requests which need sslvpn to access.


```bash
# Start the priviledged docker container with squid http proxy
docker run -it --rm \
  --privileged \
  -p 31280:3128 \
  -e VPNADDR=host:port \
  -e VPNUSER=me@domain \
  -e VPNPASS=secret \
  risid/forticlient

# Test squid proxy by curl
curl -x localhost:31280 202.207.247.51:8065

```

### Precompiled binaries

Thanks to [https://hadler.me](https://hadler.me/linux/forticlient-sslvpn-deb-packages/) for hosting up to date precompiled binaries which are used in this Dockerfile.

[Squid](https://help.ubuntu.com/community/Squid) is a Proxy server.
