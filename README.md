# Fail2Ban HAProxy Examples

Examples based on the default log format defined in `/etc/haproxy/haproxy.cfg`

`log-format "%ci:%cp [%tr] %ft %b/%s %TR/%Tw/%Tc/%Tr/%Ta %ST %B %CC %CS %tsc %ac/%fc/%bc/%sc/%rc %sq/%bq %hr %hs %{+Q}r"`

## Example log entry
Apr 21 10:13:56 my-lb haproxy[4109792]: 123.123.123.123:49074 [21/Apr/2026:17:13:56.063] fe_http~ be_frontend_80/my-node 0/0/0/116/182 404 56165 - - --NI 426/426/7/1/0 0/0 {my.domain.com} "GET /dir/file.html HTTP/1.1"

- `%ci` client ip
- `%cp` client port
- `%tr` datetime of the start of HTTP request
- `%ft` frontend name transport (‘~’ suffix for SSL)
- `%b` backend name
- `%s` server name
- `%TR` time to receive the full request from the first byte
- `%Tw` missing in doc (?) documented as "Tw" (thanks for that)
- `%Tc` time to establish a TCP connection to the server
- `%Tr` response time
- `%Ta` the active time of requests (from %TR to end)
- `%ST` status code
- `%B` bytes read
- `%CC` captured request cookie
- `%CS` captured response cookie
- `%tsc` termination state with cookie status
- `%ac` process concurrent connections
- `%fc` frontend concurrent connections
- `%bc` backend concurrent connections
- `%sc` server concurrent connections
- `%rc` umber of retries
- `%sq` server queue
- `%bq` backend queue
- `%hr` captured request headers
- `%hs` captured response headers
- `%{+Q}r` HTTP request (in quotes (={+Q})
