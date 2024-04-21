# GitHub data
Data is returned as a dictionary where the keys are the accounts nicknames (eg. https://github.com/NICKNAME).

I haven't seen [Enterprise accounts](https://docs.github.com/en/get-started/learning-about-github/types-of-github-accounts) yet.
Only Personal and Organization accounts are processed for the moment.

In **bold** what's already available.

## Personal accounts
GitHub Data | libGitHub Field | Type | Required? | Comment
--- | --- | --- | --- | ---
Avatar | **Avatar** | str | no | absolute URL of the profile picture
Name | **Name** | str | no | full name
Pronouns | | | | not provided while unauthenticated
Bio | **Biography** | str | no |
Sponsor | **Sponsor** | boolean | yes | True if the user has a sponsor button 
Followers count | **Followers-Count** | int | no | can be rounded to kilos (or megs?)
Followers list | Followers | dict | no | NOT FETCHED YET
Following count | **Following-Count** | int | no | can be rounded to kilos (or megs?)
Following list | Following | dict | no | NOT FETCHED YET
Company | **Company** | str | no |
Location | **Location** | str | no |
Timezone | **Timezone** | str | no |
Public Email | | | | not provided while unauthenticated
Profile website URL | **Website** | str | no | absolute URL
Social | **Social** | dict | yes |
Social: facebook | **Social**/**facebook** | dict | no | items have an **Id** and a **URL**
Social: Instagram | **Social**/**Instagram** | dict | no | items have an **Id** and a **URL**
Social: LinkedIn | **Social**/**LinkedIn** | dict | no | items have an **Id** and a **URL**
Social: Mastodon | **Social**/**Mastodon** | dict | no | items have an **Id** and a **URL**
Social: Mozilla (Mastodon) | **Social**/**Mozilla** | dict | no | items have an **Id** and a **URL**
Social: X (Twitter) | **Social**/**X** | dict | no | items have an **Id** and a **URL**
Social: YouTube | **Social**/**YouTube** | dict | no | items have an **Id** and a **URL**
Social: others | **Social**/**URL** | list of str | no |
Achievements | **Achievements** | dict | yes | items have a **Badge** and a **Count**. [Possible values](https://github.com/drknzz/GitHub-Achievements?tab=readme-ov-file#-achievement-list-)
Highlights | **Highlights** | list of str | yes | [possible values](https://github.com/drknzz/GitHub-Achievements?tab=readme-ov-file#-highlights-badges-)
Organizations | **Organizations** | dict | yes | items have an **Avatar**
Repositories Count | **Repositories-Count** | int | yes |
Repositories List | **Repositories** | dict | yes | [see below](https://github.com/HubTou/libGitHub/blob/main/FIELDS.md#personal-accounts-repositories)
Repositories Stars | **Repositories-Stars** | int | yes | computed from the stargazers of each repository
Stars Count | **Stars-Count** | int | yes | 
Stars List | Stars | dict | yes | NOT FETCHED YET
Sponsoring | Sponsoring | dict | no | NOT FETCHED YET
Yearly contributions | | | | not available
Member since year | | | | not available

#### Specific URL

Item | URL
--- | ---
repositories | GH/ACCOUNT?tab=repositories
projects | GH/ACCOUNT?tab=projects
packages | GH/ACCOUNT?tab=packages
stars | GH/ACCOUNT?tab=stars
sponsoring | GH/ACCOUNT?tab=sponsoring
followers | GH/ACCOUNT?tab=followers
following | GH/ACCOUNT?tab=following
achievements | GH/ACCOUNT?tab=achievements
overview | GH/ACCOUNT?tab=overview&from=AAAA-MM-DD&to=AAAA-MM-DD
sponsor | GH/sponsors/ACCOUNT

## personal accounts repositories
A dictionary where the keys are the repositories names of a personal account.

GitHub Data | libGitHub Field | Type | Required? | Comment
--- | --- | --- | --- | ---
Forked from | **Forked from** | str | no | present for forked repositories
Description | **Description** | str | no |
Main programming language | **Programming language** | str | no |
Stargazers Count | **Stargazers-Count** | int | yes |
Stargazers List | Stargazers | dict | yes | NOT FETCHED YET
Forks Count | **Forks-Count** | int | yes |
Forks List | Forks | dict | yes | NOT FETCHED YET
License | **License** | str | no |
Last updated | **Last updated** | str | no |

#### Specific URL

Item | URL
--- | ---
forks | GH/ACCOUNT/REPO/forks
stargazers | GH/ACCOUNT/REPO/stargazers

## Organization accounts
GitHub Data | libGitHub Field | type | Required? | Comment
--- | --- | --- | --- | ---
Profile picture | **Avatar** | str | no | absolute URL
Organization display name | **Name** | str | yes |
Description | **Biography** | str | yes? | can be empty
Followers count | **Followers-Count** | int | no | can be rounded to kilos (or megs?)
Followers list | Followers | dict | no | NOT FETCHED YET
Location | **Location** | str | no |
Profile website URL | **Website** | str | no | absolute URL
Social | **Social** | dict | yes |
Social: facebook | **Social**/**facebook** | dict | no | items have an **Id** and a **URL**
Social: Instagram | **Social**/**Instagram** | dict | no | items have an **Id** and a **URL**
Social: LinkedIn | **Social**/**LinkedIn** | dict | no | items have an **Id** and a **URL**
Social: Mastodon | **Social**/**Mastodon** | dict | no | items have an **Id** and a **URL**
Social: Mozilla (Mastodon) | **Social**/**Mozilla** | dict | no | items have an **Id** and a **URL**
Social: X (Twitter) | **Social**/**X** | dict | no | items have an **Id** and a **URL**
Social: YouTube | **Social**/**YouTube** | dict | no | items have an **Id** and a **URL**
Social: others | **Social**/**URL** | list of str | no |
Repositories Count | **Repositories-Count** | int | yes | For some reason the count is unavailable in machine fetched pages, but still appears in another place. Sometimes different from what appears in detail pages
Repositories List | **Repositories** | dict | yes | 
Repositories Stars | **Repositories-Stars** | int | yes | computed from the stargazers of each repository
Teams Count | | | | not available
People Count | | | | not available
People details | | | | not available
Top languages details | | | | not available
Most used topics details | | | | not available

#### Specific URL

Item | URL
--- | ---
followers | GH/orgs/ACCOUNT/followers
repositories | GH/orgs/ACCOUNT/repositories?page=X

## personal accounts repositories
A dictionary where the keys are the repositories names of a personal account.

GitHub Data | libGitHub Field | Type | Required? | Comment
--- | --- | --- | --- | ---
Is fork | **Forked from** | str | no | if present the repository is a fork but we don't have the origin
Description | **Description** | str | no |
Topics Count | **Topics-Count** | int | yes |
Topics List | **Topics** | list of str | yes |
Main programming language | **Programming language** | str | no |
Stargazers Count | **Stargazers-Count** | int | yes |
Stargazers List | Stargazers | dict | yes | NOT FETCHED YET
Forks Count | **Forks-Count** | int | yes |
Forks List | Forks | dict | yes | NOT FETCHED YET
Issues Count | **Issues-Count** | int | yes |
Pull requests Count | **Pull requests-Count** | int | yes |
License | **License** | str | no |
Last updated | **Last updated** | str | yes |

## Enterprise accounts
Yet to be seen!
