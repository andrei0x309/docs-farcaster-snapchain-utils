# createCast

`createCast` - creates a cast or a reply to a cast with optional media

### Method signature:

```typescript
	createCast = async ({
		media = [] as Array<{ farcaster: string }>,
		content = '',
		replyTo = undefined as string | {
            hash: string;
            fid: string;
        } | undefined
	}: {
            media?: {
                farcaster: string;
            }[] | undefined;
            content?: string | undefined;
            replyTo?: string | {
                hash: string;
                fid: string;
            } | undefined
        }): Promise<string>
```

Returns a hash of the created cast, or throws an error if creating the cast resulted in an error\


### ReplyTo parameter:

* `string` : the cast is sent to a channel where the string matches the channel id
* `{ hash: string, fid: number }` : is a reply to the cast matching hash for the user matching the fid
* `undefined` : is a cast sent into the home feed

### Media parameter:

`{farcaster: string}[]` : the string is a URL to your media, you might not be able to send more than 2 media attachments as per protocol restrictions, also depending on the client, some URLs might not be rendere,d for exampl,e not all clients will render mp4(like warpcast which will render streams m3u8)
