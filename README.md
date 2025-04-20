---
icon: hand-wave
cover: .gitbook/assets/OIG4.jfif
coverY: 0
layout:
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# faracster-snapchain-utils

This is a library to simplify the interaction with a Farcaster snapchain node.

It can be used in read-only mode or in read/write mode.

If you use it in read/write mode, you will need to provide a private key and a FID.

If a node is not provided, the library will use the Pinata public node.

You can also use it with Neynar, provided you pass the `NEYNAR_API_KEY` to the constructor or to `changeNode` the method.

The library allows you to change the node or signer, so you don't need to create a new instance every time you want to change the node or signer.

### Jump right in

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>QuickStart</strong></td><td>View the basics</td><td></td><td></td><td><a href="getting-started/quickstart.md">quickstart.md</a></td></tr><tr><td><strong>Write Methods</strong></td><td>View the write Methods</td><td></td><td></td><td><a href="broken-reference">Broken link</a></td></tr><tr><td><strong>Read Methods</strong></td><td>View The read methods</td><td></td><td></td><td><a href="broken-reference">Broken link</a></td></tr></tbody></table>
