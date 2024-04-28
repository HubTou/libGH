# GitHub data
Data is returned as a dictionary where the keys are the accounts nicknames (eg. https://github.com/NICKNAME).

I haven't seen [Enterprise accounts](https://docs.github.com/en/get-started/learning-about-github/types-of-github-accounts) yet.
Only Personal and Organization accounts are processed for the moment.

In **bold** what's already available.

## Accounts
GitHub Data | Perso. | Orga. | libGitHub Field | Type | Comment
--- | --- | --- | --- | --- | ---
&nbsp; | yes | yes | **account_type** | str | "personal" or "organization"
Avatar | yes | | **avatar** | str | absolute URL of the profile picture
Profile picture | | yes | **avatar** | str | absolute URL of the profile picture
Name | yes | | **name** | str | full name
Organization display name | | yes | **name** | str | |
Pronouns | yes | no | | | not provided while unauthenticated
Bio | yes | | **biography** | str | |
Description | | yes | **biography** | str | 
Sponsor | yes | no | **sponsor** | boolean | True if the user has a sponsor button 
Followers count | yes | yes | **followers_count** | int | can be rounded to kilos (or megs?)
Followers list | yes | yes | followers | dict | NOT FETCHED YET
Following count | yes | no | **following_count** | int | can be rounded to kilos (or megs?)
Following list | yes | no | following | dict | NOT FETCHED YET
Company | yes | no | **company** | str |
Location | yes | yes | **location** | str | 
Timezone | yes | no | **timezone** | str |
Public Email | yes | no | | | not provided while unauthenticated
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
Achievements | yes | no | **achievements** | dict | items have a **badge** and a **count**. [Possible values](https://github.com/drknzz/GitHub-Achievements?tab=readme-ov-file#-achievement-list-)
Highlights | yes | no | **highlights** | list of str | [possible values](https://github.com/drknzz/GitHub-Achievements?tab=readme-ov-file#-highlights-badges-)
Organizations | yes | no | **organizations** | dict | items have an **avatar**
Repositories Count | yes | yes | **repositories_count** | int | For some reason the count is unavailable in machine fetched pages, but still appears in another place. Sometimes different from what appears in detail pages
Repositories List | yes | yes | **repositories** | dict |
Repositories Stars | yes | yes | **repositories_stars** | int | computed from each repository
Stars Count | yes | no | **stars_count** | int |
Stars List | yes | no | stars | dict | NOT FETCHED YET
Sponsoring | yes | no | sponsoring | dict | NOT FETCHED YET
Yearly contributions | yes | no | | | not available
Member since year | yes | no | | | not available
Teams Count | no | yes | | | not available
People Count | no | yes | | | not available
People details | no | yes | | | not available
Top languages | (yes) | yes | **top_languages** | dict | computed from each repository. By decreasing number of repositories
Most used topics | (yes) | yes | **most_used_topics** | dict | computed from each repository. By decreasing number of repositories

## Repositories
A dictionary where the keys are the repositories names.

In the table below, the *Repo.* column is for direct repository page scraping.

GitHub Data | Perso. | Orga. | Repo. | libGitHub Field | Type | Comment
--- | --- | --- | --- | --- | --- | ---
Forked from | yes | | | **forked_from** | str | present for forked repositories
Is fork | | yes | | **forked_from** | str | if present the repository is a fork but we don't have the origin
Description | yes | yes | yes | **description** | str |
Software website URL | no | no | yes | **website** | absolute URL
Topics List | yes | yes | yes | **topics** | list of str | may be partial unless taken from the repository page
Topics Count | no | yes | yes | **topics_count** | int |
Contributors Count | no | no | yes | **contributors_count** | int |
Contributors list | no | no | yes | contributors | dict | NOT FETCHED YET
Main programming language | yes | yes | yes | **programming_language** | str |
Languages | no | no | yes | **languages** | dict | key = language (str), value = percentage (str)
Stargazers Count | yes | yes | yes | **stargazers_count** | int |
Stargazers List | yes | yes | yes | stargazers | dict | NOT FETCHED YET
Watching Count | no | no | yes | **watching_count** | int |
Watching List | no | no | yes | watching | dict | NOT FETCHED YET
Forks Count | yes | yes | yes | **forks_count** | int |
Forks List | yes | yes | yes | forks | dict | NOT FETCHED YET
Issues Count | no | yes | yes | **issues_count** | int |
Pull requests Count | no | yes | yes | **pull_requests_count** | int |
License | yes | yes | | **license** | str |
Last updated | yes | yes | | **last_updated** | str |

## Specific URL
Item | Perso. | Orga. | URL
--- | --- | --- | ---
repositories | yes | | GH/ACCOUNT?tab=repositories
repositories | | yes | GH/orgs/ACCOUNT/repositories?page=X
projects | yes | | GH/ACCOUNT?tab=projects
packages | yes | | GH/ACCOUNT?tab=packages
stars | yes | no | GH/ACCOUNT?tab=stars
sponsoring | yes | no | GH/ACCOUNT?tab=sponsoring
followers | yes | | GH/ACCOUNT?tab=followers
followers | | yes | GH/orgs/ACCOUNT/followers
following | yes | no | GH/ACCOUNT?tab=following
achievements | yes | no | GH/ACCOUNT?tab=achievements
overview | yes | no | GH/ACCOUNT?tab=overview&from=AAAA-MM-DD&to=AAAA-MM-DD
sponsor | yes | no | GH/sponsors/ACCOUNT
forks | yes | yes | GH/ACCOUNT/REPO/forks
stargazers | yes | yes | GH/ACCOUNT/REPO/stargazers
