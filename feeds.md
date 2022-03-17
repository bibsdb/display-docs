# Feeds

The API supports binding a feed to a slide. This is supported in the admin with the FeedSelector component.

A feed has a FeedSource which is bound to a FeedType, which should be implemented in the API. 

The FeedSource contains secrets related to the feed.

The FeedType supplies functions for fetching data and configuring the Feed.

TODO: Describe in details how to create a new FeedType.
