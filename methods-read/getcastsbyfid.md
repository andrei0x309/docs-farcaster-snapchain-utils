# getCastsByFid

`getCastsByFid` - gets cast using a fid

### Method signature:

```typescript
    getCastsByFid = async ({
		fid,
		itemsPerRequests = 10,
		fromTimestamp = 0,
		toTimestamp = Date.now(),
        delayBetweenRequests = 0,
        excludeCastRemoveMessages = true,
        onlyIncludeRemoveMessages = false,
        maximumCastsFetched = 0,
        fetchUntilNoDataLeft= false,
	}: {
		fid: number,
		itemsPerRequests?: number,
		fromTimestamp?: number,
		toTimestamp?: number,
        delayBetweenRequests?: number,
        excludeCastRemoveMessages?: boolean,
        onlyIncludeRemoveMessages?: boolean,
        maximumCastsFetched?: number
        fetchUntilNoDataLeft?: boolean
	}): Promise<{
            casts: {
                hash: string;
                fid: number | undefined;
                cast: CastAddBody | undefined;
                timestamp: number;
                fullMessageData: MessageData | undefined;
            }[];
        } | null>
```

### Parameters



* `fid` - fid to get casts from
* `itemsPerRequests` - how many items per request, max limited by node to a maximum of 100
* `fromTimestamp` - timestamp from which to get casts
* `toTimestamp` - timestamp until when to get casts
* `delayBetweenRequests` - delay between requests ( can help prevent rate limits or node load , default is 0, which means no delay)
* `excludeCastRemoveMessages` - don't include delete cast messages
* `onlyIncludeRemoveMessages` - only include deleted cast messages
* `maximumCastsFetched` - stop when this number is reached
* `fetchUntilNoDataLeft` - this must be set to `true` if you want to make more than **one** request, and only exit when **one** of the conditions is satisfied or **no data is left**
