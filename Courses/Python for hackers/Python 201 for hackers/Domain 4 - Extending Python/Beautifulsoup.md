___
- Beautifulsoup is a powerful web scraping tool which can be used with python.
- Right now we are going to scrap the data from the web page 246ctf.com

```
import requests 
page = requests.get("https://247ctf.com/scoreboard")
#print(page.text)

from bs4 import BeautifulSoup
soup = BeautifulSoup(page.content, 'html.parser')
#print(soup.text)

print(soup.title)
print(soup.title.name)
print(soup.title.string)

print(soup.find("a"))

for line in soup.find_all("a"):
    print(line)
    print(line.get('href'))

print(soup.find(id="fetch-error"))
print(soup.find(class_="nav-link"))
print(soup.find("a", class_="nav-link"))

table = soup.find("table")
#print(table)
table_body = table.find("tbody")
rows = table_body.find_all("tr")

for row in rows:
    print("---")
    #print(row)
    cols = [x.text.strip() for x in row.find_all("td")]
    #print(cols)
    print("{} is in {} place with {}".format(cols[2], cols[0], cols[4]))
```

- The scraped data looks like this: 

```
J:\Python 201 for Hackers>python Beautifulsoup.py
<title>247CTF - Scoreboard</title>
title
247CTF - Scoreboard
<a class="nav-link" href="/dashboard"><span class="align">Dashboard</span></a>
<a class="nav-link" href="/dashboard"><span class="align">Dashboard</span></a>
/dashboard
<a class="nav-link active rounded" href="/scoreboard"><span class="align">Scoreboard</span></a>
/scoreboard
<a class="nav-link" href="/activity"><span class="align">Activity</span></a>
/activity
<a class="nav-link" href="/about"><span class="align">About</span></a>
/about
<a class="nav-link rounded" data-target="#loginModal" data-toggle="modal" href="#"><span class="align">Login</span></a>
#
<a class="nav-link rounded unauth" data-target="#joinModal" data-toggle="modal" href="#"><span class="align">Join</span></a>
#
<a class="btn btn-default mr-1" href="/scoreboard"><span class="align">All time</span></a>
/scoreboard
<a class="btn btn-default mr-1" href="/scoreboard/monthly"><span class="align">This month</span></a>
/scoreboard/monthly
<a href="/progress/pottm">pottm</a>
/progress/pottm
<a href="/progress/jusb3">jusb3</a>
/progress/jusb3
<a href="/progress/Nemo">Nemo</a>
/progress/Nemo
<a href="/progress/Superior">Superior</a>
/progress/Superior
<a href="/progress/Malekith">Malekith</a>
/progress/Malekith
<a href="/progress/Huobase">Huobase</a>
/progress/Huobase
<a href="/progress/Peace-Maker">Peace-Maker</a>
/progress/Peace-Maker
<a href="/progress/AACDAI">AACDAI</a>
/progress/AACDAI
<a href="/progress/kkapitan">kkapitan</a>
/progress/kkapitan
<a href="/progress/practicaltacocat">practicaltacocat</a>
/progress/practicaltacocat
<a href="/progress/36AL9TyHTfH9">36AL9TyHTfH9</a>
/progress/36AL9TyHTfH9
<a href="/progress/taytantos">taytantos</a>
/progress/taytantos
<a href="/progress/blablub">blablub</a>
/progress/blablub
<a href="/progress/nyz">nyz</a>
/progress/nyz
<a href="/progress/IBSONE2017">IBSONE2017</a>
/progress/IBSONE2017
<a href="/progress/AhnMo">AhnMo</a>
/progress/AhnMo
<a href="/progress/doublesix">doublesix</a>
/progress/doublesix
<a href="/progress/SpaceCheetah">SpaceCheetah</a>
/progress/SpaceCheetah
<a href="/progress/rayaserien">rayaserien</a>
/progress/rayaserien
<a href="/progress/RubiyaLab">RubiyaLab</a>
/progress/RubiyaLab
<a href="/progress/HoneyScammer">HoneyScammer</a>
/progress/HoneyScammer
<a href="/progress/Robin_Jadoul">Robin_Jadoul</a>
/progress/Robin_Jadoul
<a href="/progress/_Sin">_Sin</a>
/progress/_Sin
<a href="/progress/knifeyspoony">knifeyspoony</a>
/progress/knifeyspoony
<a href="/progress/sirl1on">sirl1on</a>
/progress/sirl1on
<a href="/progress/wekito">wekito</a>
/progress/wekito
<a href="/progress/V1NC1D4">V1NC1D4</a>
/progress/V1NC1D4
<a href="/progress/x3ric">x3ric</a>
/progress/x3ric
<a href="/progress/f5">f5</a>
/progress/f5
<a href="/progress/Jinx">Jinx</a>
/progress/Jinx
<a href="/progress/Nattt">Nattt</a>
/progress/Nattt
<a href="/progress/ytbjplh">ytbjplh</a>
/progress/ytbjplh
<a href="/progress/elklepo">elklepo</a>
/progress/elklepo
<a href="/progress/sisyang">sisyang</a>
/progress/sisyang
<a href="/progress/rcimatti">rcimatti</a>
/progress/rcimatti
<a href="/progress/b4d">b4d</a>
/progress/b4d
<a href="/progress/slak">slak</a>
/progress/slak
<a href="/progress/ciphr">ciphr</a>
/progress/ciphr
<a href="/progress/dxer">dxer</a>
/progress/dxer
<a href="/progress/benito255">benito255</a>
/progress/benito255
<a href="/progress/UZengin">UZengin</a>
/progress/UZengin
<a href="/progress/reductor">reductor</a>
/progress/reductor
<a href="/progress/kernelpanic">kernelpanic</a>
/progress/kernelpanic
<a href="/progress/kurokaze">kurokaze</a>
/progress/kurokaze
<a href="/progress/plaxer">plaxer</a>
/progress/plaxer
<a href="/progress/alsacchi">alsacchi</a>
/progress/alsacchi
<a href="/progress/Arkanor">Arkanor</a>
/progress/Arkanor
<a href="/progress/nick0ve">nick0ve</a>
/progress/nick0ve
<a href="/progress/TheAwoo">TheAwoo</a>
/progress/TheAwoo
<a href="/progress/poiko">poiko</a>
/progress/poiko
<a href="#" id="forgot-link">Forgot your password?</a>
#
<a class="pb-3" href="/privacy" id="privacy">By registering, you agree to our privacy policy</a>
/privacy
<div class="container none" id="fetch-error">
<div class="rounded text-center p-2 mt-3 sitewide">
<span class="align">Error during challenge fetch. Please reload or use an alternative browser.</span>
</div>
</div>
<a class="nav-link" href="/dashboard"><span class="align">Dashboard</span></a>
<a class="nav-link" href="/dashboard"><span class="align">Dashboard</span></a>
---
pottm is in 1st place with 13,525 pts
---
jusb3 is in 2nd place with 13,525 pts
---
Nemo is in 3rd place with 13,525 pts
---
Superior is in 4th place with 13,525 pts
---
Malekith is in 5th place with 13,525 pts
---
Huobase is in 6th place with 13,525 pts
---
Peace-Maker is in 7th place with 13,245 pts
---
AACDAI is in 8th place with 13,190 pts
---
kkapitan is in 9th place with 13,010 pts
---
practicaltacocat is in 10th place with 12,910 pts
---
36AL9TyHTfH9 is in 11th place with 12,880 pts
---
taytantos is in 12th place with 12,725 pts
---
blablub is in 13th place with 12,645 pts
---
nyz is in 14th place with 12,070 pts
---
IBSONE2017 is in 15th place with 11,985 pts
---
AhnMo is in 16th place with 11,905 pts
---
doublesix is in 17th place with 11,885 pts
---
SpaceCheetah is in 18th place with 11,530 pts
---
rayaserien is in 19th place with 11,390 pts
---
RubiyaLab is in 20th place with 11,215 pts
---
HoneyScammer is in 21st place with 10,755 pts
---
Robin_Jadoul is in 22nd place with 10,745 pts
---
_Sin is in 23rd place with 10,690 pts
---
knifeyspoony is in 24th place with 10,670 pts
---
sirl1on is in 25th place with 10,505 pts
---
wekito is in 26th place with 10,380 pts
---
V1NC1D4 is in 27th place with 10,330 pts
---
x3ric is in 28th place with 10,330 pts
---
f5 is in 29th place with 10,300 pts
---
Jinx is in 30th place with 10,255 pts
---
Nattt is in 31st place with 10,250 pts
---
ytbjplh is in 32nd place with 10,140 pts
---
elklepo is in 33rd place with 10,130 pts
---
sisyang is in 34th place with 10,125 pts
---
rcimatti is in 35th place with 10,045 pts
---
b4d is in 36th place with 10,000 pts
---
slak is in 37th place with 9,930 pts
---
ciphr is in 38th place with 9,890 pts
---
dxer is in 39th place with 9,855 pts
---
benito255 is in 40th place with 9,475 pts
---
UZengin is in 41st place with 9,385 pts
---
reductor is in 42nd place with 9,165 pts
---
kernelpanic is in 43rd place with 9,130 pts
---
kurokaze is in 44th place with 9,015 pts
---
plaxer is in 45th place with 8,945 pts
---
alsacchi is in 46th place with 8,915 pts
---
Arkanor is in 47th place with 8,880 pts
---
nick0ve is in 48th place with 8,695 pts
---
TheAwoo is in 49th place with 8,590 pts
---
poiko is in 50th place with 8,485 pts
```

