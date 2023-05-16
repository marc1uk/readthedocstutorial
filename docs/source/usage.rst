Describing Programming Objects
==============================

.. _DescribingObjects:

Console commands
----------------

Each time you start a new shell process (such as by logging in), you will need to source the Setup script to configure the environment:

.. code-block:: console

   user@host $ . Setup.sh

Describing C++ classes
----------------------

Class descriptions are created with a fairly intuitive struct-like syntax as follows:

.. cpp:class:: Tool
   An abstract base class that all User Tools must derive from

.. cpp:class:: DemoTool : public Tool

   A demonstration tool, showing minimal overrides that must be defined by the user.
   
.. cpp:function:: bool DemoTool::Initialise(std::string configfile, DataModel& datamodel)

   The :cpp:func:`DemoTool::Initialise` function configures the demonstration tool, reading the contents of the :cpp:var:`DemoTool.Initialise.configfile`
   into a :cpp:class:`Store` object, which can hold any kind of ASCII-representable data type.
   The input :cpp:class`DataModel` is used to initialise the :cpp:member:`m_data` member. All :cpp:class:`Tool` instances share the same :cpp:class:`DataModel`
   instance, so this may be used as a means to pass data between Tools. 
   
   :param configfile: a text file containing configuration option key-value pairs
   :type configfile: std::string
   :parameter datamodel: a reference to the ToolChain DataModel, shared by all Tools.
   :type configfile: DataModel&
   :returns: a boolean indicating whether errors were encountered during Initialisation
   :throws: none. Any unhandled exceptions thrown by the Tool will be caught by the ToolChain, which may be configured to terminate on or ignore such occurrances.
   
.. cpp:member:: DataModel DemoTool::m_data
   


Describing functions
--------------------
you can similarly describe functions such as the ``lumache.get_random_ingredients()`` function:

.. autofunction:: lumache.get_random_ingredients

Give a description of the function here, such as noting that the ``kind`` parameter should be either ``"meat"``, ``"fish"``,
or ``"veggies"``. Otherwise, :py:func:`lumache.get_random_ingredients`
will raise an exception.

.. autoexception:: lumache.InvalidKindError

For example:

>>> import lumache
>>> lumache.get_random_ingredients()
['shells', 'gorgonzola', 'parsley']

