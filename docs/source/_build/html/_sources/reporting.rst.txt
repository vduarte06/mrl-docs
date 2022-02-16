===================
4. Creating reports
===================

A MRL report has at least 4 mandatory sections: ``ExamInfo, Identification; Results and Conclusion.``

4.1. Exam Information
---------------------

We start by identifing the exam:


.. code-block:: ruby

    # ExamInfo:
        Equipment: 'Nox';
        Channels: EEG, EMG, PSG, ECG;
        StartDateTime: 1/1/2022;
        EndDatetime: 2/2/2022;
    end

This will allow MRL to access the exam variables

4.2. Patient Identification
---------------------------

MRL will read the patient information from the exam file. 
However, if any identification information is missing in the exam file you will have to fill it in manually as the following example:

.. code-block:: ruby

    #Identification:
        patientName: 'Patient Name';
        Birthdate: '08-06-1992';
        Age: age(this.Birthdate);
        Summary: 'Fumador, hipersonolência diurna';
        PreviousReport: PreviousReport(this);
    end

4.3. Results
------------

The results section is basically a selection of the variables to be shown in the report.
We can group them in categories of findings. Tipical categories of results in a PSG are Respiration, Sleep Architecture, Movement Sleep Disorders, and so on.

This section is usually filled by a sleep technician.

.. code-block:: ruby

    #Results:
        Respiration: IAH, ODI;
        SleepArchitecture: SleepTime, Arousals, SleepPhases;
        LegsvsArousals : correlate(LegMovement, Arousals); 
    end


4.4. Conclusions
----------------

A physician will look at the results and make conclusions.

There is a limited range of conclusions you can make from a PSG exam. 

In the following example we show how a physician can diagnose a patient with Severe Obstructive Sleep Apnea (OSA) and prescribe Continuous Positive Airway Pressure (CPAP) Therapy.

.. code-block:: ruby

    #Conclusions:
        Diagnosis: Diagnosis.OSA.severe;
        Recomendatios: CPAP;
    end


4.5. Appends
------------

It is an optional block where you can add figures, graphs or tables that can help to describe the results

.. code-block:: ruby

    #Appends:
        figure: 'Hipnograma' ipnogram.png;
        graph: 'Arousal vs Limb Movements' [Arousal,PLM];
        table: 'Arousals, Limb Movements e SO2' [Arousals ,PLM, SO2];     
    end

.. autosummary::
   :toctree: generated