# Aquire & Analyze

Will, Matt, Marcus

# Description 

A minimalist wrapper for searching public reddit comments/submissions via the pushshift.io API.

Pushshift is an extremely useful resource, but the API is poorly documented. As such, this API wrapper is currently designed to make it easy to pass pretty much any search parameter the user wants to try.

Although it is not necessarily reflective of the current status of the API, you should attempt to familiarize yourself with the Pushshift API documentation to better understand what search arguments are likely to work.

Features Handles rate limiting and exponential backoff subject to maximum retries and maximum backoff limits. A minimum rate limit of 1 request per second is used as a default per consultation with Pushshift’s maintainer, /u/Stuck_in_the_matrix.

Handles paging of results. Returns all historical results for a given query by default.

Optionally handles incorporation of praw to fetch objects after getting ids from pushshift If not using praw, returns results in comment and submission objects whose API is similar to the corresponding praw objects. Additionally, result objects have an additional .d_ attribute that offers dict access to the associated data attributes.

Optionally adds a created attribute which converts a comment/submission’s created_utc timestamp to the user’s local time. (may raise exceptions for users with certain timezone settings).

Simple interface to pass query arguments to the API. The API is sparsely documented, so it’s often fruitful to just try an argument and see if it works.

A stop_condition argument to make it simple to stop yielding results given arbitrary user-defined criteria Commandline interface (CLI) for simplified usage outside of python environment.

# Purpose

The purpose of this aquire and analyze is to aquire two sets of text from comment sections, one coming from the Subreddit r/Gaming searching for keyword IGN and the other coming from r/IGN searching for keyword gaming. This invers of search was the bases for our analysis to see what patterns of text will be found.
