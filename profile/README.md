<img src="https://opencampingdb.github.io/logo.png" alt="" width="80" height="80" align="right">

# Open Camping DB

A free, open list of places to camp and stop in Australia: campgrounds, free camps, caravan parks, hostels and motels, rest areas, dump points, water, toilets, long vehicle parking, lookouts, swimming spots, pubs, museums and the services travellers need on the road. Each place can carry its site features, from campfires and big rig access to phone signal and crocodile warnings.

It is built from [OpenStreetMap](https://www.openstreetmap.org) every night and improved by reports, reviews and checks from the apps that use it, and by the owners of the places themselves. Anyone may use it, including in a commercial app, under the [Open Database Licence (ODbL 1.0)](https://opendatacommons.org/licenses/odbl/1-0/). Show "© OpenStreetMap contributors, Open Camping DB" wherever the data appears.

## Get the data

Every change to the data is published as a GitHub Release. Start from the manifest, which names the release and the record format and gives each file's URL, size and SHA-256:

```sh
curl -fsSL -o manifest.json https://github.com/opencampingdb/data/releases/latest/download/manifest.json
curl -fsSL -o places.ndjson.gz "$(jq -r .places.url manifest.json)"
echo "$(jq -r .places.sha256 manifest.json)  places.ndjson.gz" | shasum -a 256 -c
```

`places.ndjson.gz` holds one JSON place per line, about 6 MB compressed for the whole of Australia. A release also carries the reviews, the ids of merged places, matched Wikimedia Commons photos and the same data as an SQLite database (`ocdb.sqlite.gz`), with changesets that update an earlier copy in place. The current record format is 13 and the database layout is 2.

[CONNECTING.md](https://github.com/opencampingdb/data/blob/main/CONNECTING.md) explains each field, the 33 kinds of place and how to keep a copy current. A format change that older readers would misread is announced in a `format-change` issue on [data](https://github.com/opencampingdb/data/issues) before it ships.

## Send feedback from your app

The [feedback engine](https://github.com/opencampingdb/feedback-engine) SDK, `@opencampingdb/feedback`, sends reports, reviews, checks and the prices places publish. It asks for the traveller's consent and queues submissions while the phone is offline. It isn't on npm: [build and pack it](https://github.com/opencampingdb/feedback-engine/blob/main/docs/integration.md#2-install) from the repository, then install the `.tgz` in your app.

Every submission passes [quality rules](https://github.com/opencampingdb/feedback-engine/blob/main/README.md#how-the-quality-rules-work) before it changes the data. A fact report from an attested install (App Attest or Play Integrity) usually applies at once, and one without attestation needs a second device, on another network, to report the same value within 90 days. Changes reach the data as pull requests: automatic ones merge once their checks pass, and the rest wait for a person.

Ask for an app key with the **App key** form in [feedback-engine](https://github.com/opencampingdb/feedback-engine/issues/new/choose).

## Owners

If you run a campground or caravan park, you can [claim your place](https://opencampingdb.github.io/owners/claim.html) and keep its details right. You put a short code on your own website or public Facebook page, and a person approves the claim before anything is published. Owners of farms, stations and wineries can [list their private property](https://opencampingdb.github.io/owners/list.html), which apps show as private land to book with the owner first. It's free, and guests book directly with you.

## Repositories

| Repository | What it holds |
|---|---|
| [data](https://github.com/opencampingdb/data) | The places, the nightly OpenStreetMap sync, validation, the releases and the MapRoulette challenges for mappers (ODbL 1.0) |
| [feedback-engine](https://github.com/opencampingdb/feedback-engine) | The SDK, the intake, a photo kit apps run for themselves, and the rules that turn feedback into changes (Apache 2.0) |
| [opencampingdb.github.io](https://github.com/opencampingdb/opencampingdb.github.io) | The website and its owner pages |
| [.github](https://github.com/opencampingdb/.github) | This profile and the [governance](https://github.com/opencampingdb/.github/blob/main/GOVERNANCE.md) |
| `inbox` (private) | Raw feedback and owners' contact details, before anything reaches the data |

## Contact

Questions and corrections: open an issue in [data](https://github.com/opencampingdb/data/issues/new/choose). Takedown requests: the **Takedown** form there. Security problems and anything private: **Report a vulnerability** on the repository's Security tab.
