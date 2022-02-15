==================
1. Getting started
==================
To introduce MRL, lets create a simple MRL report for a Polisonomgraphy study (PSG) as follows:

1. Create a file with the extension ``.mrl``
2. add the following code. Make sure you have the file name correctly linked to the report in order to access the exam results within your report.
3. Compile the report. 

Example:

.. code-block:: ruby

    from utils import Diagnosis;
    Identification:
        patientName: 'Patient Name';
        Birthdate: '01-01-2000';
    end

    ExamInfo:
        name: 'exam.edf'
        type: 'PSG'
    end

    Results:
        Respiration: IAH, ODI;
    end

    Conclusions:
        Diagnosis: Diagnosis.OSA.severe;
        Recomendatios: CPAP;
    end


The result will be a beaultiful, objective and uniformized PSG report.



