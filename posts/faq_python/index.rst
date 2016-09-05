.. title: Q&A: Python
.. slug: faq_python
.. date: 2016-03-03 20:19:08 UTC+01:00
.. tags: faq, python, code, snippets, stackoverflow, templates
.. category: coding, python, knowledge-base
.. link:  Frequently asked questions on Python standard library modules
.. description: 
.. type: text


.. contents:: Table of Contents
   :depth: 2
.. section-numbering::


Compilation of faq items.


.. TEASER_END


Learning from Community
------------------------

* if stuck
    * make a reproducible self-contained example
        * isolates problem
        * helps yourself and others to understand issue
    


Datetime
-----------

* `Adding 5 days to Date in python <http://stackoverflow.com/questions/6871016/adding-5-days-to-date-in-python>`_

.. code-block:: python

    date_1 = datetime.datetime.strptime(start_date, "%m/%d/%y")
    end_date = date_1 + datetime.timedelta(days=10)


* `In a matplotlib plot, can I highlight specific x-value ranges? <http://stackoverflow.com/questions/8270981/in-a-matplotlib-plot-can-i-highlight-specific-x-value-ranges>`_

.. code-block:: python

    import matplotlib.pyplot as plt

    plt.plot(range(10))
    plt.axvspan(3, 6, color='red', alpha=0.5)
    plt.show()


    # with datetime

    import matplotlib.pyplot as plt
    import matplotlib.dates as mdates
    import datetime as dt

    t = mdates.drange(dt.datetime(2011, 10, 15), dt.datetime(2011, 11, 27),
                      dt.timedelta(hours=2))
    y = np.sin(t)

    fig, ax = plt.subplots()
    ax.plot_date(t, y, 'b-')
    ax.axvspan(*mdates.datestr2num(['10/27/2011', '11/2/2011']), color='red', alpha=0.5)
    fig.autofmt_xdate()
    plt.show()
    

matplotlib
=========================
    
:doc:`faq_python_mpl`