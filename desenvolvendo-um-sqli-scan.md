---
description: Scam SQL Injection em python.
---

# Desenvolvendo um SQLi Scan

<mark style="color:blue;">import</mark> copy&#x20;

<mark style="color:blue;">import</mark> sys&#x20;

from urllib <mark style="color:blue;">import</mark> parse

<mark style="color:blue;">import</mark> requests

def request(url):&#x20;

&#x20;      headers = {"User-Agent":&#x20;

&#x20;                             "Mozilla/5.0 (X11; Linux x86\_64; rv:78.0) Gecko/[20100101 ](#user-content-fn-1)[^1]Firefox/78.0"}&#x20;

try:

&#x20;       response = requests.get(url, headers=headers)&#x20;

&#x20;       html = response.text

&#x20;       return html&#x20;

&#x20;       except:&#x20;

&#x20;             pass

def is\_vulnerable(html):&#x20;

&#x20;       errors = \["mysql\_fetch\_array()",

&#x20;                         "You have an error in your SQL syntax"]&#x20;

&#x20;        for error in errors:&#x20;

&#x20;        if error in html:&#x20;

&#x20;        return True

if  [**name**](#user-content-fn-2)[^2]  == "[**main**](#user-content-fn-3)[^3]":&#x20;

&#x20;     url = sys.argv\[1]

&#x20;     url\_parsed = parse.urlsplit(url)

&#x20;     params = parse.parse\_qs(url\_parsed.query)

&#x20;     for param in params.keys():&#x20;

&#x20;     query = copy.deepcopy(params)

&#x20;     for c in "'\\"':&#x20;

&#x20;    query\[param]\[0] = c&#x20;

&#x20;    new\_params = parse.urlencode(query, doseq=True)

&#x20;    url\_final = url\_parsed.\_replace(query=new\_params)

&#x20;    url\_final = url\_final.geturl()

&#x20;    html = request(url\_final)&#x20;

&#x20;    if html:

&#x20;    if is\_vulnerable(html):&#x20;

&#x20;    print("\[ + ] {} parameter is vulnerable".format(param))&#x20;

&#x20;    quit()

&#x20;   print("NOT VULNERABLE")

```python
```

[^1]: 

[^2]: antes de depois do name colocar "\_"

[^3]: antes e depois do main, colocar "\_"
