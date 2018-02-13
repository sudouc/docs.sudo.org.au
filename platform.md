# Sudo\Platform[![Build Status](https://travis-ci.org/sudouc/platform.sudo.org.au.svg?branch=master)](https://travis-ci.org/sudouc/platform.sudo.org.au) ![](https://img.shields.io/badge/sudo-medium-yellow.svg)
 
API Platform for all of Sudo's Shinangians 😄


## Installation

### You'll need

To get started, you'll need the following:
* NodeJS
* Docker
* PHP
* Composer [[Windows](https://getcomposer.org/doc/00-intro.md#installation-windows)] [[OSX/Linux/Unix](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx)]

### Steps

1. Clone master `git clone https://github.com/sudouc/platform.sudo.org.au.git`
1. Change directory to platform `cd platform.sudo.org.au`
2. Run `curl -o .env http://goo.gl/FNLQP1 -L`
2. Change directory to the folder and run `composer install`
2. Open Terminal and type `docker-compose up -d` (250mb)
3. Run `php artisan migrate:refresh --seed` to get started with your local DB.
4. Open your browser to `http://localhost:9090`
5. [Optional] Run npm install
6. [Optional] Run npm run watch to live reload the page on code changes


## Let's get down to business...

Poke @sifex for a tutotial on how to make and brake shit



## Current Projects 

- Hummingbird – Sudo's Dashboard Redevelopment
- Pontiyak – API for UniPing
- Flux – Placeholder for MemeEconomy

## Testing

For more info on writing tests, visit https://laravel.com/docs/5.4/testing.

To run unit tests:

```bash
> phpunit
```

For more info on writing browser tests, visit https://laravel.com/docs/5.4/dusk.

To run browser testing:

```bash
> php artisan dusk
```

---

## To Do list


### DevOps

- [x] Docker Compose (Alex)
- [x] Laravel Mix Setup
- [x] TravisCI  

### Development

**Integrations + Cleanup**

- [ ] Steam
- [ ] Keybase
- [ ] GitHub (This one needs to be set to public members)
- [ ] Facebook Group
- [ ] Facebook Page
- [ ] Discord
- [ ] University of Canberra Login System! (Contact Member of AdBoard)

**Dashboard**

- [ ] Easy Integration for those who aren't in the loop
- [ ] Keybase Updates
- [ ] Events
- [ ] Job Board

**API Dock**

- [ ] Sudo Website (Events)
- [ ] Blog Posting Ability
- [ ] Weather API
- [ ] UC's IoT (See Kumudu for Info)
- [ ] Crawler App
- [ ] Live http://sudo.org.au/projects/ update

**Rebuild Induction / Signup**
- [ ] Mutli Society
- [ ] Payment Gateway Info

    
    
    
## Contributing

Contributing should be possible by November 2017. Hold @sifex accountable if this is not the case
