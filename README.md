# The Hitchhiker's Guide to the Web Automation

## Purpose

This document covers existing web automation projects, solutions and platforms.

It's targeted to people who just started automating or want to switch from shell scripts to some foundation.

## Overview

Simple web automation scripts can be written in bash, or python.
However this approach fails short in the face of network failures, different ways of delivering notifications and need to transform data.

Number of solutions tries to remove boilerplate from web automation tasks.
These solutions provide:

* A foundation for making network requests and connecting them to actions.
* Collection of recipies for solving common problems built on top of the foundation.

The common examples of web automation tasks include:

* Fetching weather prediction
* Aggregating digest of social network updates
* Building complex reminders

The year of technology birth can be said to be 2011, when [Zapier](https://zapier.com) launched on [Startup Weekend](http://startupweekend.org/).
Two years later number of open source alternatives emerged, most notably:

* [Huginn](https://github.com/huginn/huginn) - Multi-tenant web solution written and extendable in Ruby.
* [Trigger-Happy](https://trigger-happy.eu/) - Similar solution, but with much less of recipies and written in Python.

And some paid services, with slightly different targeting:

* [If this than that](ifttt.com) - targeted on IoT and mobile devices.
* [bip.io](https://bip.io) - both open source and paid hosted.

Also worth mentioning open source solutions:

* [Home Assistant](https://home-assistant.io/) - Platform for home automation with web automation capabilities.
* [Kibitzr](https://kibitzr.github.io) - Command-line utility extendable with Python and Bash scripts.

# Browser automation

State of the art library for browser automation is [Selenium](selenium-python.readthedocs.io).
It supports most popular platforms and browsers.
However it's primary use case is web applications testing, it's tedious in configuration and has a high entry barrier.

Browser automation complexity is an effect of following inherent properties of the task:

* Interactions must be defined in terms of markup, which is rarely composed with this thought.
* HTML structure is rigid and changes often.
* Browsers communicate through network inheriting all it's failures and unreliability.

But in many cases it's the only option to extract content from remote system.
Number of paid solutions exists aiming to simplify web scrapping:

* [Import.io](https://import.io) - turns websites into structured APIs.
* [https://scrapinghub.com/portia/](Portia) - lets you scrape web sites without any programming knowledge required.
* [Kimono](https://www.kimonolabs.com/) - manual tools for web page extraction.

Libraries for parsing and scraping web pages:

* [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/) - parses malformed HTML.
* [Scrapy](https://scrapy.org/) - fast and powerful scraping and web crawling framework.
