Core & Components
=====================

The ``core`` code is designed to remain untouched and unexpanded.
Its members are first-class citizens of the asset and must have no
knowledge of the behaviour components.
These are the three ``core`` members and their responsibilities:

  1. ``Prop``
  
      * Owns the ``RigidBody3D`` target body and holds a reference to the
        active ``Interactor``, acting as the central hub between physics,
        input and behaviour.
      * Dispatches interaction lifecycle events (start, end) and camera
        movement requests as signals, decoupling core logic from behaviour
        implementation.

  2. ``Interactor``

      * Casts a ray each physics frame, either from the screen center
        (``CAMERA_MODE``) or from the cursor position (``CURSOR_MODE``),
        to detect and bind ``Prop`` nodes within reach.
      * Tracks and exposes input state (pressed, just_pressed, released)
        and mouse delta for consumption by behaviour components via
        ``get_action_state()`` and ``get_mouse_delta()``.

  3. ``PropBehaviour``

      * Defines the base interface for all behaviour components, exposing
        a reference to the owning ``Prop`` and its active ``Camera3D``
        through the ``setup()`` method.
      * Declares the ``execute()`` method as the single entry point called
        each frame by ``Prop.update_interaction()``, to be overridden by
        each concrete behaviour.

The ``components`` code is considered "second-class", inheriting from
``PropBehaviour`` and meant to be modified, expanded and/or replaced.
Behaviour components can (and should) know about the internals of core
members, but not the other way around.

Currently there are three implementations of behaviour components, 
though more may be added in the future:

  1. ``GrabBehaviour``
  2. ``SpinBehaviour``
  3. ``ThrowBehaviour``
