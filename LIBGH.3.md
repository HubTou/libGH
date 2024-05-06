# libGH(3)

## NAME
libgh - GitHub scraping library

## SYNOPSIS
import **libgh**

Dict *libgh*.**load_account**(String account_name, Integer cache_days, Boolean force_fetch=False, List complete=[])

Dict *libgh*.**load_accounts**(List accounts_list, Integer cache_days, Boolean force_fetch=False, List complete=[])

Dict *libgh*.**load_repository**(String account_name, String repository_name, Integer cache_days, Boolean force_fetch=False)

Dict *libgh*.**load_repositories**(List repositories_list, Integer cache_days, Boolean force_fetch=False)

The following functions will be moved into the **libpnu** library in a future version:

Bytes, ListOfTuples *libgh*.**get_url_bdata**(String url, String cache_dir, Dict headers={}, Integer cache_days=1, Boolean cache_index=False, Boolean force_fetch=False, Integer min_delay=0, Integer max_per_minute=-1, Integer max_per_hour=-1, Integer max_per_day=-1, Integer timeout=15)

String, ListOfTuples *libgh*.**get_url_data**(String url, String cache_dir, Dict headers={}, Integer cache_days=1, Boolean cache_index=False, Boolean force_fetch=False, Integer min_delay=0, Integer max_per_minute=-1, Integer max_per_hour=-1, Integer max_per_day=-1, Integer timeout=15)

Void *libgh*.**prune_cache**(String cache_dir, Integer cache_days)

List *libgh*.**collection2xml**(Collection data, String name="root", Integer depth=0, Integer indent_size=2, Boolean show_types=False)

## DESCRIPTION
The **load_account**() function returns a dictionary of account information.

The **load_accounts**() function returns a dictionary of accounts information.

The *complete* parameters contains a list of optional contents to download.
It currently only applies to organizational accounts and can contain the strings
"forked_from" and "topics" if an additional request is to be performed to complete
missing information from accounts requests.

The **load_repository**() function returns a dictionary of repository information.

The **load_repositories**() function returns a dictionary of repositories information.

The **get_url_bdata**() function returns an URL binary data and HTTP headers from a recent cache file or from the Web.

The **get_url_data**() function returns an URL text data and HTTP headers from a recent cache file or from the Web.

A dictionary of additional headers (typically for setting session cookies) can be provided in the optional *headers* parameters.

The **prune_cache**() function removes old files and their index entries, and unused directories from the caching directory.

The **collection2xml**() function returns the collection data type as a list of XML lines.
The currently supported collection data types are dict, list, tuple, set, frozenset.
The name of the root element can be indicated with the *name* parameter.
The number of spaces per identation level can be indicated with the *indent_size* parameter.
The elements' type can be optionally included as a tag property with the *show_types* parameter.

All parameters with default values are optional.

### CACHING PARAMETERS

The *cache_dir* parameters indicate the name of a subdirectory in the caching directory intended to isolate the calling program's usage.

The *cache_days* parameters indicate the number of days a content should be served from the cache before being refreshed from the Web. A value of 0 means to disable caching functionalities.

The *force_fetch* parameters indicate if contents should be refreshed from the Web regardless of their age (but their results will be cached).

The *cache_index* parameters indicate if an *index.txt* file should be generated to desribe what's stored in the cache (it's only for human readability purposes).

### RATE-LIMITING PARAMETERS

The *min_delay* parameters indicate the number of seconds to be waited between requests to a specific Web site. 0 means no delay.

The *max_per_day*, *max_per_hour* and *max_per_minute* parameters the cumulated number of requests to a specific Web site that can be made per time period. -1 means no limit.

The *timeout* parameters indicate the maximum number of seconds to wait for an answer from a Web site, before raising a LookupError exception.

Triggering rate limiting will likely raise a PermissionError exception.

## ENVIRONMENT
The *LOCALAPPDATA* and *TMP* environment variables under Windows, and *HOME*, *TMPDIR* and *TMP* environment variables
under other operating systems can influence the caching directory used.

## FILES
The *libgh* library will attempt to maintain a caching directory for the web requests it makes.

This directory will be located in one of the following places:

    Unix:
        ${HOME}/.cache/libgh
        ${TMPDIR}/.cache/libgh
        ${TMP}/.cache/libgh
    Windows:
        %LOCALAPPDATA%\cache\libgh
        %TMP%\cache\libgh

An *index.txt* file will make the correspondence between URL and files.

## STANDARDS
The **libgh** library is not a standard UNIX one.

This implementation tries to follow the [PEP 8](https://www.python.org/dev/peps/pep-0008/) style guide for [Python](https://www.python.org/) code.

## PORTABILITY
To be tested under Windows.

## HISTORY
This implementation was made for the [PNU project](https://github.com/HubTou/PNU).

It's intended as the scraping engine for another tool.

## LICENSE
This library is available under the [3-clause BSD license](https://opensource.org/licenses/BSD-3-Clause).

## AUTHORS)
[Hubert Tournier](https://github.com/HubTou)

## CAVEATS
Some information are not available in unauthenticated mode and the rate limits
per hour are quite low, but it should be fine anyway for most usages.
