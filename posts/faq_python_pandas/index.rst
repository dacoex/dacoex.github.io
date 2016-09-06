.. title: Pandas FAQ
.. slug: faq_python_pandas
.. date: 2016-03-03 20:19:28 UTC+01:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text


IO
==

Excel interfacing
----------------------

* Specify number of rows of Excel file to bea read in
    * In Pandas, whats the equivalent of 'nrows' from read_csv() to be used in read_excel()?
        * http://stackoverflow.com/questions/35747476/in-pandas-whats-the-equivalent-of-nrows-from-read-csv-to-be-used-in-read-ex
        
        If you know the number of rows in your Excel sheet, you can use the skip_footer parameter to read the first n - skip_footer rows of your file, where n is the total number of rows.
        Assuming your excel sheet has 100 rows, this line would parse the first 20 rows.::

            data = pd.read_excel(filepath, header=0, parse_cols = "A:D", skip_footer=80)
            
            
DataStructure
===============

DataFrame
-------------

Rename
__________

* [[http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.rename.html#pandas.DataFrame.rename|rename]]
* [[http://stackoverflow.com/questions/19758364/python-rename-single-column-header-in-pandas-dataframe|python: rename single column header in pandas dataframe]]

::

    data.rename(columns={'gdp':'log(gdp)'}, inplace=True)
