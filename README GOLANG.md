Go Installation

(revisited from https://www.digitalocean.com/community/tutorials/how-to-install-go-1-7-on-debian-8)

1. Download go:
	curl -O https://storage.googleapis.com/golang/go1.8.linux-amd64.tar.gz

2. Extract tar
	tar xvf go1.8.linux-amd64.tar.gz

3. Give right user permission (if you NEED different!)
	sudo chown -R <ec2-user>:<ec2-user> ./go

4. Move go wherever you want:
	mv go <new_path>

5. Set ~/.profile exports:
	sudo nano ~./profile

		export GOROOT=<new_path>/go
		export GOPATH=/mnt/data/gowork #working directory (I suggest <new_path>/gowork)
		export PATH=$PATH:$GOROOT/bin:$GOPATH/bin






GO USAGE:

//prepare db file:
mkdir /mnt/data/gowork/safebrowsing
touch /mnt/data/gowork/safebrowsing/db
go get github.com/rebrandly/google-safe-browsing/cmd/sbserver

APIKEY=AIzaSyApXjU6_9gl2kWAb1D12AYn496VNtwHHGE
SERVICEADDRESS=0.0.0.0
PORT=5346
DB=/mnt/data/gowork/safebrowsing/db

sbserver -apikey $APIKEY -srvaddr $SERVICEADDRESS:$PORT -db $DB

//to run in background
nohup sbserver -apikey $APIKEY -srvaddr $SERVICEADDRESS:$PORT -db $DB &

//to kill:
ps
kill












PORT=8070 NODE_ENV=development node start app.js



