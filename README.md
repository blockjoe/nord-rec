# nord-rec

A simple bash CLI to get the result of [NordVPN's reccomended server functionality](https://nordvpn.com/servers/tools/).

## Dependencies

curl
jq
column

## Examples

Get the default automatic result

```bash
$ nord-rec
us6919.nordvpn.com
```

Filter by country

```bash
$ nord-rec -c Sweden
se437.nordvpn.com
```

Filter by server group

```bash
$ nord-rec -g P2P
us5445.nordvpn.com
```

Filter by technology support

```bash
$ nord-rec -c Sweden -t Wiregaurd
se495.nordvpn.com
```

Get multiple reccomendations

```bash
$ nord-rec -c Sweden -n 5
se495.nordvpn.com
se458.nordvpn.com
se502.nordvpn.com
se503.nordvpn.com
se399.nordvpn.com
```

Get detailed information about the reccomendation
```bash
$ nord-rec -c Sweden -v
      Server: Sweden #495
    Hostname: se495.nordvpn.com
    Location: Sweden - Stockholm
        Load: 6
     Created: 2020-08-04 10:18:17
     Updated: 2021-01-02 01:06:43
      Region: Europe
      Groups: Standard VPN servers, P2P
Technologies:
              - IKEv2/IPSec
              - OpenVPN UDP
              - OpenVPN TCP
              - HTTP Proxy (SSL)
              - HTTP CyberSec Proxy (SSL)
              - Wireguard
```

Get help
```bash
$ nord-rec -h
Get the result of Nord VPN's reccomended server utility.

Usage: nord-rec [options]

Options:
  -c, --country <country-name|country-id>
      Filter the reccomendations by country.
  -g, --group <group-name|group-id>
      Filter the reccomendations by group.
  -t, --technology <tech-name|tech-id>
      Filter the reccomendations by technology.
  -n <n-results>
      Get n results.
  --list-countries
      Display the availble countries and ids.
  --list-groups
      Display the available server groups and ids.
  --list-technologies
      Display the available technologies and ids.
  -v, --verbose
      Display more information about the reccomended server(s).
  -h, --help
      Display help message.
```
