# About

Torrent tracker. Fixes some of the annoyances with Gazelle.

Multiple artists with the same name all get different pages, owing to a well-typed separation between:

* artists (who may have any contributory relationship to a release group: such as "composer", "producer", "main", and so on)
* release groups (the abstract concept of an release that groups specific releases together, and that many artists may contribute to)
* releases (specific pressings of an album: special editions, alternate editions, and so on)
* torrents (an encode of a release)

The upload page is dynamic. Typing in the name of an artist brings up an autocomplete function, which allows one to select from a list of pre-existing release groups and releases for said artist.

Torrents can be uploaded from any page, with the relevant details filled in on the upload page. For example:

* One can click "Upload Release Group" on an artist's page, to skip the artist part of the upload page, and directly add a new release group to the artist, a new release to the release group, and torrent to the release.
* One can click "Upload Release" on a release group's page, to skip the artist and release group part of the upload page, and directly add a new release to the release group and torrent to the release.

# Screenshots

![Release group page](/screenshots/release-group-page.png)

![Upload page](/screenshots/upload-page.png)

# Feature List & Roadmap

* 🟩 Robust database schema
	- 🟩 Capable of disambiguating multiple artists with the same name
* 🟩 Search
	- 🟩 With autocomplete
	- 🟨 Advanced search with filters
* 🟩 metainfo uploading
* 🟩 metainfo downloading
* 🟩 bittorrent announce
	- 🟨 Authentication with passkey
* 🟩 Progressive upload page
	- 🟩 Fields can be autocompleted by searching for an artist or album
	- 🟩 Fields can be autocompleted by clicking "upload here" on an artist/release group/release page
* 🟩 Artist pages
	- 🟩 Artist portrait image
	- 🟩 Artist country flag
	- 🟨 Artist biography
* 🟩 Release group pages
	- 🟩 Album art image
* 🟩 Release pages
	- 🟩 Album art image
* 🟩 Torrent pages
	- 🟩 File list
* 🟨 Web torrent support
	- 🟨 Ability to stream an album
	- 🟨 Ability to stream album art
* 🟩 Forum
	- 🟩 Threads
	- 🟩 Categories
* 🟩 Users
	- 🟩 User biography
	- 🟨 User avatar
	- 🟨 User inbox/messaging system
	- 🟩 Latest downloads/uploads
	- 🟨 Download/uploads list
	- 🟨 Download/upload totals and ratio
	- 🟨 Current seeding list
	- 🟩 Permissions system
	- 🟨 User classes
* 🟨 Requests
	- 🟨 Bounties
	- 🟨 Subscriptions
	- 🟨 Linking relevant requests on artist/release group/release pages
* 🟩 News

# Requirements

* Python >=3.10

# Dependencies

* django
* django-glrm
* django-markupfield
* django-picklefield
* django-debug-toolbar
* django-countries
* django-mptt
* djangorestframework
* bcoding
* markdown

# Development

## Installing

1. If not running python 3.11, install [pyenv](https://github.com/pyenv/pyenv).
2. Install [poetry](https://python-poetry.org/docs/).
3. Run `poetry install` from the repository directory to set up a virtual environment with the necessary python version and packages

## Running

Populate the database:

* Create the default user groups: `poetry run python3 manage.py create_user_groups`
* Create the default forum categories: `poetry run python3 manage.py create_forum_groups`
* Create a super user account: `poetry run python3 manage.py createsuperuser`

Run the server: `poetry run python3 manage.py runserver`

## Testing

`poetry run python3 manage.py test`

# License & Credits

MIT License. See [LICENSE.md](../master/LICENSE.md). Credits and licenses for images can be found in [CREDITS.md](../master/CREDITS.md).
