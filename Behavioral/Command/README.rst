`Command`__
===========

Purpose
-------

To encapsulate invocation and decoupling.

We have an Invoker and a Receiver. This pattern uses a "Command" to
delegate the method call against the Receiver and presents the same
method "execute". Therefore, the Invoker just knows to call "execute" to
process the Command of the client. The Receiver is decoupled from the
Invoker.

The second aspect of this pattern is the undo(), which undoes the method
execute(). Command can also be aggregated to combine more complex
commands with minimum copy-paste and relying on composition over
inheritance.

Examples
--------

-  A text editor : all events are commands which can be undone, stacked
   and saved.
-  big CLI tools use subcommands to distribute various tasks and pack
   them in "modules", each of these can be implemented with the Command
   pattern (e.g. vagrant)

UML Diagram
-----------

.. image:: uml/uml.png
   :alt: Alt Command UML Diagram
   :align: center

Code
----

You can also find this code on `GitHub`_

Command.php

.. literalinclude:: Command.php
   :language: php
   :linenos:

UndoableCommand.php

.. literalinclude:: UndoableCommand.php
   :language: php
   :linenos:

HelloCommand.php

.. literalinclude:: HelloCommand.php
   :language: php
   :linenos:

AddMessageDateCommand.php

.. literalinclude:: AddMessageDateCommand.php
   :language: php
   :linenos:

Receiver.php

.. literalinclude:: Receiver.php
   :language: php
   :linenos:

Invoker.php

.. literalinclude:: Invoker.php
   :language: php
   :linenos:

Test
----

Tests/CommandTest.php

.. literalinclude:: Tests/CommandTest.php
   :language: php
   :linenos:

Tests/UndoableCommandTest.php

.. literalinclude:: Tests/UndoableCommandTest.php
   :language: php
   :linenos:

.. _`GitHub`: https://github.com/DesignPatternsPHP/DesignPatternsPHP/tree/main/Behavioral/Command
.. __: http://en.wikipedia.org/wiki/Command_pattern
