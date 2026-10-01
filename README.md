# SpinBooth booth catalog

Motor-control profiles for 360 photo booths, so [SpinBooth](https://github.com/marketingformybusiness/SpinBooth)
recognises a booth and drives it without the operator setting anything up.

`catalog.json` is a signed envelope:

```json
{ "sig": "<base64 Ed25519 signature>", "body": "<base64 of the catalog JSON>" }
```

The signature is checked against a public key compiled into the app, over the exact body bytes, and
**every entry is re-checked against the app's own safety lint after the signature verifies** — so a
profile with no stop command cannot ship even if the signing key were stolen. Serving this file from
a public host is therefore safe: altering a single byte makes the app reject the whole catalog.

## What a profile is

How one controller expects to be told to spin — which bytes mean start, stop, speed and direction.
Nothing identifying: no operator, event, guest or location data appears here.

Each one was captured from real hardware. Guessed commands could spin an arm unpredictably, so
nothing reaches this file without having driven a real booth.

## Contributing yours

In SpinBooth: **Learn → ⋯ → Share as catalog entry**, and send the JSON. Booths are mostly rebadged
from a handful of Guangdong boards, so one capture usually covers many brands at once.

`verified: false` means it worked on the bench. It becomes `true` after it has run a real event.
