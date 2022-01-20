=================
3. Analysing data
=================

As shown in the section ``2.2. Functions.``, we can link MRL to Python functions.

Besides the custom functions implementation, data processing libraries like Numpy and Scipy are linked by default.

This can be very useful to analise the exam results in a very convinient way.

For example. Lets suppose we found that the patient had multiple arousals and also multiple episodes of periodic leg movements. 
We could use the function ``numpy.correlate`` to check if this 2 finds are actually correlated, as shown bellow:

.. code-block:: ruby

    arousalsVsLegMovements = correlate(Arousals, LegMovements)

Notice that the variables ``Arousals`` and ``LegMovements`` are imported from the exam file.

Check out Numpy documentation (https://numpy.org/) for more information on data analysis.

