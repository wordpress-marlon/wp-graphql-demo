# wp-graphql-demo
``` 

import requests
import json

url = 'http://localhost:10003/graphql'
query = '{pages {edges{node{title}}}}'
r = requests.post(url, json={'query': query})
yjson = json.loads(r.text)

if r.status_code == 200:
    for article in yjson['data']['pages']['edges']:
        print("Titulo: " +  article['node']['title'])
else:
    print(r.status_code)

``` 
