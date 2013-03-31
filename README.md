walrus
======

Walrus is a tool for sending images in [PyBitmessage](Bitmessage/PyBitmessage).

Roughly, it:
* Base64 encodes the provided image
* Wraps the image string in richtext markup
* Sends the result as a message

To do those things it uses the API built into [PyBitmessage](Bitmessage/PyBitmessage)

Bitmessage's Wiki explains [how to configure your API credentials](https://bitmessage.org/wiki/API_Reference).

configuration
-------------

Walrus needs your API credentials. By default Walrus will attempt to load PyBitmessage's keys.dat from PyBitmessage's appdata folder. This should be fine for most users.

If you're running PyBitmessage in portable mode you'll need to set the path to the PyBitmessage folder. Use the `bitmsgpath` variable near the top of walrus.py to do so.

If you'd rather manually specify the username, password, host, and port, you can do so by setting the variables directly below `bitmsgpath`.

Walrus, by default, assumes you want to share images with the Image Board mailing list. The address is set below `bitmsgpath`. You can also specify an address to send to at runtime using the -t flag. 

usage
-----

```
Usage: walrus.py filename [options]

Options:
  --version             show program's version number and exit
  -h, --help            show this help message and exit
  -s, --send            Send output to Address
  -f FROM, --from=FROM  Address/Label to send from
  -t TO, --to=TO        Address/Label to send to.
  -u SUBJECT, --subject=SUBJECT
                        Subject of the message. Default is image name.
```

todo
----

- [x] Get basic functionality implemented
- [ ] Flesh out API portion and split into separate file
- [ ] Support multiple images per message
- [ ] Ensure To Address is valid

help
----

Walrus has been tested on Ubuntu. It should work just as well on OSX and Windows but I can't be sure. Please open an issue if you've found an error in Walrus.

If you've found a problem with [PyBitmessage](Bitmessage/PyBitmessage), please open an issue on their Github issue tracker

contribute
----------

I'd be happy to receive suggestions and pull requests here on Github.

license
-------

Walrus is licensed under the MIT license. See the included LICENSE file or http://delicatebits.mit-license.org
