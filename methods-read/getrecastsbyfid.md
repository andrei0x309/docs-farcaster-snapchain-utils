# getRecastsByFid

`getRecastsByFid` - gets recasts using a fid ( excludes like reaction type)

### Method signature:

```typescript
getRecastsByFid = async ({
		fid,
		itemsPerRequests = 10,
		fromTimestamp = 0,
		toTimestamp = Date.now(),
        delayBetweenRequests = 0,
        fetchUntilNoDataLeft = false,
        maximumReactionsFetched = 0
	}: {
		fid: number,
		itemsPerRequests?: number,
		fromTimestamp?: number,
		toTimestamp?: number,
        delayBetweenRequests?: number,
        fetchUntilNoDataLeft?: boolean,
        maximumReactionsFetched?: number
	}): Promise<{
            hash: string;
            fid: number | undefined;
            reaction: {
                type: ReactionType | undefined;
                targetCastId: CastId | undefined;
                targetUrl: string | undefined;
            };
            timestamp: number;
        }[]>
```

### Parameters



* `fid` - fid to get reactions from
* `itemsPerRequests` - how many items per request, max limited by node to a maximum of 100
* `fromTimestamp` - timestamp from which to get data
* `toTimestamp` - timestamp  until when to get data
* `delayBetweenRequests` - delay between requests ( can help prevent rate limits or node load , default is 0, which means no delay)
* `maximumReactionsFetched` - stop when this number is reached
* `fetchUntilNoDataLeft` - this must be set to `true` if you want to make more than **one** request, and only exit when **one** of the conditions is satisfied or **no data is left**
