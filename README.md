# reddl
improved reddit CLI searcher

reddl has been heavily inspired by [redyt by Bugswriter](https://github.com/Bugswriter/redyt) but offers a number of improvements, such as .gif support, automatic fullscreen, searching for users, support for sorting by different time periods, using a less suspicious user agent, etc.

## Installation

It's a simple shell script. Just download it anywhere (preferably somewhere in your PATH) and execute it. reddl will automatically create the files `~/.config/reddl/subs` and `~/.config/reddl/users` to store your favorite subreddits/users. They come with some suggestions, but you can change them or ignore them altogether. 

To run reddl, you'll need sxiv as an image viewer, dmenu for user input, and jq to parse reddit's .json file. Supports notify-send, but will otherwise just use echo as a notifier.

## Usage

If you use reddl without an option, it will open up dmenu to ask you for a subreddit and download all pictures from the first 100 posts on the subreddit's hot page. Available options are:

- \-n [requests] &nbsp; &nbsp; Set the number of requests. For example `reddl -n 10` only looks at the first 10 posts on that subreddit. Defaults to 100.
- \-s [hot, new,...] &nbsp; &nbsp; Sort by either "hot", "new", "top", or "rising". Defaults to "hot".
- \-t [day, week,...] &nbsp; &nbsp; Set the time period for sorting by top. For example `reddl -s top -t all` gives the top posts of all time on that subreddit. Does nothing if not sorting by top.
- \-f &nbsp; &nbsp; Usually reddl opens the images in fullscreen. Use the -f option if you _don't_ want reddl to open in fullscreen and prefer a new window instead. You can always press the `F` key in sxiv to toggle between fullscreen and windowed mode.
- \-u &nbsp; &nbsp; Search for users instead of subreddits. Has it's own file for default dmenu entries.
- \-h &nbsp; &nbsp; Opens up a brief help page.

Images are deleted every time sxiv is closed. If you want to save an image to set it as a wallpaper for your desktop or to do unorthodox things with your waifu, you'd have to copy it from /tmp/reddl while sxiv is still running. There are other scripts that can copy images or set wallpapers straight from sxiv.
