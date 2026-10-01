# SpinBooth — Privacy

_Last updated: 1 October 2026_

> **This is a starting draft, not legal advice.** It describes accurately what the software does, so
> a lawyer reviewing it has facts to work from rather than boilerplate. Have one review it before you
> publish it, especially if you operate in the EU or California.

## The short version

SpinBooth runs on the operator's own phone. **Videos, photos and guest contact details stay on that
phone** unless the operator deliberately sends them somewhere — to their own cloud storage, their own
email provider, or their own AI service.

**The makers of SpinBooth do not receive, store or have access to any of it.** There is no SpinBooth
account, no SpinBooth server holding events, and no analytics that carry anyone's personal data.

## Who is responsible for what

| | |
|---|---|
| **The booth operator** | Decides what is collected and where it goes. For data-protection law, they are the controller of their guests' data. |
| **SpinBooth (the app)** | A tool that runs on their device. |

If you are a guest at an event and want your data removed, ask the operator running the booth — they
hold it, and they can delete it.

## What the app uses on the device

- **Camera and microphone** — to record each spin. Footage is written to the app's own storage.
- **Bluetooth** — to drive the booth's motor. Nothing personal is transmitted; it is start, stop,
  speed and direction.
- **Photo library** — only when someone chooses to save a video or photo, or the operator switches
  on automatic saving.
- **Local network** — only in Wi-Fi sharing mode, where the phone serves the video directly to a
  guest's phone on the same network. It does not leave the venue.

## What can leave the device, and only if the operator switches it on

- **Guest contact details.** If the operator enables "Text me my video" or email delivery, guests may
  enter a name, phone number or email. These are stored on the phone and can be exported by the
  operator as a spreadsheet. They are sent to the operator's own SMS or email provider to deliver the
  video.
- **Videos and photos.** If the operator enables cloud sharing, each video is uploaded to **the
  operator's own** storage — their S3/R2 bucket, their Google Drive, or their Dropbox — so a QR code
  or link works. **Anyone with that link can watch the video.**
- **One still photo per guest, to an AI service.** If the operator enables AI styling, a single frame
  is sent to the AI provider they configured, to be restyled, and comes back changed. The video
  itself is never sent. That provider's own privacy terms then apply. The app will not do this until
  the operator confirms they have their guests' permission.
- **Printing.** Sent directly to a printer over AirPrint on the local network.

Guests are shown, at the booth and before entering anything, exactly which of these apply — generated
from how that booth is configured, so the notice always matches what is about to happen.

## Anonymous booth information (off by default)

An operator can opt in to help identify booth models. If they do, the app sends a description of the
**booth hardware** — never anything about people:

- the booth's model name with its serial number stripped (`360 Controller_3426` → `360 Controller`)
- the Bluetooth services and characteristics it offers
- the first byte of its reply, and the manufacturer ID from its advertisement
- a random install identifier used only to avoid counting the same phone twice

No videos, photos, contacts, location, event details or device identifiers are included. The MAC
address a controller reports is removed in full.

## Payment

Subscriptions are handled by Apple. SpinBooth never sees a card number, billing address or any other
payment detail — only whether this Apple ID currently has a subscription.

## Keeping things

Everything lives on the operator's phone until they delete it. Deleting the app removes it all.
Within the app, an operator can delete guest contacts and the event recap at any time.

If the operator uploaded videos to their own cloud storage, those copies are theirs to manage and are
deleted there.

## Children

SpinBooth is sold to event professionals, not to children. Guests at an event may be any age; it is
the operator's responsibility to obtain consent appropriately, and to be aware that photographing
children and sending their images to an AI service may carry additional obligations where they work.

## Contact

marketingformybusiness@gmail.com
