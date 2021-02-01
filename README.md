# EXPORT_MODULE for Nadybot

The purpose of this module is to be able to import and export bot data from a generic data interchange format

## Exporting

Exporting all of the Nadybot data of one bot into a portable format which can then be imported into another bot that implements this format:

`!export 2021-01-31`: Generates an export of all your bot data in `data/export/2021-01-31.json`

## Importing

In order to import data from an old export, you should first think about how you want to map access levels between the bots. BeBot or Tyrbot use a totally different access level system than Nadybot.

`!import 2021-01-31 superadmin=admin admin=mod leader=member member=member`: Import from `data/export/2021-01-31.json`, mapping the accesslevel from superadmin to admin, from admin to mod, and so on.

Please note that importing a dump will delete most of the already existing data of your bot, so **only do this after you created an export or database backup**! This cannot be stressed enough.

*In detail*: Everything that is included in the dump, will be deleted before importing. So if your dump contains members of the bot, they will all be wiped first. If it does include an empty set of members, they will still be wiped. Only if the members were not exported at all, they won't be touched.