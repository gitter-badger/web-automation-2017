# The Hitchhiker's Guide to the Web Automation

## Disclaimer

I'm an enthusiast and not a professional user of all mentioned products, feel free to send corrections to [GitHub repository](https://github.com/peterdemin/web-automation-2017).

## Purpose

This document covers existing web automation projects, services, and platforms.

It's targeted to people who just started automating or want to switch from bunch shell scripts to a more solid foundation.

## Overview

Simple web automation scripts can be written in bash or python.
However, this approach fails short in the face of network failures, different ways of delivering notifications and need to transform data.

A number of solutions try to remove boilerplate from web automation tasks.
These solutions provide:

* A foundation for making network requests and connecting them to actions.
* Collection of recipes for solving common problems built on top of the foundation.

The common examples of web automation tasks include:

* Fetching weather prediction
* Aggregating digest of social network updates
* Building complex reminders

The year of technology birth can be said to be 2011, when [Zapier](https://zapier.com) launched on [Startup Weekend](http://startupweekend.org/).
Two years later a number of open source alternatives emerged, most notably:

* [Huginn](https://github.com/huginn/huginn) - Multi-tenant web solution written and extendable in Ruby.
* [Trigger-Happy](https://trigger-happy.eu/) - Similar solution, but with much fewer recipes and written as a reusable Django application.

And some paid services, with slightly different targeting:

* [If This Than That](ifttt.com) - targeted on IoT and mobile devices.
* [Bip.io](https://bip.io) - both open source and paid hosted solutions.

Also worth mentioning open source solutions:

* [Home Assistant](https://home-assistant.io/) - Platform for home automation with web automation capabilities.
* [Kibitzr](https://kibitzr.github.io) - Command-line utility extendable with Python and Bash scripts.

## Browser automation

State of the art library for browser automation is [Selenium](selenium-python.readthedocs.io).
It supports most popular platforms and browsers.
However it's primary use case is web applications testing, it's tedious in configuration and has a high entry barrier.

Browser automation complexity is an effect of following inherent properties of the task:

* Interactions must be defined in terms of markup, which is rarely composed with this thought.
* HTML structure is rigid and changes often.
* Browsers communicate through network inheriting all its failures and unreliability.

But in many cases, it's the only option to extract content from the remote system.
Number of paid solutions exists aiming to simplify web scrapping:

* [Import.io](https://import.io) - turns websites into structured APIs.
* [Portia](https://scrapinghub.com/portia/) - lets you scrape web sites without any programming knowledge required.
* [Kimono](https://www.kimonolabs.com/) - manual tools for web page extraction.

Libraries for parsing and scraping web pages:

* [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/) - parses malformed HTML.
* [Scrapy](https://scrapy.org/) - fast and powerful scraping and web crawling framework.

## Zapier 

[Zapier](https://zapier.com) is the most popular web automation app.
Zapier tasks are called Zaps.

A Zap is a blueprint for a task you want to do over and over.
In words, a Zap looks like this: "When I get a new thing in A, do this other thing in B."
The first part is the Trigger and the second part is the Action.

Zapier supports hundreds of apps.
You can mix and match triggers and actions to automate just about anything.

An example might be "When I get a new entry from a Wufoo form, create a new lead in Salesforce."
Zapier thrives for granularity.
User can pick what fields from the trigger service should go to the action service.
For instance, the phone number from Wufoo form should be the work phone of the new Salesforce lead.

## Huginn

[Huginn](https://github.com/huginn/huginn) is the closest alternative to Zapier.
It's a multi-tenant system for building agents that perform automated online tasks.

Huginn started in 2013 and have built a broad community with hundreds of contributors and collected thousands of stars.

Huginn organizes directed graphs of events passing between different types of agents.
There are more than 50 types of agents.
The user builds pipelines of predefined agent types inside the browser.

Agents are written in Ruby language and are stored inside Huginn's subdirectory.

For operating Huginn requires MySQL database and Nginx server.
Installation is pretty involved, but well documented.

## Trigger Happy

[Trigger-Happy](https://trigger-happy.eu/) is similar to Huginn in design, but is implemented as a reusable Django application. Community is smaller, and project don't see much attention these days.
