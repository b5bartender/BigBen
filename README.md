#BigBen IRC Bot

####written by [Christopher T. Lemay](http://www.thecrittac.us)
####requires python-irclib and beautifulsoup

###A simple IRC bot that will chime off the number of BONGs at the top of the hour, among other things.

USAGE: ./BigBen

The first set of commands will cause the bot to connect to the given network, assume the given
nickname and ircname, identify with nickserv using the given password, and join
the given channels.

The second command will read the options from a file.

At the top of the hour, the bot will chime off the same number of BONGs that Big
Ben does. Thus the bot is set to GMT. This happens in all channels that BigBen
is in.

If the phrase ".time" is said in the channel, the bot will tell what time it is,
using the phrase "OI IT'S X BONG", where X is the number of BONGs said at the
top of the hour.
The same thing happens if the message ".time #channel" is messaged to the bot privately.
If the phrase ".ptime" is said in the channel, the bot will /notice the person
who said such a thing with the current time.

If the bot receives a private message of ".speak #channel TEXT_HERE", it will
echo the text back to the channel specified.

Many of these commands can be changed in the COMMANDS file in order to cut down on possible spam.

If ".ping" (or any other message starting with '.' and ending with 'ing') is said in any
channel, the bot will replace 'ing' with 'ong' and respond to that same channel.

If the phrase ".tweet USERNAME" is said in the channel, the bot will fetch the
most recent tweet from that user. If a number is specified after the tweet, the
nth tweet will be fetched.

If the phrase ".urban TERM (optional definition number)" is said in the channel,
the bot will fetch a definition for that term from Urban Dictionary. If a number
is not specified, the bot will fetch the first definition for that term.

If the phrase ".tell NICK MESSAGE" is said in the channel, the bot will /query
the message to the given nick when that nick joins any channel the bot is in or
sends a message to any channel the bot is in.

If the phrase ".4chan BOARD SEARCH_TERM" is said in the channel, the bot will
search the given board on 4chan for threads that have the search term in the
original post. For example, ".4chan g desktop thread" would search /g/ for
threads that have "desktop thread" in the original post.

If kicked, the bot will reconnect after 10 seconds have passed.

If a message in any channel starts with the bot's nick and ends with '??' (for example,
"BigBen, am I ever going to get married??"), the bot will give a random response from the
RESPONSES file.

If the message, minus the leading nick and trailing question mark, is in the
CUSTOMRESPONSES file before the "::" in its line, the message after the "::"
will be sent to the channel.

Nicks in the IGNORE file will be ignored. This is useful if there are other
bots in the channel that we don't want BigBen to get links from. This file
needs to end with a newline character.

Nicks in the NICKS file can privately message the bot ".update" to update the
responses files, the IGNORE file and the NICKS file. The NICKS file also
needs to end with a newline character.

There is a function to log the number of users in each channel. If enabled,
it will write the number of users in each channel to the given file. This updates with
each join and part, and every fifteen seconds.

The bot also supports modifying previous messages with a sed-like syntax. For
example:

<TheCrittaC> aabb
<TheCrittaC> :s/a/b
<BigBen> TheCrittaC: babb
<TheCrittaC> :s/a/b/g
<BigBen> TheCrittaC: bbbb

If you would like to see the bot in action and/or talk with me and the bot, you
can join #BigBen on [Rizon](irc://irc.rizon.net).

BigBen is licensed under the terms of the GNU General Public license, version
2 or later, at the user's discretion.

