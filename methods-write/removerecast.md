# removeRecast

`removeRecast` - remove a recast from a cast ( a recast is a form of super-like )

### Method signature:

```typescript
async (hash: string, fid: number): Promise<boolean>
```

* hash: target hash of the cast that will have the recast removed
* fid: fid of the author of that cast
* returns `true` if the recast was removed`false` if there was an error

