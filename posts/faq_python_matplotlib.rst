.. title: Q&A: Python / matplotlib
.. slug: faq_python_mpl
.. date: 2016-03-04 20:19:08 UTC+01:00
.. tags: faq, python, code, snippets, stackoverflow, templates, coding, lessons-learned, matplotlib
.. category: knowledge-base
.. link:  Frequently asked questions on Python standard plotting library matplotlib
.. description: 
.. type: text


Axis
=============

* get axis limits
    * http://stackoverflow.com/a/3681015 from `set axis limits in matplotlib pyplot <http://stackoverflow.com/questions/3645787/set-axis-limits-in-matplotlib-pyplot>`_::
    
        ylim( ax1.get_ylim() )  

* multiple axes
    * simple, 2 y-axis scales: `two_scales <http://matplotlib.org/examples/api/two_scales.html>`_
    * 3 differnt y-axis scales: `multiple_yaxis_with_spines <http://matplotlib.org/examples/pylab_examples/multiple_yaxis_with_spines.html>`_
* date axis
    * `finance_demo <http://matplotlib.org/examples/pylab_examples/finance_demo.html>`_

Ticks
-----------
* General tick configuration    
    * `major_minor_demo1 <http://matplotlib.org/examples/pylab_examples/major_minor_demo1.html>`_
    * `major_minor_demo2 <http://matplotlib.org/examples/pylab_examples/major_minor_demo2.html>`_
    * `Controlling figure aesthetics <http://stanford.edu/~mwaskom/software/seaborn/tutorial/aesthetics.html>`_
* Define interval for date axis
    * See also:
        * `How to set date tick labels on x axis, only for given points on matplotlib <http://stackoverflow.com/questions/12857683/how-to-set-date-tick-labels-on-x-axis-only-for-given-points-on-matplotlib>`_
        
* Ticks placement
    * `matplotlib: draw major tick labels under minor labels <http://stackoverflow.com/questions/17718827/matplotlib-draw-major-tick-labels-under-minor-labels>`_
        * places days below hours...

    ::
    
        xax.set_tick_params(which='major', pad=15)



    .. code-block:: python
    
        # from: http://stackoverflow.com/q/12857683
        monthsLoc = matplotlib.dates.MonthLocator()
        daysLoc = matplotlib.dates.DayLocator(interval=1)
        ax.xaxis.set_major_locator(monthsLoc)
        ax.xaxis.set_minor_locator(daysLoc)


Markers
=============


Filling & Highlighting
==========================

* `api example code: span_regions.py <http://matplotlib.org/examples/api/span_regions.html?highlight=facecolor%20axhline>`_
    * Illustrate some helper functions for shading regions where a logical mask is True
    
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
    

* Conditional highlight
    * `collections.BrokenBarHCollection.span_where not working with pandas timeseries <https://github.com/matplotlib/matplotlib/issues/3872>`_
    
    