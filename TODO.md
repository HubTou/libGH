# libGH TODOLIST
Feel free to [submit your own ideas!](https://github.com/HubTou/libgh/discussions).

## Planned evolutions
* Move libpnu2.py code into [HubTou/libpnu](https://github.com/HubTou/libpnu)

## Probable evolutions
* libpnu2/get_url_bdata:
  * Load browser signature from a file at first call
* Fetch:
  * Accounts from:
    * Followers
    * Contributors
    * Stargazers
    * Watchers
  * Repos from:
    * Forks
  * Instructions to do so will be passed with the "complete" parameter.

## Possible evolutions
* Fetch:
  * Accounts from:
    * Following
    * Sponsoring
  * Repos from:
    * Stars
    * Sponsoring
* Add GitHub authenticated mode

## Unprobable evolutions
* A *--all|-a* option to load all repositories individually
  * Not with the rate limits of unauthenticated mode anyway
