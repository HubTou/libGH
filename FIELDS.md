# GitHub data
Data is returned as a dictionary where the keys are the accounts nicknames (eg. https://github.com/NICKNAME).

I haven't seen [Enterprise accounts](https://docs.github.com/en/get-started/learning-about-github/types-of-github-accounts) yet.
Only Personal and Organization accounts are processed for the moment.

In **bold** what's already available.

## Personal accounts
Data | Field | Required? | Comment
--- | --- | --- | ---
Nick name | **Nickname** | yes | As in https://github.com/NICKNAME
Avatar | **Avatar** | no | absolute URL of the profile picture
Name | **Name** | no | Full name
Bio | **Biography** | no | can be empty
Pronouns | - | no | NOT FETCHED YET
Followers URL | **Followers/URL** | no |
Followers count | **Followers/Count** | no | can be rounded to kilos (or megs?)
Followers list | Followers/Dict | no | NOT FETCHED YET
Following URL | **Following/URL** | no |
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
Repositories URL | **Repositories/URL** | yes | absolute URL
Repositories Count | **Repositories/Count** | yes |
Repositories List | **Repositories/Dict** | yes | 
Projects | - | no | WON'T BE FETCHED
Packages | - | no | WON'T BE FETCHED
Stars URL | **Stars/URL** | yes | absolute URL
Stars Count | **Stars/Count** | yes |
Stars List | Stars/Dict | yes | NOT FETCHED YET
Yearly contributions | - | no | NOT FETCHED YET

## Organization accounts
Data | Field | Required? | Comment
--- | --- | --- | ---
Profile picture | **Avatar** | no | absolute URL
Organization display name | **Name** | yes |
Email | Email | ? | NOT FETCHED YET
Description | **Biography** | yes?| can be empty
Followers URL | **Followers/URL** | no |
Followers count | **Followers/Count** | no | can be rounded to kilos (or megs?)
Followers list | Followers/Dict | no | NOT FETCHED YET
Location | **Location** | no |
URL | **Website** | no | absolute URL
LinkedIn | LinkedIn | no | NOT FETCHED YET
Facebook | Facebook | no | NOT FETCHED YET
Twitter | Twitter | no | NOT FETCHED YET
Instagram | Instagram | no | NOT FETCHED YET
Repositories URL | **Repositories/URL** | yes | absolute URL
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
A dictionary where the keys are the repositories names.

Data | Field | Required? | Comment
--- | --- | --- | ---
- | URL | yes |

## Repository
Data | Field | Required? | Comment
--- | --- | --- | ---
