Minetest **tech_api** repository
----------------------------

This repository contains the **tech_api** mod, which makes energy delivery and
distribution uniform throughout all the mods that use it. This means that if you
are creating a [Minetest](http://www.minetest.net/) mod that will
use/produce/store/carry energy, this API will give you all the tools you need to
simplify your life and make your creation compatible with all the other mods
that use it.

It is also an excuse to rewrite the energy subsystem of the
[Technic](https://github.com/minetest-mods/technic) mod, which will probably be
the first one to use the API.

Also, in the future, it may be extended to provide useful methods to deal with
items and fluids (i.e. pipes and tubes compatible between different mods), but
the focus is currently on power distribution.

~~Currently it has no implementation, but a [specification sheet](/docs/specifications.md)
is being written. Go check it out and feel free to contribute with your ideas,
requirements or wishes, so that we can build something we all agree upon and
we'll all be using in our mods.~~

A first implementation is in progress on the
[experimental branch](https://github.com/gdelazzari/tech_api/tree/experimental).

The implementation will happen in steps, progressively optimizing the code.
This allows to first have a basic working version (simple code = less problems,
...usually...) and then to use that as a starting base for the various
planned optimizations.

The specifications document is currently "out of sync", and will stay in this
state until the first basic implementation allows me to figure out exactly how
the system is going to operate. The LDoc documentation, however, will always
reflect the code.

## Current state (TODO list)
+ [x] API skeleton and basic structure
+ [x] Documentation setup (LDoc)
+ [x] Definitions management
+ [x] Nodestore module
+ [x] Base API functions (on_construct/destruct, etc...)
+ [x] Network traversal/discovery algorithm
+ [x] Manage energy classes
+ [x] Manage linkable faces
+ [x] Manage multiple definitions for a node
+ [x] Manage a node being both a device and a transporter
+ [x] Energy distribution algorithm
  + [x] User devices
  + [x] Provider devices
  + [x] Storage devices
  + [x] Monitor devices
+ [ ] Clean up code
+ [ ] Generic performance optimizations
+ [ ] Network management optimizations (when adding/removing devices/transporters)
+ [ ] Nodestore automatic backup every *x* time
+ [ ] Better way of storing the nodestore (modstorage fails for a big one)

## Documentation

The code is well documented using LDoc. First be sure to read the
[specifications document](/docs/specifications.md) to understand the architecture
of the energy system. Then, to have in-depth documentation for the Lua code, you
can run the script `generate-doc.sh`, which will generate HTML pages for the
various modules. Open `ldoc/index.html`. Obviously you must have LDoc installed,
along with its requirements. Follow the
[instructions here](https://github.com/stevedonovan/LDoc).

If you don't care about pretty docs then you can just go through the code and
follow the comments.

## Contributing

You can contribute by creating an issue (or participating to the already open
ones). If you want to help directly with the specs, just fork the repository
and make a pull request.

You can also join the IRC channel #minetest-technic to talk with us.

Thank you!
