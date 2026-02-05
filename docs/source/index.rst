Welcome to the CFSDS documentation page!
=========================================

.. image:: ./images/CFSDS.png
   :alt: CFSDS workflow

`The Canadian Fire Spread Dataset <https://www.nature.com/articles/s41597-024-03436-4>`_ (CFSDS) is a comprehensive
wildfire progression dataset that maps the daily spread of large Canadian wildfires (≥ 500 ha) from 2002–2024. Built using
MODIS and VIIRS satellite active fire detections alongside national burned area perimeter data, the dataset estimates the
day-of-burning for each pixel at ~90 m resolution, producing detailed fire growth and spread patterns over time. CFSDS
also includes a rich set of environmental covariates, such as weather, terrain, and vegetation characteristics—supporting
research into wildfire behavior, model development, and improved fire prediction under changing climate conditions.

CFSDS uses **ordinary kriging**, a geostatistical interpolation method that estimates values at locations without direct
observations based on nearby data. It assumes that points closer together are more similar than those farther apart.
Unlike simpler methods such as inverse distance weighting, kriging explicitly models the spatial structure of the data
using a *variogram*, which describes how similarity decreases with distance.

In CFSDS, VIIRS and MODIS hotspots (from FIRMS) are used in the kriging process to reconstruct daily fire spread within
the final fire perimeters provided by NBAC. Hotspot observations are often incomplete due to limited satellite
overpasses or obstruction from smoke and clouds. Kriging fills in these gaps, estimating the most likely burn day for
each pixel based on nearby hotspots, allowing a continuous, high-resolution map of daily fire growth.

Day-of-burning at each pixel was used to identify environmental conditions of burning, such as daily weather, derived
weather metrics, topography, and forest fuel characteristics. This dataset can be used in a broad range of research
and management applications, including retrospective analysis of fire spread, as a benchmark dataset for validating
statistical or machine-learning models, and for forecasting the effects of climate change on fire activity.

Data Availability
-----------------

Processed files are openly available for download on the
`Open Science Framework repository <https://osf.io/f48ry/overview>`_.

This repository provides release notes for all file versions and includes **daily fire growth summaries, fire growth
points, and fire growth rasters**. It also contains an example code repository with sample data, demonstrating a
simplified version of the kriging process and illustrating how each type of provided file was generated.

Citation
--------

When using the data or methods presented here, please cite our work as follows:

Barber, Q. E., Jain, P., Whitman, E., Thompson, D. K., Guindon, L., Parks, S. A., Wang, X., Hethcoat,
M. G., & Parisien, M.-A. (2024). *The Canadian Fire Spread Dataset*. Scientific Data, 11, 764.
https://doi.org/10.1038/s41597-024-03436-4

.. code-block:: bibtex

   @article{Barber2024_CFSDS,
     title={The Canadian Fire Spread Dataset},
     author={Barber, Quinn E. and Jain, Piyush and Whitman, Ellen and Thompson, Dan K. and Guindon, Luc
             and Parks, Sean A. and Wang, Xianli and Hethcoat, Matthew G. and Parisien, Marc-Andr{\'e}},
     journal={Scientific Data},
     volume={11},
     pages={764},
     year={2024},
     doi={10.1038/s41597-024-03436-4}
   }

Documentation
-------------

For users interested in a more in-depth understanding, please refer to the
`CFSDS documentation <https://cfsds-docs.readthedocs.io/en/latest/index.html>`_.

Check out the :doc:`usage` section for further information, including
how to :ref:`installation` the project.

.. note::

   This project is under active development.

Contents
--------

.. toctree::

   usage
   api
   kriging
