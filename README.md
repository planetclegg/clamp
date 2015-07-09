# clamp
CLI Alias tool with variable substitution

(this is a heavily bastardized version derived from https://github.com/seiferteric/clamp)

From the original: This tool allows you to bind a string to a CLI command. It also allows for variable that are passed as cli parameters. This is really handy for testing an HTTP API by wrapping curl commands.

I had the idea to do something like this a while back, found someone had done something similar, but there were a few things I wanted to change:

- Needed to run it on windows shell, cygwin, and OS X
- Wanted to minimize dependencies for quick deploy
- Wanted to be able to edit the config file directly, without lots of escaping
- Wanted to be able to pull in environment variables (with defaults)
- Wanted to be able to recursively call commands with the script

So I set out to hack away at the original script and this is what I came up with.

This version uses .INI style files in the format of SafeConfigParser, rather than JSON, so the configuration documentation from the original is quite different.  For the most part you won't have to escape anything when editing the .clamp file, but beware of semi-colons starting inline comments


##.clamp files
Clamp expects a file file in the current directory called .clamp where it can find the command aliases. This allows you to create different .clamp files for
different projects.


##Install
Manual process currently.. Sorry.  I'm a python neophyte, and was in a hurry.
Requires python3

##TODO
- general clean up, there are a few hacky things in the script currently
- provide a mechanism for injectable converters, (e.g. url-encoding parameters)
- 