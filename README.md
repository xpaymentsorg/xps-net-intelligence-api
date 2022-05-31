# xps-net-intelligence-api
xPayments API Status.

## Prerequisite
* gpay
* node
* npm
* pm2

## Installation
Make sure you have node.js and npm installed.

Clone the repository and install the dependencies

```bash
git clone https://github.com/xpaymentsorg/xps-net-intelligence-api
cd xps-net-intelligence-api
npm install
```

Install pm2 with npm

```bash
sudo npm install -g pm2
```

## Configuration

Configure the app modifying [app.json](/xps-net-intelligence-api/blob/master/app.json.example). Note that you have to rename the file app.json.example to app.json.

```json
"env":
	{
		"NODE_ENV"        : "production", // tell the client we're in production environment
		"RPC_HOST"        : "localhost", // eth JSON-RPC host
		"RPC_PORT"        : "8550", // xps JSON-RPC port
		"LISTENING_PORT"  : "30350", // xps listening port (only used for display)
		"INSTANCE_NAME"   : "node1", // whatever you wish to name your node
		"CONTACT_DETAILS" : "", // add your contact details here if you wish (email/skype)
		"WS_SERVER"       : "wss://rpc.xps.network", // path to eth-netstats WebSockets api server
		"WS_SECRET"       : "mysecret", // WebSockets api server secret used for login
		"VERBOSITY"       : 2 // Set the verbosity (0 = silent, 1 = error, warn, 2 = error, warn, info, success, 3 = all logs)
	}
```

## Run

Run it using pm2:

```bash
pm2 start app.json
```

## Logs

View the logs with pm2:

```bash
pm2 logs 0
```

It is a fork of eth-net-intelligence-api.<br>
Official eth-net-intelligence-api Repository: https://github.com/cubedro/eth-net-intelligence-api<br>
