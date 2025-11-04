___
### Input:
```
import requests

x = requests.get('http://httpbin.org/get')

print(x.headers)
print(x.headers['Server'])
print(x.status_code)

if x.status_code == 200:
	print("Success!")
elif x.status_code == 400:
	print("Not found!")
elif x.status_code == 503:
	print("Temperory unavailable")

print(x.elapsed)
print(x.cookies)

x = requests.get('http://httpbin.org/get', params={'id':'1'})
print(x.url)

x = requests.get('http://httpbin.org/get', params={'id':'2'}, headers={'Accept':'application/json', 'test_header':'test'})
print(x.text)

x = requests.delete('http://httpbin.org/delete')
print(x.text)

x = requests.post('http://httpbin.org/post', data={'a':'b'})
print(x.text)

x = requests.get('http://httpbin.org/get', auth=('username','password'))
print(x.text)

```

### Output:
```
$ python3 Requests.py
{'Date': 'Tue, 04 Nov 2025 16:53:36 GMT', 'Content-Type': 'application/json', 'Content-Length': '316', 'Connection': 'keep-alive', 'Server': 'gunicorn/19.9.0', 'Access-Control-Allow-Origin': '*', 'Access-Control-Allow-Credentials': 'true'}
gunicorn/19.9.0
200
Success!
0:00:01.725273
<RequestsCookieJar[]>
http://httpbin.org/get?id=1
{
  "args": {
    "id": "2"
  }, 
  "headers": {
    "Accept": "application/json", 
    "Accept-Encoding": "gzip, deflate, br, zstd", 
    "Host": "httpbin.org", 
    "Test-Header": "test", 
    "User-Agent": "python-requests/2.32.5", 
    "X-Amzn-Trace-Id": "Root=1-690a2fa5-4041fd5c3d9bec6f3c6743b7"
  }, 
  "origin": "152.58.34.108", 
  "url": "http://httpbin.org/get?id=2"
}

{
  "args": {}, 
  "data": "", 
  "files": {}, 
  "form": {}, 
  "headers": {
    "Accept": "*/*", 
    "Accept-Encoding": "gzip, deflate, br, zstd", 
    "Content-Length": "0", 
    "Host": "httpbin.org", 
    "User-Agent": "python-requests/2.32.5", 
    "X-Amzn-Trace-Id": "Root=1-690a2fa6-5a1fc4ae3c08891f536866dd"
  }, 
  "json": null, 
  "origin": "152.58.34.108", 
  "url": "http://httpbin.org/delete"
}

{
  "args": {}, 
  "data": "", 
  "files": {}, 
  "form": {
    "a": "b"
  }, 
  "headers": {
    "Accept": "*/*", 
    "Accept-Encoding": "gzip, deflate, br, zstd", 
    "Content-Length": "3", 
    "Content-Type": "application/x-www-form-urlencoded", 
    "Host": "httpbin.org", 
    "User-Agent": "python-requests/2.32.5", 
    "X-Amzn-Trace-Id": "Root=1-690a2fc0-18a6f9780308eefd0113e6d1"
  }, 
  "json": null, 
  "origin": "152.58.34.108", 
  "url": "http://httpbin.org/post"
}

{
  "args": {}, 
  "headers": {
    "Accept": "*/*", 
    "Accept-Encoding": "gzip, deflate, br, zstd", 
    "Authorization": "Basic dXNlcm5hbWU6cGFzc3dvcmQ=", 
    "Host": "httpbin.org", 
    "User-Agent": "python-requests/2.32.5", 
    "X-Amzn-Trace-Id": "Root=1-690a2fc2-2dbbfafa1230c2d8538ccc34"
  }, 
  "origin": "152.58.34.108", 
  "url": "http://httpbin.org/get"
}

```
