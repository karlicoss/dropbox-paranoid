Tool to get around some Dropbox inconveniences.

1. If you have a file editing conflict, Dropbox would normally show you the notification, but that's easy to miss or forget to resolve. This script is looking for such files and notifies you of them.
2. Dropbox is quite bad at handling symlinks and is corrupting symlinks in two ways:

    * turning internal symlinks (pointing within Dropbox folder) into regular files (e.g. as described [here](http://www.paulingraham.com/dropbox-and-symlinks.html)).
    * turning external symlinks into regular files on the remote machines. Arguably, it's a 'feautre', but often not what you would expect.

To prevent that, this script searches for symlinks and notifies you of them to prevent corruption.

# Running
1. `cp config.py.example config.py` and modify `config.py` so `DB_PATH` is set properly.
2. You might want to run this script on cron, say, every 10 minutes so you get notified quickly. It's worth running on every laptop you're syncing to.

# Prerequisites
* python3.6
* [optional] `python3-notify2` for nice desktop notifications

