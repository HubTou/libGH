# libGH TODOLIST
Feel free to [submit your own ideas!](https://github.com/HubTou/libgh/discussions).

## Planned evolutions
* Move libpnu2.py code into [HubTou/libpnu](https://github.com/HubTou/libpnu)

## Probable evolutions
* Fetch:
  * Accounts from:
    * Followers
    * Contributors
    * Stargazers
    * Watchers
  * Repos from:
    * Forks
  * Instructions to do so will be passed with the "complete" parameter.
* libpnu2/get_url_bdata:
  * Load browser signature from a file at first call

## Possible evolutions
* Fetch:
  * Accounts from:
    * Following
    * Sponsoring
  * Repos from:
    * Stars
    * Sponsoring
* Add GitHub authenticated mode
* libpnu2/get_url_bdata:
  * Always create an index.txt file for the cache
  * Replace the *cache_index* parameter by a *private* parameter
    indicating if source URL are to be mentioned
  * Write a cache expiration number of days in each line
  * Make the *cache_days* parameter optional in *prune_cache()*
    using the previous cache expiration number of days by default

## Unprobable evolutions
* A *--all|-a* option to load all repositories individually
  * Not with the rate limits of unauthenticated mode anyway
