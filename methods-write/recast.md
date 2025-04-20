# recast

`recast` - recast a cast ( a recast is a form of super-like )

### Method signature:

```typescript
async (hash: string, fid: number): Promise<boolean>
```

* hash: target hash of the cast about to be recasted
* fid: fid of the author of that cast
* returns `true` if the cast was recasted `false` if there was an error

