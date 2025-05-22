---
icon: bullseye-arrow
---

# Quickstart

### Install

{% tabs %}
{% tab title="bun" %}
```
bun add farcaster-snapchain-utils
```
{% endtab %}

{% tab title="yarn" %}
{% code overflow="wrap" %}
```
yarn add farcaster-snapchain-utils
```
{% endcode %}
{% endtab %}
{% endtabs %}

### Usage  - read-only with the public node from Pinata

<pre class="language-typescript"><code class="lang-typescript"><strong>import { SnapChainClient } from 'farcaster-snapchain-utils'
</strong>
const client = SnapChainClient();

// client.method... -> must be a read method only, or it will throw an error

</code></pre>

### - read-write with your node

```typescript
import { SnapChainClient } from 'farcaster-snapchain-utils'

const userFid = 1791;
// Example signer must be a valid signer of the FID
const signer = "0x222ab147ccbaa2dc660717f28ea4aaeea13b93fe9df297669efdd12f7c1669df";

const client = new SnapChainClient({
    FID: userFid,
    PK: signer,
    NODE_URL: 'hub-grpc.pinata.cloud', // your node domain, ex, node.fosscaster.xyz
    NODE_USER: '', // node auth user if needed
    NODE_PASS: '', // node auth password if needed
    GRPC_SSL: true // if node has SSL this is optional
}) 

// client.method... -> you can call read/write methods like follow / createCast, etc


```

### - read-write with Neynar Key

```typescript
import { SnapChainClient } from 'farcaster-snapchain-utils'

const userFid = 1791;
// Example signer must be a valid signer of the FID
const signer = "0x222ab147ccbaa2dc660717f28ea4aaeea13b93fe9df297669efdd12f7c1669df";
// Example of a Neynar api key must be valid
const NEYNAR_API_KEY = "A02E9451-6CFB-25B0-238E-15E18F2264DA"; 

const clientNeynar = new SnapChainClient({
    FID: userFid,
    PK: signer,
    NEYNAR_API_KEY,
});

// client.method... -> you can call read/write methods like follow / createCast, etc
```

### - add/change node later

You can also add or change either the node or key later, which is useful for avoiding creating multiple instances of `SnapChainClient` if you don't need to.

<pre class="language-typescript"><code class="lang-typescript"><strong>import { SnapChainClient } from 'farcaster-snapchain-utils'
</strong>
const client = SnapChainClient();

// changed to specific node 
client.changeNode({
NODE_URL: 'node.fosscaster.xyz',
NODE_USER: 'secret-user',
NODE_PASS: 'secret-pass'
})

//changed to using Neynar node
client.changeNode({
NEYNAR_API_KEY: 'my-secret-api-key',
})

</code></pre>

`changeNode`needs either `NODE_URL` or `NEYNAR_API_KEY` if neither is provided, it will throw an error; if both are provided, it will default to using the Neynar key instead of the node.\


### - add/change user (signer/fid) later

```typescript
import { SnapChainClient } from 'farcaster-snapchain-utils'

const client = SnapChainClient();

// changed to specific signer
client.changeSigner({
FID: 1791, // a public user fid
// my secret signer PK
PK: '0x1111111111111111111111111111111111111111111111111111111111111111' 
})

await client.follow(3) // follow dwr.eth with user andrei0x309

client.changeSigner({
FID: 3, // a public user fid
// my secret signer PK
PK: '0x1111111111111111111111111111111111111111111111111111111111111111' 
})

await client.follow(1791) // follow andrei0x309 with user dwr.eth
```

Check all methods to see all possible client actions
