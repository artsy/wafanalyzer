Web Application Firewall (WAF) Analyzer
====================
This is a simple python script for gathering Top-N analytics from the 'Traffic' app in the Cloudflare portal, where all firewall events are logged. Running it will provide you with the following threat information:

1. Top 15 IPs which trigger rules
2. Top 15 countries for threat origin
3. Top 15 URLs that have been attacked
4. Top 15 rules that have triggered

The WAF Analyzer also provides some additional functions such as fetching information regarding a specific ray ID that triggered the firewall.

Set Up
------
Simply clone this repository, run `pip install -r requirements.txt` then `cp config.py.example config.py`, fill in the details in `config.py` file, then run `./analyzer.py`.

For additional help run `./analyzer.py --help`

Notes
------
A few things to note about the Cloudflare UI and the API.

1. The 'country threats' in the analytics app only cover browser integrity check and IP reputation (not WAF events) - this script is meant to bridge the gap a bit;
2. Any IP firewall event (specific IP/CIDR or Country Code) does not have a rule id. For this reason IP Firewall Events are one large group, it is not possible to break out them to the individual event types (IP vs Country).

Support
------
Please raise an issue on this repository and include detailed information of the problem you are encountering.

> Cloudflare's support team will not be able to resolve issues with this script as it is not officially supported.
