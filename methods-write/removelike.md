# removeLike

`removeLike` - removes a like

### Method signature:

```typescript
async (hash: string, fid: number): Promise<boolean>
```

* hash: target hash of the cast about to be liked
* fid: fid of the author of that cast
* returns `true` if the like was removed `false` if there was an error

