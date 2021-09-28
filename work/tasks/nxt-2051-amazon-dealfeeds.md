# NXT-2051 - dealfeed for Amazon

## questions:
- are we returning items by asin one-by-one or we need to return them all?
- do we need to return multiple items by query? (by brand or something)
- what traffic we're expecting? does it worth writing it stateless for now? (and just use ram cache)
- 
## suggestions:
- use separate endpoint to retrieve item and to download items from dealfeed (multiple instances might request too many times...)
- extract models
  - it might be cool to loose the intermediate `OriginalDealFeedItem`
  - separate classes with static factory methods - fromCSV, from 
- use md5 to check if we have already anything in cache (and if we need to download the csv)
- we need to remove the items from cache which are not in the dealfeed anymore, right?
