# tor-proxivity

sudo docker run -it -p 8118:8118 -p 9050:9050 -d abdolnabi/tor-proxivity -l "AU"

curl -Lx http://<ipv4_address>:8118 http://jsonip.com/<br/>
#POWERSHELL<br/>
Invoke-RestMethod -Proxy http://<ipv4_address>:8118 http://jsonip.com/


sudo docker run -it --rm dperson/torproxy -h
Usage: torproxy.sh [-opt] [command]
Options (fields in '[]' are optional, '<>' are required):
    -h          This help
    -b ""       Configure tor relaying bandwidth in KB/s
                possible arg: "[number]" - # of KB/s to allow
    -e          Allow this to be an exit node for tor traffic
    -l "<country>" Configure tor to only use exit nodes in specified country
                required args: "<country>" (IE, "US" or "DE")
                <country> - country traffic should exit in
    -n          Generate new circuits now
    -p "<password>" Configure tor HashedControlPassword for control port
    -s "<port>;<host:port>" Configure tor hidden service
                required args: "<port>;<host:port>"
                <port> - port for .onion service to listen on
                <host:port> - destination for service request

The 'command' (if provided and valid) will be run instead of torproxy
ENVIRONMENT VARIABLES

TORUSER - If set use named user instead of 'tor' (for example root)
BW - As above, set a tor relay bandwidth limit in KB, IE 50
EXITNODE - As above, allow tor traffic to access the internet from your IP
LOCATION - As above, configure the country to use for exit node selection
PASSWORD - As above, configure HashedControlPassword for control port
`SERVICE - As above, configure hidden service, IE '80;hostname:80'
TZ - Configure the zoneinfo timezone, IE EST5EDT
USERID - Set the UID for the app user
GROUPID - Set the GID for the app user
Other environment variables beginning with TOR_ will edit the configuration file accordingly:

TOR_NewCircuitPeriod=400 will translate to NewCircuitPeriod 10
