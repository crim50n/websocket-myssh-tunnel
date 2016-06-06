# websocket-myssh-tunnel (python3 based)

Union of Shellinabox Frontend and Asyncssh Backend, using WebSocket to build SSH Tunnel, providing more features compared with original Shellinabox.

--------------------------------------------------------

*Features of websocket-myssh-tunnel*:

- Inherit from Shellinabox: UTF-8 Support, Color Terminal, Beep Sound, OnScreen Keyboard, ..
- Tunnel Feature Support: Able to connect an another SSH server 
- Quick Cleaning: Able to detect the abnormally exited session and instantly close the corresponding session resources (Shellinabox will hang running processes for a while when users abnormally quit the session)


*Supported All mainstream browsers*:

-	IE 11 (only beep sound is not supported)
-	Firefox/Iceweasel latest (all supported)
-	Chrome/Chromium latest (all supported)

--------------------------------------------------------

### Getting started on Ubuntu (>=16.04 LTS)

```sh
sudo apt-get install python3-websockets python3-asyncssh
git clone https://github.com/ghostplant/websocket-myssh-tunnel
cd websocket-myssh-tunnel
./dl-wsshd
```

--------------------------------------------------------

### Next, open your browser to get access the terminal

```sh
firefox "https://0.0.0.0:8022/"

[or]

firefox "https://0.0.0.0:8022/?username=user1&hostname=localhost"
```

--------------------------------------------------------

### Deploy Service in Docker

```sh
cd websocket-myssh-tunnel
docker build -t myssh-tunnel .

openssl req -x509 -nodes -days 3650 -subj "/CN=myssh/" -newkey rsa:2048 -keyout cert.pem -out cert.pem
docker run --rm -v `pwd`/cert.pem:/srv/cert.pem -p 8022:8022 myssh-tunnel

[then]

firefox "https://0.0.0.0:8022/?hostname=172.17.0.1"
```

--------------------------------------------------------

docker build -t ssh-tunnel .
### Future work

- extend approach for login using RSAPubKey

Any issues are welcomed to provide.

