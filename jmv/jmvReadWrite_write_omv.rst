.. sectionauthor:: `Sebastian Jentschke <https://www.uib.no/en/persons/Sebastian.Jentschke>`_

===========================================================
Write ``.omv``-files to be used with jamovi (``write_omv``)
===========================================================

Description
-----------

    Write ``.omv``-files to be used with the statistical spreadsheet `jamovi <www.jamovi.org>`_.

Usage
-----

.. code-block:: R

   jmvWrite(
     dtaFrm = NULL,
     fleNme = "",
     retDbg = FALSE)

Arguments
---------

+------------+-----------------------------------------------------------------------------------+
| ``dtaFrm`` | Data frame to be exported (default = NULL)                                        |
+------------+-----------------------------------------------------------------------------------+
| ``fleNme`` | Name / position of the output file to be generated ("FILENAME.omv"; default = "") |
+------------+-----------------------------------------------------------------------------------+
| ``retDbg`` | Whether to return a list with debugging information (see Value; default: FALSE)   |
+------------+-----------------------------------------------------------------------------------+

Details
-------

     jamovi has a specific measurement level / type ``ID`` (in addition to the "standard" ones ``Nominal``, ``Ordinal``, and ``Continuous``). ``ID`` is used
     for columns that contain some form of ID (e.g., a participant code). In order to set a variable of your data frame to ``ID``, you have to manually set an
     attribute ``jmv-id`` (e.g., ``attr(dtaFrm$column, "jmv-id") = TRUE``).

Output
------

     A results object (list; only if ``retDbg`` is ``TRUE``), containing the meta data (``mtaDta``, ``metadata.json`` in the ``.omv``-file), the extended data
     (``xtdDta``, ``xdata.json`` in the ``.omv``-file) and the original data frame (``dtaFrm``).

Examples
--------

.. code-block:: R
    
   library(jmvReadWrite);
     
   # use the data set "ToothGrowth" and, if it exists, write it as jamovi-file using write_omv()
   data("ToothGrowth");
   fleOMV <- paste0(tempfile(), ".omv");
   # typically, one would use a "real" file name instead of tempfile(), e.g., "Data1.omv"
   dtaDbg = write_omv(ToothGrowth, fleOMV, retDbg = TRUE);
   print(names(dtaDbg));
   # the print-function is only used to force devtools::run_examples() to show output -> "mtaDta" "xtdDta" "dtaFrm"
   # returns a list with the metadata (mtaDta, e.g., column and data type), the extended data (xtdDta, e.g., variable
   # lables), and the data frame (dtaFrm)
   # the purpose of these variables is merely for checking (understanding the file format) and debugging
     
   # check whether the file was written to the disk, get the file information (size, etc.) and delete the file afterwards
   print(list.files(dirname(fleOMV), basename(fleOMV)));
   # -> "file[...].omv" ([...] contains a random combination of numbers / characters
   print(file.info(fleOMV)$size);
   # -> 2199 (size may differ on different OSes)
   unlink(fleOMV);
