About the Asset
===================

Overview
----------

This asset emerged from the need to support different types of interactions with physical props
across various contexts. An early prototype concentrated all logic into a single script, causing the
codebase to grow into an ever-expanding monolith as new behaviors and interaction types were added.
This led to the development of a Prop system that incorporates new behaviors using the
component pattern, no custom scripts or nested inheritance required.

Current Features
--------------------

Currently, three behavior types are supported:

1. **Grab Behaviour**: allows the prop to be secured in place by a spring mechanism.
2. **Spin Behaviour**: allows the prop to be rotated around its X and Y axes.
3. **Throw Behaviour**: applies an impulse to the object, launching it in a given direction.

And two interaction modes:

1. **Cursor Mode**: interaction is performed through the cursor.
2. **Camera Mode**: interaction is performed through the center of the camera, ideal for first-person games.

Vision & Goals
------------------

The asset was designed to be easy to setup and straightforward to expand. The core idea is to be
able to add and remove behaviors from the Prop without the need for custom scripts or deeply nested
inheritance. For this reason, the component pattern was adopted.

In the future, adding a new behavior should be as simple as creating a script following the
``<name>_behaviour.gd`` convention and attaching it to the target Prop in the scene, configuring
it through the Inspector, without ever touching the source code in the ``core`` directory. The
current architecture does not yet support this, but it remains the goal for upcoming versions.

Also, setting up a scene from scratch should not be a difficult task. This is, in fact, one of the
asset's core purposes: to provide a straightforward setup experience with minimal cognitive overhead.

Installation
-----------------

To install the asset, download it from the Godot Asset Library <https://godotengine.org/asset-library/asset>
(not yet available) or clone the repository, then, extract the archive and drag the ``addons`` folder
along with all its contents into the root of your ``Godot`` project and let the engine work its magic.

License
-------
 
CC0 1.0 Universal (CC0 1.0) Public Domain Dedication
Copyright © 2025 Contributors
 
To the extent possible under law, the authors have waived all copyright
and related or neighboring rights to this software and associated
documentation files (the "Software").
 
This work is published from Brazil.
 
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
 
You should have received a copy of the CC0 Public Domain Dedication
along with this software. If not, see:
https://creativecommons.org/publicdomain/zero/1.0/