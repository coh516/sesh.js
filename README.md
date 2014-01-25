# sesh.js - super simple session management for node.js with main connection listener instantializer

this was forked and re-built for the DMT POET project. It ads a main() and connects it to a port.  This allows
a simpler method of dealing with the request/response callbacks while proviing sessioning.
In my DMT POET system, i call the lib sesh.  I'm just publishing this standalone.. 

## Installation

### Installing npm (node package manager)
<pre>
  ~~curl http://npmjs.org/install.sh | sh~~

</pre>

### Installing session.js
<pre>
  ~~npm install sesh~~
  use standard git installation
</pre>

### Example request.session

    {
        "id": "m2ENokSCHY3",
        "data": {
            "history": [
                "/"
            ],
            "user": "Guest"
        },
        "path": "/",
        "persistent": true,
        "lifetime": 604800,
        "expiration": 1291446379596
    }


### Usage

#### the package was changed to create a main function that parses out get and push requests and instantializes the main with response/reqeusts

	


#### Magic Monkey Punched Middle-ware Sessions (automatically patches httpServer)

    var http = require('http'),
        session = require('./lib/core').magicSession(main, 6789); // create a main and associate it to port 6789

   function main() { 

	if (this.get) { 
		console.log(this.request, this.response);
	}
	if (this.post) {
		console.log(this.request, this.response);
	}
}
 


# Authors

     inimino@inimino.org, Marak Squires
     coh516@gmail.com, Seth Tenenbaum

