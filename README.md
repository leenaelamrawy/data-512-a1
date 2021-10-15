# data-512-a1
GOAL OF THE PROJECT:

The goal of this project is to extract historical data about Wikipedia pageviews and pagecounts and to construct a csv file to store the following data:
Pageviews desktop views, Pageviews mobile app views, Pageviews mobile web views, Pagecounts desktop views, Pagecounts mobile views. The data acquired is then aggregated in order to obtain the total number of views for pagecounts and pageviews. The final step of this project is creating a time series chart to visualize the trends in Wikipedia pagecounts and pageviews over time; specifically from December 2007 to August 2021. 

LICENSE OF SOURCE DATA & LINK TO WIKIMEDIA FOUNDATION REST API TERMS OF USE:

https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions

RELEVANT API DOCUMENTATION: 

1) https://www.mediawiki.org/wiki/Wikimedia_REST_API
2) https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts
3) https://wikimedia.org/api/rest_v1/#/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end
4) https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews
5) https://wikimedia.org/api/rest_v1/#/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end


DESCRIPTION OF DATA IN THE FINAL DATAFRAME:

- year: the year portion of the timestamp that represents when a user visited the Wikipedia page

- month: the month portion of the timestamp that represents when a user visited the Wikipedia page

- pagecount_all_views: A summation of the views from both mobile pagecounts and desktop pagecounts

- pagecount_desktop_views: The total number of desktop views for pagecounts

- pagecount_mobile_views: The total number of mobile views for pagecounts

- pageview_all_views: summation of the views from both mobile pageviews and desktop pageviews

- pageview_desktop_views: The total number of desktop views for pageviews

- pageview_mobile_views: The total number of mobile views for pageviews


SPECIAL CONSIDERATIONS WITH DATA: 

1) Data from the Pageview API excludes spiders/crawlers, while data from the Pagecounts API does not.
2) Rows in the data that do not contains data for a specific date/time stamp were filled with zeros to elimiate the NAN values in the final dataset.
3) Multiple file formats: In the first section of this assignment, the data is acquired and convered to 5 json files. After performing all the data manipulation, the final dataframe is saved to a csv.
4) The data for pagecounts and pageviews is available for different time frames. As a result there is no data for certain variables on the time series chart up until certain dates on thes x-axis.

REPRODUCING ANALYSIS:

In order to reproduce this analysis, simply run all the cells in the jupyter notebook in order. This will automatically create the 5 json files, final csv file which will be available in your current directory. Finally, the visualization will appear in the last cell of the notebook.
