---
title:      "GMaps info app"
---
### App to search on Google Maps.
[Github link](https://github.com/exced/GMapsInfo)

A simple app built with Electron & Angular.

It uses Google Maps API and gives you specific information about the location when you click on the map.
The description comes from DBpedia.

## Search
1. You can do 'normal search' by clicking on the map or by searching a location by address.
2. You can do 'advanced search' (a tab stands for it) and search for every __'class'__ around a specific point.

The __'classes'__ are from DBpedia ontology and are updated at each time you run the app. 
There is a [list](http://mappings.dbpedia.org/server/ontology/classes/#Place).

For instance you can do search like : __10 museums around Paris within 0.5 area.__
It requests the wikipedia database to get 10 museums around Paris, and gives the wikipedia description
of it when you click.

I have only used geolocation and reverse geolocation from GMAPS API : returns cityname from lat et lng &
returns lat, lng when clicking on Maps.
You don't have to use geocoding. You can search for City name from DBPedia with only lat & lng but it does not
work well (it gives you a lot of city around the point).
