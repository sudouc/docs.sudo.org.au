# Sudo\Nico 

## Installation

To get started, you'll need the following:
* **NodeJS** [[Windows](https://nodejs.org/dist/v8.12.0/node-v8.12.0-x86.msi), [Mac](https://nodejs.org/dist/v8.12.0/node-v8.12.0.pkg)]
* **Git** [[Windows](https://github.com/git-for-windows/git/releases/download/v2.19.0.windows.1/Git-2.19.0-32-bit.exe), [Mac](https://sourceforge.net/projects/git-osx-installer/files/git-2.18.0-intel-universal-mavericks.dmg/download?use_mirror=autoselect)]

### Getting Started

1. Open CMD / Terminal, clone the nico-client repo: `git clone https://github.com/sudouc/nico-client.git`
1. Change directory to nico-client `cd nico-client`
2. Run `npm install`
2. Run `npm run start`
2. Open in your favourite editor.

If you've already cloned the repo, cd into it and run `git pull`. That'll fetch the most up to date version from Github. (If it doesn't comply, use `git pull --force`)

## Week 1

### Breaking down the client

We had a look at how the client operates, and how we interface with the server. Firstly we import our "client", "Player" and "World" objects. 


```js
import { client, World, Player } from './index';
import repl from "repl";
```

We then specify which server we're dealing with. For our default, we have our Nico Server open at https://nico.sudo.org.au.

```js
client.setup('https://nico.sudo.org.au')
```

This is followed by specifying which service we want to interface with.

!> Note: We can also go to  https://nico.sudo.org.au/players to access the current world state.

### Callbacks

Callbacks are functions we pass to an operation that the operation can call any time the operation comes across an event.

In better terms, we can assign callbacks to the world whenever the server updates by using the `world.onUpdate(fn)` method; like so:

```js
world.onUpdate((message) => {
	// Do something when the server updates
	console.log(message)
});
```

### Promises

Promises are essentially callbacks, but are expressed differently, and complete different tasks. 

For operations that may take a while (like fetching the current world state from a server), we don't want to hold up our main script with waiting for this servers response, so we give the promise something to do once we get given a response. We can achieve this with the `then`, `catch` and `finally` functions.

 ```js
 
// Example
world.context.fetch().then(function(response) { 
	// Do something when the server responds
	console.log(response)
})

// Example
player.moveUp().then((response) => {
	console.log('Server has recieved the player moving up')
})
```

### Creating a player in this world

We now create a new instance of a "Player" object, and give the player some sort of background about which world it exists in. This is useful when we call `player.moveUp()` to actually talk to the server.

We then follow this up with setting the player ID – before we talk to the server.

```js
// Create a new player object
const player = new Player();
// Give the playe object a world to interface with (creates event binding)
player.addToWorld(world)

// Set our player ID
const playerID = '';
player.setPlayerID(playerID);
```

Right now, our player only exists on our computer, and thus we need to sync it to the server. The following essentially achieves the following:

1. Calling `player.existsInWorld` asks the server if we exist. We don't want to hold up the server, so `player.existsInWorld` returns a Promise.
1. Once the exists comes back, we call `player.createInWorld()` if exists is false.


 ```js
player.existsInWorld().then(exists => {
	exists ? '' : player.createInWorld()
})
```

### Moving

Moving is a simple as doing the following.

```js
player.moveUp()
```

## Week 2

In week 2, we've got a couple of things to accomplish. Don't worry if it's daunting, should be pretty straightforward.

Git Clone: `https://github.com/sudouc/nico-player.git`
