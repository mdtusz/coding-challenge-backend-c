# Busbud Coding Challenge

A simple challenge Busbud had me do.

## Requirements

Design an API endpoint that provides auto-complete suggestions for large cities.
The suggestions should be restricted to cities in the USA and Canada with a population above 5000 people.

## Demo

Check it out [here](https://busbud.herokuapp.com/suggestions?q=van&latitude=49.123&longitude=-123.45). The first time you visit, it will likely be atrociously slow because free Heroku instances stop running after a short period of time, but if you search for something else or change the parameters, you should find results come faster and faster. The fastest I've witnessed has been 1ms, but it will depend what you're searching for (because of the in memory store) and also is dependent on Heroku (dem free instances aren't super quick).

I simply stored the cities in-memory because it's static data, and using elastic-search for a coding challenge seemed like overkill. The string similarity is found using the Levenshtein edit distance, and the Haversine forumula is found to order the distances if a latitude and longitude are provided.
