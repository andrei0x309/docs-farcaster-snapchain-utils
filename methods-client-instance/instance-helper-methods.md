# Instance helper methods

### changeSigner

#### Description:

It helps you to change the signer (user) of the instance.

#### Method Signature:

```typescript
	changeSigner = ({
        PK,
        FID,
    }: {
        PK: string,
        FID: number,
    }): boolean => {
```

### changeNode

#### Description:

It helps you to change the node of the instance.

#### Method Signature:

```typescript
changeNode = ({
		NODE_URL,
		NODE_USER,
		NODE_PASS,
        NEYNAR_API_KEY,
	}: {
        NODE_URL?: string,
        NODE_USER?: string,
        NODE_PASS?: string,
        NEYNAR_API_KEY?: string,
	}): void 
```

### getCurentFID

#### Description:

Gets the current FID of the instance

#### Method Signature:

```typescript
 getCurentFID = (): number
```

### getCurentNode

#### Description:

Gets the current node of the instance

#### Method Signature:

```typescript
 getCurentNode = (): string
```

### getCurrentSignerPk

#### Description:

Gets the current PK of the signe

#### Method Signature:

```typescript
getCurrentSignerPk = (): string 
```

### getCurrentNeynarApiKey

#### Description:

Gets the current Neynar API key

#### Method Signature:

```typescript
getCurrentNeynarApiKey = (): string
```
