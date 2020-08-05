# 3Box-ReactJS

```js
const Box = require("3box");

const box = await Box.create(window.ethereum)
const [address] = await window.ethereum.enable()
await box.auth([], { address })
// Note: sometimes, openSpace returns early... caution
const space = await box.openSpace('io-textile-dropzone')
await box.syncDone;
try {
  // We'll try to restore the private key if it's available
  var storedIdent = await space.private.get('identity')
  if (storedIdent === null) {
    throw new Error('No identity')
  }

  const identity = await Libp2pCryptoIdentity.fromString(storedIdent)
  const auth = authorize(identity)
} catch (e) {
  // /**
  //  * If the stored identity wasn't found, create a new one.
  //  */
  const identity = await Libp2pCryptoIdentity.fromRandom()
  const identityString = identity.toString()
  await space.private.set('identity', identityString)
  alert("error")
}
```
