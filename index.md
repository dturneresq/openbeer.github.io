---
layout: default
title: Welcome
---

# {{ page.title }}

## What's `beer.db`?

A free open public domain beer database & schema
for use in any (programming) language
(e.g. uses plain text fixtures/data sets).


## Plain Text Fixtures

The `beerdb` command line tool
lets you import beer and brewery data in plain text. Example:

### Breweries

~~~
alaskan, Alaskan Brewing Co., 1986, AK, Juneau | AK 99801-9540 // 5429 Shaune Dr.
brooklyn, Brooklyn Brewery, 1987, NY, Brooklyn | NY 11249 // #1 Brewers Row // 79 N 11th St.
dixie, Dixie Brewing Co., 1907, LA, New Orleans | LA 70119 // 2401 Tulane Ave.
~~~

### Beers

~~~
Alaskan Pale, 5.2%, by:alaskan, golden_ale
Alaskan Amber, 5.3%, by:alaskan,  alt
Alaskan IPA|Alaskan India Pale Ale, 6.2%, by:alaskan, ipa|india_pale_ale
Alaskan Smoked Porter, 6.5%, by:alaskan,  porter

Brooklyn Lager,     5.2%, by:brooklyn, lager|american_amber_lager
Brooklyn Brown Ale, 5.6%, by:brooklyn,  brown_ale|american_brown_ale
Brooklyn East India Pale Ale,  6.9%, by:brooklyn,  ipa|india_pale_ale
Brooklyn Pilsner,  5.1%, by:brooklyn,  pilsner|golden_lager
Brooklyn Black Chocolate Stout,  10.0%, by:brooklyn, imperial_stout
Brooklyn Dry Irish Stout, 4.7%, by:brooklyn, dry_irish_stout
Brooklyn Oktoberfest, 5.5%,    by:brooklyn, maerzen|oktoberfest

Dixie|Dixie Lager, 4.6%, by:dixie, american_lager
Dixie Blackened Voodoo|Dixie Blackened Voodoo Lager,  5.0%, by:dixie,  munich_dunkel|dark_lager
~~~


## Usage

Build yourself a copy of the `beer.db` from the plain text fixtures
in three steps.

Step 1:  Get a copy of the `world.db` fixtures

    $ git clone git://github.com/geraldb/world.db.git

Step 2:  Get a copy of the `beer.db` fixtures

    $ git clone git://github.com/geraldb/beer.db.git

Step 3:  Let's build the `beer.db`

    $ beerdb setup --include ./beer.db --worldinclude ./world.db

That's it.

## Web Admin Demo

Try the `beer.db` Web Admin demo running
on Heroku [`prost.herokuapp.com`](http://prost.herokuapp.com).

![](i/beer_db_admin_screenshoot.png)


## Web Service / HTTP JSON API - `GET /beer/guinness`

Try the `beer.db` HTTP JSON API demo running
on Heroku [`prost.herokuapp.com/api`](http://prost.herokuapp.com/api).

Example:

~~~
GET /beer/guinness

{
  "key":"guinness",
  "title":"Guinness",
  "synonyms": "Guinness Draught",
  "abv":"4.2",
  "srm":null,
  "og":null,
  "tags":["irish_dry_stout","dry_stout","stout"],
  "brewery":
  {
    "key": "guinness",
    "title": "St. James's Gate Brewery / Guinness Brewery"
  },
  "country":
  {
    "key":"ie",
    "title":"Irland"
  }
}
~~~

## Tables, Schema

The `beer.db` includes the following tables:

* beers       (belongs to brewery n brand)          e.g. Guiness Extra Stout
* brands      (has many beers; belongs to brewery)  e.g. Guiness
* breweries   (has many brands n beers)             e.g. St. James's Gate Brewery / Guinness Brewery
* tags                                              e.g. irish_dry_stout, stout
* taggings (join table)

For more see the [`beer.sql`](https://github.com/geraldb/beer.db/blob/master/beer.sql) script.

## Command Line Tool

To build your own `beer.db` copy
use the `beerdb` command line tool.
See the [`beerdb` command line tool project](https://github.com/geraldb/beer.db.ruby)
for more.


## Talks - Slide Decks

- [`beer.db` - Using Open Beer & Brewery Data in Ruby](https://github.com/geraldb/beer.db/blob/master/talks/beer_db_intro.md)


## Real World Usage

- [beer.db.admin](https://github.com/geraldb/beer.db.admin) - `beer.db` Web Admin Tool in Ruby on Rails (version 3.2 and up).


## Alternatives

- [BreweryDB.com](http://www.brewerydb.com) -  beer and brewery data API by PintLabs Inc - (API use only - no database available for download; free demo; $ for use)
- [Open Beer Database (`openbeerdatabase.com`)](http://openbeerdatabase.com)  - free, public beer and brewery data API by Tristan Dunn (work-in-progress; API use only - no database available for download)
- [Open Beer Database (`openbeerdb.com`)](http://openbeerdb.com)  - free, public beer and brewery database (archive, no longer active)

## License

The `beer.db` schema, data and scripts are dedicated to the public domain.
Use it as you please with no restrictions whatsoever.

## Questions? Comments?

Send them along to the [Open Beer & Brewery Database Forum/Mailing List](http://groups.google.com/group/beerdb). Thanks!
