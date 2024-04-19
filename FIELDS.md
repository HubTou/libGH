# GitHub data
Data is returned as a dictionary where the keys are the accounts nicknames (eg. https://github.com/NICKNAME).

I haven't seen [Enterprise accounts](https://docs.github.com/en/get-started/learning-about-github/types-of-github-accounts) yet.
Only Personal and Organization accounts are processed for the moment.

In **bold** what's already available.

## Personal accounts
Data | libGitHub Field | Required? | Comment
--- | --- | --- | ---
Avatar | **Avatar** | no | absolute URL of the profile picture
Name | **Name** | no | Full name
Bio | **Biography** | no | can be empty
Pronouns | - | no | NOT FETCHED YET
Followers count | **Followers/Count** | no | can be rounded to kilos (or megs?)
Followers list | Followers/Dict | no | NOT FETCHED YET
Following count | **Following/Count** | no | can be rounded to kilos (or megs?)
Following list | | Following/Dict | NOT FETCHED YET
Company | Company | no | NOT FETCHED YET
Location | **Location** | no |
Email | Email | no | NOT FETCHED YET
URL | **Website** | no | absolute URL
LinkedIn | LinkedIn | no | NOT FETCHED YET
Facebook | Facebook | no | NOT FETCHED YET
Twitter | Twitter | no | NOT FETCHED YET
Instagram | Instagram | no | NOT FETCHED YET
Social account | - | no | NOT FETCHED YET
Repositories Count | **Repositories/Count** | yes |
Repositories List | **Repositories/Dict** | yes | 
Projects | - | no | WON'T BE FETCHED
Packages | - | no | WON'T BE FETCHED
Stars Count | **Stars/Count** | yes |
Stars List | Stars/Dict | yes | NOT FETCHED YET
Yearly contributions | - | no | NOT FETCHED YET

Specific URL:

Item | URL
--- | ---
repositories | GH/ACCOUNT?tab=repositories
projects | GH/ACCOUNT?tab=projects
packages | GH/ACCOUNT?tab=packages
stars | GH/ACCOUNT?tab=stars
followers | GH/ACCOUNT?tab=followers
following | GH/ACCOUNT?tab=following
achievements | GH/ACCOUNT?tab=achievements
overview | GH/ACCOUNT?tab=overview&from=AAAA-MM-DD&to=AAAA-MM-DD
sponsor | GH/sponsors/ACCOUNT

## personal accounts repositories

Specific URL:

Item | URL
--- | ---
forks | GH/ACCOUNT/REPO/forks
stargazers | GH/ACCOUNT/REPO/stargazers

## Organization accounts
Data | libGitHub Field | Required? | Comment
--- | --- | --- | ---
Profile picture | **Avatar** | no | absolute URL
Organization display name | **Name** | yes |
Email | Email | ? | NOT FETCHED YET
Description | **Biography** | yes?| can be empty
Followers count | **Followers/Count** | no | can be rounded to kilos (or megs?)
Followers list | Followers/Dict | no | NOT FETCHED YET
Location | **Location** | no |
URL | **Website** | no | absolute URL
LinkedIn | LinkedIn | no | NOT FETCHED YET
Facebook | Facebook | no | NOT FETCHED YET
Twitter | Twitter | no | NOT FETCHED YET
Instagram | Instagram | no | NOT FETCHED YET
Repositories Count | **Repositories/Count** | yes | For some reason the count is unavailable in machine fetched pages, but still appears in another place. Sometimes different from what appears in detail pages
Repositories List | **Repositories/Dict** | yes | 
Discussions | - | no | WON'T BE FETCHED
Projects | - | no | WON'T BE FETCHED
Packages | - | no | WON'T BE FETCHED
Teams | - | no | NOT FETCHED YET
People | - | no | NOT FETCHED YET

## Enterprise accounts
Yet to be seen!

## Repositories dictionary
A dictionary where the keys are the repositories names of a personal or organization account.

Data | Field | Required? | Comment
--- | --- | --- | ---
url | URL | yes |
