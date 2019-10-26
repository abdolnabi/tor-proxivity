# tor-proxivity

sudo docker run -it -p 8118:8118 -p 9050:9050 -d abdolnabi/tor-proxivity

curl -Lx http://<ipv4_address>:8118 http://jsonip.com/
#POWERSHELL
Invoke-RestMethod -Proxy http://<ipv4_address>:8118 http://jsonip.com/
