# S4G Shooting Tracker

![](https://img.shields.io/badge/app%20status-stable-green.svg) ![](https://img.shields.io/badge/Dependencies-none-green.svg)

## Overview

> A mass shooting is when four or more people are shot in an event, or related series of events, likely without a cooling off period.

[Shooting Tracker](http://www.shootingtracker.com), is a website built by members of a Reddit forum supporting gun control called [GunsAreCool](https://www.reddit.com/r/GunsAreCool/). The site aggregates (via crowdsourcing) news stories about shooting incidents — of any kind — in which four or more people are reported to have been either injured or killed.

Using this data as a starting point, this app uses Splunk to examine a range of datasets - from gun control to gun deaths - to examine the topic futher. 

## Caveats

As with all scientific analyses, the sample collection methodology is very important. I cannot confirm the accuracy of these datasets. Do your own due dilligence.

In the spirit of transparency you should be aware that:

* [Shooting Tracker](http://www.shootingtracker.com) crowdsources data. [Problems have been identified with field definitions](http://www.nationalreview.com/article/427985/media-mass-shootings-count-misleading) - for example, what constitues a wounded victim. You should make your own conclusions as to wether this tolerance is acceptable.

* [Mother Jones](http://www.motherjones.com/politics/2012/12/mass-shootings-mother-jones-full-data) is arguably somewhat more reliable than [Shooting Tracker](http://www.shootingtracker.com) - they claim the data is being used by academic researchers, legislative aides, and law enforcement officials.  As Splunk only allows `MAX_DAYS_AGO<=10951` the data set in this repository only used data from 01/Jan/1987 (4 records omitted).

* Some of the datasets used for lookups are outdated - generally because more recent data is unobtainable. The timeline of each dataset is cited below for your reference.

## Data Sources

### Indexed

* [Shooting Tracker](http://www.shootingtracker.com) - mass shootings [2013 - present]
* [Mother Jones](http://www.motherjones.com/politics/2012/12/mass-shootings-mother-jones-full-data) - mass shootings [1982 - present]

### Lookups

* [The National Enquirer](http://www.nationaljournal.com/s/53345/states-with-most-gun-laws-see-fewest-gun-related-deaths) - gun deaths, gun control laws [2013]
* [Wikipedia](https://simple.wikipedia.org/wiki/List_of_U.S._states_by_population) - population [2013]
* [Simple Maps](http://simplemaps.com/resources/us-cities-data) - cities location (lat, lon) 
* [Kaiser Family Foundation](http://kff.org/other/state-indicator/median-annual-income/#) - median state household income [2014]
* [Kaiser Family Foundation](http://kff.org/other/state-indicator/firearms-death-rate-per-100000/#) - gun deaths / 100k (US) [2013]
* [The Guardian](http://www.theguardian.com/news/datablog/2012/jul/22/gun-homicides-ownership-world-list#data) - Gun ownership / homicides (world) [2012]
* [Demographic Data](http://demographicdata.org/facts-and-figures/gun-ownership-statistics/) - gun ownership + crime stats [2010 - 2013 misc]

## Installation

This package has been designed so that even those new to Splunk can get up and running in less than 10 minutes.

### Guide

1. Download and install the latest version of Splunk, for free (index up to 500mb day).
2. Copy this package (everything in s4g-shooting_tracker) to `$SPLUNK$/etc/apps`
3. Start Splunk `$SPLUNK$/bin/./splunk start`
4. The app should now be running at http://localhost:8000/en-US/app/s4g-shooting_tracker/

### Pull requests

I welcome all external contributions to help imporove this app. [You can find this repository on Github](https://github.com/himynamesdave/s4g-shooting_tracker).

## About

The project was built by the [Splunk4Good team](http://splunk4good.com/) in a few spare hours. You should check out some of our other projects too, [like when we compared Gas and Electric cars](http://connectedcars.splunk4good.com/).

You can also [submit your own idea for an open data project](https://docs.google.com/a/dgwd.co/forms/d/1oZerAAoZClkqqtNSCz6qhej-jKBU5NgUZCgEJ8BB20Q/viewform?edit_requested=true).

Made with <3 by [Splunk](http://www.splunk.com).