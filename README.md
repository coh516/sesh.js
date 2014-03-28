# sesh.js HTTP server micro framework. 

This was forked from the original Session.js and re-built for the DMT POET project as a http micro-framework. It adds a singleton init function and connects it to a port.  This allows a simpler method of dealing with the request/response callbacks and post/get pseudo-events while providing sessioning.  I'm publishing this standalone fork in case anyone has any interest.

## Installation

### Installing session.js
  copy into modules_modules/sesh or use npm's git functioanility or just do the standard git checkout method

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


#### Simplified connection with main init function (automatically patches httpServer)

    var http = require('http'),
        session = require('sesh')
        
        session.magicSession(main, 6789); // create a main and associate it to port 6789
<pre>
function main() { 

	if (this.get) { 
		console.log(this.request, this.response);
	}
	if (this.post) {
		console.log(this.request, this.response);
		this.spit("hello to client"); // writes as text/plain .. some more twkin needed for other types
	}
	console.log(this.request.session);
	console.log(this.request.sessionRoot);
}
</pre>
 



