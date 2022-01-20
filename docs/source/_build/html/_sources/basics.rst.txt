=============
2. MRL Basics
=============

2.1. Variables
--------------

When an exam is imported, multiple variables will be availabe in the environment of MRL.
E.g. if we want to know the Apnea/Hipopnea Index (AHI) we can simply state AHI to access this variable.

We can also create our own variable asignments, as shown in the following exame:

.. code-block:: javascript

    arg = 1;
    functionOutput = someFunctionOutput(arg);

2.2. Functions
--------------

MRL doenst support general purpose programming but allows the user to import functions implemented in other languages. 

MRL ships with Python integration.
Python was chosen to be the default language because it has great libraries for signal processing and is easy to learn.

In summary: functions must be implemented in Python and then connected to MRL. They will send it to python as pipe message.

.. note::

   Functions must be declared in a file with the extension ``.fmrl``

In the following example we declared a function ``getAge(date)`` and connect we connect it to MRL.

.. code-block:: javascript

    function getAge(date) -> call python_module.get_age date;


2.3. Objects
------------

The concept of objects is usefull for programmers who are integrating the language into a system. 
A healthcare professional writing a report doesn't need to worry about the concept of objects but will be able to take advantage of this abstraction while writing reports.

Objects are represented in a simple ``key:value`` form. E.g.

.. code-block:: ruby

    Person:
        name: 'Patient Name';
        Birthdate: '01-01-2000';

The propeties of objects can be accessed with dot.
`` Person.name ``

The reserved word ``this`` refers to the current object while constructing an object.. E.g.

.. code-block:: ruby

    PatientIdentification:
        name: 'Patient Name';
        Birthdate: '01-01-2000';
        ...
        previousReports: getPreviousReports(this);

In the example above the properties of the object ``PatientIdentification`` will be used to get the previous reports of that patients using a function.

.. autosummary::
   :toctree: generated