# GitHub data
In **bold** what's made available.

## Accounts
Data is returned as a dictionary where the keys are the accounts nicknames (eg. https://github.com/NICKNAME).

GitHub Data | Perso. | Orga. | libGitHub Field | Type | Comment
--- | --- | --- | --- | --- | ---
&nbsp; | yes | yes | **account_type** | str | "personal" or "organization"
Avatar / Profile picture | yes | yes | **avatar** | str | absolute URL of the profile picture
Name | yes | yes | **name** | str | full name
Pronouns | yes | | | | not provided while unauthenticated
Bio / Description | yes | yes | **biography** | str | |
Sponsor | yes | | **sponsor** | boolean | True if the user has a sponsor button 
Followers count | yes | yes | **followers_count** | int | can be rounded to kilos (or megs?)
Followers list | yes | yes | followers | dict | NOT FETCHED YET
Following count | yes | | **following_count** | int | can be rounded to kilos (or megs?)
Following list | yes | | following | dict | NOT FETCHED YET
Company | yes | | **company** | str |
Location | yes | yes | **location** | str | 
Timezone | yes | | **timezone** | str |
Public Email | yes | | | | not provided while unauthenticated
Profile website URL | yes | yes | **website** | str | absolute URL
Social | yes | yes | **social** | dict | yes |
Social: facebook | yes | yes | **social**/**facebook** | dict | items have an **id** and a **url**
Social: Instagram | yes | yes | **social**/**instagram** | dict | items have an **id** and a **url**
Social: LinkedIn | yes | yes | **social**/**linkedin** | dict | items have an **id** and a **url**
Social: Mastodon | yes | yes | **social**/**mastodon** | dict | items have an **id** and a **url**
Social: Mozilla (Mastodon) | yes | yes | **social**/**mozilla** | dict | items have an **id** and a **url**
Social: X (Twitter) | yes | yes | **social**/**x** | dict | items have an **id** and a **url**
Social: YouTube | yes | yes | **social**/**youtube** | dict | items have an **id** and a **url**
Social: others | yes | yes | **social**/**url** | list of str |
Achievements | yes | | **achievements** | dict | items have a **badge** and a **count**. [Possible values](https://github.com/drknzz/GitHub-Achievements?tab=readme-ov-file#-achievement-list-)
Highlights | yes | | **highlights** | list of str | [possible values](https://github.com/drknzz/GitHub-Achievements?tab=readme-ov-file#-highlights-badges-)
Organizations | yes | | **organizations** | dict | items have an **avatar**
Repositories Count | yes | yes | **repositories_count** | int | For some reason the count is unavailable in machine fetched pages, but still appears in another place. Sometimes different from what appears in detail pages
Repositories List | yes | yes | **repositories** | dict |
Repositories Stars | yes | yes | **repositories_stars** | int | computed from each repository
Stars Count | yes | | **stars_count** | int |
Stars List | yes | | stars | dict | NOT FETCHED YET
Sponsoring | yes | | sponsoring | dict | NOT FETCHED YET
Yearly contributions | yes | | | | not available
Member since year | yes | | | | not available
Teams Count | | yes | | | not available
People Count | | yes | | | not available
People details | | yes | | | not available
Top languages | (yes) | yes | **top_languages** | dict | computed from each repository. By decreasing number of repositories
Most used topics | (yes) | yes | **most_used_topics** | dict | computed from each repository. By decreasing number of repositories

## Repositories
Data is returned as a dictionary where the keys are the repositories names.

In the table below, the *Repo.* column is for direct repository page scraping.

GitHub Data | Perso. | Orga. | Repo. | libGitHub Field | Type | Comment
--- | --- | --- | --- | --- | --- | ---
Forked from | yes | | yes | **forked_from** | str | present for forked repositories
Is fork | | yes | | **forked_from** | str | if present the repository is a fork but we don't have the origin
Description | yes | yes | yes | **description** | str |
Software website URL | | | yes | **website** | absolute URL
Topics List | yes | yes | yes | **topics** | list of str | may be partial unless taken from the repository page
Topics Count | | yes | yes | **topics_count** | int |
Contributors Count | | | yes | **contributors_count** | int |
Contributors list | | | yes | contributors | dict | NOT FETCHED YET
Main programming language | yes | yes | yes | **programming_language** | str |
Languages | | | yes | **languages** | dict | key = language (str), value = percentage (float)
Stargazers Count | yes | yes | yes | **stargazers_count** | int |
Stargazers List | yes | yes | yes | stargazers | dict | NOT FETCHED YET
Watching Count | | | yes | **watching_count** | int |
Watching List | | | yes | watching | dict | NOT FETCHED YET
Releases Count | | | yes | **releases_count** | int |
Last release name | | | yes | **last_release_name** | str |
Last release date | | | yes | **last_release_date** | str | datetime
Packages Count | | | yes | **packages_count** | int |
Sponsor Button | | | yes | **is_sponsorable** | boolean |
Forks Count | yes | yes | yes | **forks_count** | int |
Forks List | yes | yes | yes | forks | dict | NOT FETCHED YET
Issues Count | | yes | yes | **issues_count** | int |
Pull requests Count | | yes | yes | **pull_requests_count** | int |
License | yes | yes | yes | **license** | str | "specific" is used for any non-standard license
Branches Count | | | yes | | | not available
Tags Count | | | yes | | | not available
Last updated | yes | yes | | **last_updated** | str |
Commits Count | | | yes | **commits_count** | int |

## Interesting URL for further scraping
Item | Perso. | Orga. | URL
--- | --- | --- | ---
Achievements | yes | | GH/ACCOUNT?tab=achievements
Contributors | yes | yes | GH/ACCOUNT/REPO/graphs/contributors
Followers | yes | | GH/ACCOUNT?tab=followers
Followers | | yes | GH/orgs/ACCOUNT/followers
Following | yes | | GH/ACCOUNT?tab=following
forks | yes | yes | GH/ACCOUNT/REPO/forks
Overview | yes | | GH/ACCOUNT?tab=overview&from=AAAA-MM-DD&to=AAAA-MM-DD
Packages | yes | | GH/ACCOUNT?tab=packages
Projects | yes | | GH/ACCOUNT?tab=projects
Sponsor | yes | | GH/sponsors/ACCOUNT
Sponsoring | yes | | GH/ACCOUNT?tab=sponsoring
Stargazers | yes | yes | GH/ACCOUNT/REPO/stargazers
Stars | yes | | GH/ACCOUNT?tab=stars
Watchers | yes | yes | GH/ACCOUNT/REPO/watchers
