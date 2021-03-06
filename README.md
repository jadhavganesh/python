# Getting Started

This repo provides a Python client for the [ipdata.co](https://ipdata.co) Free Geolocation API.

## Installation

Run

```
pip install ipdata
```

## Examples

```
from ipdata import ipdata
ip = ipdata.ipdata()
data = ip.lookup('1.1.1.1')
if data['status']==200:
    for key in data['response']:
        print('#', key, ':', data['response'][key])
else:
    print(data['response'])
# ip : 1.1.1.1
# city : Research
# region : Victoria
# country_name : Australia
# country_code : AU
# continent_name : Oceania
# continent_code : OC
# latitude : -37.7
# longitude : 145.1833
# asn : 
# organisation : 
# postal : 3095
# currency : AUD
# currency_symbol : $
# calling_code : 61
# flag : https://ipdata.co/flags/au.png
# time_zone : Australia/Melbourne
```

To get a specific field, do

```
country = ip.lookup('1.1.1.1')['response']['country_name']
# 'Australia'
```

### Using API keys

```
from ipdata import ipdata

apikey = 'myapikey'
ip = ipdata.ipdata(apikey=apikey)
data = ip.lookup('1.1.1.1')

if data['status']==200:
    for key in data['response']:
        print('#', key, ':', data['response'][key])
else:
    print(data['response'])
```