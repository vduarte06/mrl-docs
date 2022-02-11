===================
4. Creating reports
===================

A MRL report has at least 4 mandatory sections: ``ExamInfo, Identification; Results and Conclusion.``

4.1. Exam Information
--------------------

We start by identifing the exam:

This will allow MRL to access the exam recording variables

4.2. Patient Identification
--------------------------

MRL will read the patient information from the exam file. 
However, if any identification information is missing in the exam file you will have to fill it in manually as the following example:

.. code-block:: ruby

    #Identification:
        patientName: 'Patient Name';
        Birthdate: '08-06-1992';
        Age: age(this.Birthdate);
        Summary: 'Fumador, hipersonolência diurna';
        PreviousReport: PreviousReport(this);

4.3. Results
-----------

4.3. Conclusion
--------------

.. autosummary::
   :toctree: generated