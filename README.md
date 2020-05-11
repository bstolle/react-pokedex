[![forthebadge](https://forthebadge.com/images/badges/built-with-love.svg)](https://forthebadge.com)
![GitHub](https://img.shields.io/github/license/bstolle/react-pokedex?style=for-the-badge)

# Pokédex

A quick site for browsing pokemon and visualizing any pokemon lists.
Great for visualizing data on a living pokedex

## Features

* Browse the list of all Pokémon and find just the Pokémon you want using a plethora of filters
* Make your own custom filter or sorting function if you know javascript
* Import Pokémon from various formats: JSON / CSV / TSV / Smogon / Reddit Markdown Table
* Or even import using javascript, and make use of all the extra possibilities that entails
* Export Pokémon to most of those same formats
* Browse all your Pokémon, or just those in specific tabs
* Edit Pokémon and Pokémon collections
* Pokémons not loaded from external sources are stored in your browser, and will be there when you open up the site again
* Simple display of how complete your collection is
* Automatically calculates breedables based on your Pokémon (although this feature is in need of some love still)
* Link to [a](https://armienn.github.io/pokemon/#Magearna) [specific](https://armienn.github.io/pokemon/#123) [Pokémon](https://armienn.github.io/pokemon/#nidoran-m)
* Link to your collection [in a spreadsheet](https://armienn.github.io/pokemon/?1FOnsr7np65g0RhTETo1gMS298alHhTNwngT_8oYrZvI#2), [a json file](https://armienn.github.io/pokemon/?json:gist.githubusercontent.com/Armienn/dbcc734e78c27eee1c6590f1cd11fd17/raw/e30d8b5a6330d5affbcb3512cd2399ed5603aaee/test-json-pokemons.json), [a script](https://armienn.github.io/pokemon/?script:gist.githubusercontent.com/Armienn/27b4759d86c33542656f255efd1e50af/raw/47e287512645df0a4f75a515d48f9268a7340604/test-pokemons.js) et cetera
* Faster loading than sharing a Google Sheets document

## Recent Updates

* Began adding the Galar region pokemon to the list. (Names and sprites are accruate. Any details are not)
* Fixed the favicon that was not hooked up


## Future Features Wishlist

* Get all pokemon data updated for Galar region pokemon
  * Look for a way to automate the import of pokemon data from a reliable source
* Fix the large pokedex entry images for Galar region pokemon
* Reorganize the left Nav
* Restyle it to look more like an in-game pokedex
* Add links to reliable pokemon resources like **Serebii**, **Smogon**, and **Bulbapedia**
  * Detail page to have links on each type
  * Detail page to have links on each ability
* Add flag sprite to each language entry
* Improve style and usability of search bar 
* sadf ()

## How to Use with Spreadsheets

1. Have a Google Spreadsheet with Pokémon in it
2. Publish it (`File > Publish to the web…`)
3. Add your spreadsheet id to the end of this link: `https://armienn.github.io/pokemon/?spreadsheet-id`

Example: [`https://armienn.github.io/pokemon/?1FOnsr7np65g0RhTETo1gMS298alHhTNwngT_8oYrZvI`](https://armienn.github.io/pokemon/?1FOnsr7np65g0RhTETo1gMS298alHhTNwngT_8oYrZvI)

Don't have a sheet? Copy [this template spreadsheet](https://docs.google.com/spreadsheets/d/1mhDDWpfizdO1AitOMzAxODRQYNlHQAkpRRqBauzn4cI/edit?usp=sharing) and start filling in your data.

For the best experience your spreadsheets first tab should look somewhat like in [the template spreadsheet](https://docs.google.com/spreadsheets/d/1mhDDWpfizdO1AitOMzAxODRQYNlHQAkpRRqBauzn4cI/edit?usp=sharing). This spreadsheet also contains a template worksheet with all the supported columns.

The script tries a few different column names for every piece of Pokémon information, so the columns don't need to have the same exact headers. E.g. both "ATK IV" and "IV Attack" will work for the Pokémon's attack IV. Pokéballs in particular can both be defined in a column called "Pokéball" where the name of the ball is written, or in a series of columns each named with the name of a Pokéball (See the difference between the TEMPLATE and EXAMPLE worksheets in the template sheet (the Pokéball columns are hidden to the far right in the EXAMPLE sheet)).

Most columns can be deleted. Even a sheet as simple as [this](https://docs.google.com/spreadsheets/d/1Co8N7zAWXhPnKHTUOdPbLunalSDoGyDVoftpvV0IxDY/edit?usp=sharing) will work: [See?](https://armienn.github.io/pokemon/?1Co8N7zAWXhPnKHTUOdPbLunalSDoGyDVoftpvV0IxDY#1)

Worksheets named "db" or whose name contains "template", "item", "config", "resource" or "database" won't be shown, and sheets whose name start with "lf" or "looking for" will appear on their own in the list of tabs and the Pokémon in them won't be added to the list of all your Pokémon.





## Settings
[Edit on StackBlitz ⚡️](https://stackblitz.com/edit/react-ue3hjh)

By having settings in your spreadsheet as seen in the template spreadsheet, it is possible enable the auto breedables list, and to choose the colour scheme to use (either Night, Day or Custom).

## Other notes

For developers interested in the code: I cleaned up the code at one point, but then I started spitting out features again. It's so so. However, here are some parts that might be of interest:

* `stuff.data` contains information about pokemons, moves, types, eggGroups etc.
* `new Pokemon(args)` will create a new Pokémon object. `args` can be the name of a Pokémon, or an object containing at least `name` or `id` and optionally `form`.
* `stuff.collection` houses `pokemons`, `lookingFor` and `local`. These are all lists of tabs (`{title:string, id:string, pokemons:Pokemon[]}`). The first two are filled when loading from a spreadsheet, and the last one contain the Pokémons which are stored using the Web Storage API. Add tabs with `AddTab()`, `AddLookingForTab()` and `AddLocalTab()`, and save the current state of the local tabs with `SaveLocalTabs()`
* `stuff.optionsSection` has `importMethods` and `exportMethods`
* `stuff.headerSection` has `filters` and `sorts`
* `stuff.listSection` has `basePokemonColumns` and `tabPokemonColumns`, which are used to set up the main list of Pokémon
* `stuff.settings` has `colorSchemes`

This project also provides various Pokémon data in json format, found in data-sumo/pokemons.json, data-sumo/moves.json, data-sumo/abilities.json, data-sumo/natures.json, data-sumo/types.json and data-sumo/egg-groups.json. There's no guarantee about correctness or updatedness, and no documentation, but it's there for those who want it.


## Authors

* **Armienn** - authored a similar project that inspired me (I have since abanded his forked code for a more "from scratch" model)
* **Benjamin Stolle** - Picked up to enhance the original
* **Jessica Lord** - wrote the foundational code using the sheets reader. Gives a big leg up on importing data the way most pokemon traders store it now.


## Acknowledgments

* Thanks to [richi3f](https://github.com/richi3f) for the inspiration for this site, and for the initial template spreadsheet.
* VS Code was used to update this codebase (bstolle's contributions)

## License

This project is licensed under the BSD 3-Clause - see the [LICENSE.md](LICENSE.md) file for details

Pokémon &copy; Nintendo / Game Freak, 1995-2017.


### Fork -n- Go!

Here's a fun fact:

GitHub gives free hosting for every repository (see [GitHub Pages](http://pages.github.com)). 

This repo only has a **gh-pages** branch, the branch GitHub hosts, which means as soon as you **fork** it, you have a hosted and live version of it yourself! Read more about [fork-n-go](http://jlord.github.io/forkngo) type of projects.

Next, create a spreadsheet with the same column headers as [the original](https://docs.google.com/a/github.com/spreadsheets/d/1hnfQcggYcBYimuO_UOMvwoOi_I9vUvFpkMt4wjrrpLE/edit#gid=0).

Click on the `index.html` file, click edit and change **line 118** (or thereabouts) it looks like: 

```javascript
    document.addEventListener('DOMContentLoaded', function() {
	  	var gData
	  	var URL = "0Ao5u1U6KYND7dFVkcnJRNUtHWUNKamxoRGg4ZzNiT3c"
			Tabletop.init( { key: URL, callback: showInfo, simpleSheet: true } ) 
    }) 
```

Replace the existing spreadsheet URL key with your spreadsheet's key. You'll find that by clicking (in Google Spreadsheets) File > Publish to the Web > Start Publishing, it will then display the key in a window. ![get key](https://raw.github.com/jllord/sheetsee-cache/master/img/key.png)

Commit those changes and **LIKE WOAH** you now have a version of this website hooked to a spreadsheet that you can distrubute however you'd like.

You can find your version at **yourGitHubName.github.io/theReposName** (in this case /hack-spots).

## But How?

A Google Spreadsheet holds all the data and it is connected to this website using the goodies in [sheetsee.js](http://www.github.com/jlord/sheetsee.js). Everytime you visit the website, you'll have the most up to date data that has been entered into the spreadsheet. 

