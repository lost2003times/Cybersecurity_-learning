___
### Input

```
import pickle

hackers =  {"neut": 1, "geohot": 100, "neo": 1000}
for key, value in hackers.items():
    print(key,value)

serialised = pickle.dumps(hackers)
print(serialised)

hackers_v2 = pickle.loads(serialised)
print(hackers_v2)

for key, value in hackers_v2.items():
    print(key,value)
```

### Output
```
J:\Python 201 for Hackers>python Serialization.py
neut 1
geohot 100
neo 1000
b'\x80\x04\x95"\x00\x00\x00\x00\x00\x00\x00}\x94(\x8c\x04neut\x94K\x01\x8c\x06geohot\x94Kd\x8c\x03neo\x94M\xe8\x03u.'
{'neut': 1, 'geohot': 100, 'neo': 1000}
neut 1
geohot 100
neo 1000
```

