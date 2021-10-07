# README

## Goal of this Project

The goal of this project is to create and analyze a dataset of monthly traffic on English Wikipedia since January 2008.

## Licenses

The source data is licensed under the [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/) and [GFDL](https://www.gnu.org/licenses/fdl-1.3.html) licenses.

The Wikimedia Foundation REST API terms of use may be found [here](https://www.mediawiki.org/wiki/Wikimedia_REST_API#Terms_and_conditions)

## API Documentation

Desktop and mobile web traffic data from 12/2007 to 7/2016 is accessed via the Legacy Pagecounts API. Its documentation is available [here](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts).

Desktop, mobile web, and mobile app traffic data from 7/2015 to the present is accessed via the Pageviews API. Its documentation is available [here](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews).

Sample code for API calls available [here](https://public.paws.wmcloud.org/User:Jtmorgan/data512_a1_example.ipynb) was used largely intact in this analysis to perform the API calls.

## Data File Format

This repository contains six data files.

The following files are JSON formatted and contain the raw output of the API calls.

* pagecounts_desktop-site_200712-201607.json
* pagecounts_mobile-site_200712-201607.json
* pageviews_desktop_201507-202108.json
* pageviews_mobile-app_201507-202108.json
* pageviews_mobile-web_201507-202108.json

The sixth file is a CSV file, en-wikipedia_traffic_200712-202108.csv, which contains the following columns:

* year: The year this data was recorded
* month: The month this data was recorded
* pagecount_all_views: Total views, both desktop and mobile, from the Pagecount API
* pagecount_desktop_views: Desktop views, from the Pagecount API
* pagecount_mobile_views: Mobile (web) views, from the pagecount API (no data available prior to 10/2014)
* pageview_all_views: Total views, desktop, mobile web, and mobile app, from the Pageview API
* pageview_desktop_views: Desktop views, from the Pageview API
* pageview_mobile_views: Mobile web and app views, from the Pageview API.

## Special Considerations

* Pageviews and Pagecounts differ in that Pagecounts cannot filter self-reported bots such as web crawlers. Therefore, in the months where the two APIs overlap, the Pagecount view tally is higher.
* Mobile access data is not available prior to October 2014.

