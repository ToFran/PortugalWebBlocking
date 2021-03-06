# [List of websites blocked in Portugal][1]

**2017-11-01 WARNING: THIS IS OUTDATED, I'm going to start maintaining this soon (check the other branches)**

This repo contains (some of) the domains currently being blocked by ISP's in Portugal.

**blockList.txt** - A simple list of the blocked domains domains

**blockList.json** - A detailed JSON file with all the domains, that follows the following format:
```JSON
{
	"info" : {
		"isps" : {
			"ispName" : {
				"dnsAdress" : ["0.0.0.0"],
				"lastScan" : ["yyyy-MM-ddThh:mm:ss"]
			}
		},
		"reference" : {
			"name" : "Google Public DNS",
			"dnsAdress" : ["8.8.8.8", "8.8.4.4"],
			"lastScan" : ["yyyy-MM-ddThh:mm:ss"]
		}
	},
	"domains":{
		"domain.name" : {
			"hosts": {
				"@": {
					"blockDate" : "yyyy-MM",
					"ip" : ["0.0.0.0"],
					"reason": "Why was the website blocked? (Copyright | Gambling | 'Mistake' | Unknown)",
					"isp" : {
						"ispName" : {
							"status" : 0,
							"dnsResponse" : [
								"255.255.255.255"
							]
						}
					}
				}
			}
		}
	}
}
```

Status codes:
* `-2` Not Scanned;
* `-1` Can't be Resolved (Website down);
* `0` Not Blocked (Same response, self-explanatory);
* `1` DNS Blocked (The DNS did not reply, but the domain was resolved by the reference DNS);
* `0` DNS Redirect (The DNS replied with a different IP from what it actually is).


**domainScan.py** - the script used to scan and generate the data for all the domains

**dnsServerList.json** - the list of DNS servers (ISP's DNS and open DNS's)

**/web** - The folder with the static resources to the [web viewer][1]

## Acknowledgements

- [dnspython](https://github.com/rthalley/dnspython)
- [jquery](https://jquery.com/)
- [tablesorter](https://github.com/christianbach/tablesorter)
- [GitHub Corners](https://github.com/tholman/github-corners)
- [Stop hand icon](https://en.wikipedia.org/wiki/File:Stop_hand.svg)


## License

[MIT](LICENSE)

[1]: <https://tofran.github.io/PortugalWebBlocking/>
