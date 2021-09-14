.. sectionauthor:: Jonathon Love

============================
``OptionControl`` (abstract)
============================

**Inherits from** |ui_basecontrol|_

**This control type is abstract and can not be used directly.**

This is the abstract base of all controls that can be bound to an
option. These types of controls allow a user to see and/or set the value
of an option that has been defined in the ``*.a.yaml``.

Properties
----------

In addition to any inherited properties, an ``OptionControl`` supports:

+------------+-----------------------------------------+------------------+
| Property   | Description                             | Form             |
+============+=========================================+==================+
| ``name``   | Sets the unique name for the control.   | Unique string    |
|            | If ``optionName`` is not defined        | (or option name) |
|            | ``name`` will be used to data-bind to   |                  |
|            | an option.                              |                  |
+------------+-----------------------------------------+------------------+
| |optNme|   | Sets the name of the option to which    | defined option   |
|            | the control is to be data bound. If     | name             |
|            | this property is omitted and ``name``   |                  |
|            | property is used instead.               |                  |
+------------+-----------------------------------------+------------------+
| |optPrt|   | Sets the name of the sub-option to      | defined option   |
|            | which the control is to be data bound.  | part name        |
|            | Some controls don’t bind to a whole     |                  |
|            | option but only to part. For example,   |                  |
|            | a ``RadioButton`` binds to a sub-option |                  |
|            | of the underlying ``List`` option (see  |                  |
|            | `here <ui_radiobutton.html>`__ for an   |                  |
|            | example.                                |                  |
+------------+-----------------------------------------+------------------+
| ``label``  | Sets the text to be displayed by the    | string           |
|            | control’s label. NOTE: not all controls |                  |
|            | have labels. In the circumstance that a |                  |
|            | control does not have a label, a        |                  |
|            | defined ``label`` property is ignored.  |                  |
+------------+-----------------------------------------+------------------+
| ``enable`` | Sets a data-binding string to control   | string           |
|            | the enable state of the control.        |                  |
+------------+-----------------------------------------+------------------+

Further Details
~~~~~~~~~~~~~~~

``enable``
^^^^^^^^^^

This property is what’s called a ‘data-binding’. Data-binding is where
the value of a particular property is bound to the value of another UI
control. When the value of the control changes, so does the respective
property value. For example we may want to bind to the value of a
``CheckBox`` (TRUE/FALSE) to the enabling/disabling feature of a
``TextBox``. This would be achieved by specifying the name of the
control to which you would like to bind inside of parentheses (or
brackets).

.. code-block:: yaml

   - type: CheckBox
     name: pcEqGr
     label: Cut points for
     style: inline
     verticalAlignment: center
     children:
       - type: TextBox
         name: pcNEqGr
         label: ""
         suffix: equal groups
         format: number
         inputPattern: "[0-9]+"
         enable: (pcEqGr)

In the above example, the ``TextBox`` named ``pcNEqGr`` would enable
when the ``CheckBox`` named ``pcEqGr`` is checked.

``label``
^^^^^^^^^

The ``label`` property of an ``OptionControl`` serves only to override
the ``title`` property of the underlying option. If the ``label``
property is not defined, the control will use the ``title`` property of
the underlying option. This results in the UI control definition being
minimal, only describing information when necessary.

*Option Definition*

.. code-block:: yaml

   - name: descStats
     title: Descriptive statistics
     type: Bool
     default: false
     description:
         R: >
           `TRUE` or `FALSE` (default), provide descriptive statistics

*UI Control Definition*

.. code-block:: yaml

   - type: CheckBox
     name: descStats

Events
------

+------------+---------------------------------------------------------+
| Event      | Description                                             |
+============+=========================================================+
| *change*   | Fires when the value of the control has changed.        |
+------------+---------------------------------------------------------+
| *changing* | Fires when the value of the control is about to change. |
+------------+---------------------------------------------------------+

Controls
--------

Below is a list of controls that inherit from ``OptionControl``.

.. toctree::
   :titlesonly:

   ui_textbox
   ui_checkbox
   ui_radiobutton
   ui_combobox
   ui_label
   ui_listbox
   ui_variablelabel
   ui_termlabel

.. ----------------------------------------------------------------------

.. |ui_basecontrol| replace:: ``BaseControl``
.. _ui_basecontrol: ui_basecontrol.html

.. |optNme| replace:: ``optionName``
.. |optPrt| replace:: ``optionPart``
