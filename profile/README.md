<img src="https://opencampingdb.github.io/logo.png" alt="" width="80" height="80" align="right">

# Open Camping DB

A free, open list of places to camp and stop in Australia: campgrounds, free camps, caravan parks, hostels and motels, rest areas, dump points, water, toilets, long vehicle parking, lookouts, swimming spots, pubs, museums and the services travellers need on the road. Each place can carry its site features, from campfires and big rig access to phone signal and crocodile warnings.

It is built each night from [OpenStreetMap](https://www.openstreetmap.org) and improved by reports, reviews and checks from the apps that use it, and by the owners of the places themselves. Anyone may use it, including in a commercial app, under the [Open Database Licence (ODbL 1.0)](https://opendatacommons.org/licenses/odbl/1-0/).

## Use the data

- **Download:** start from the [latest manifest](https://github.com/opencampingdb/data/releases/latest/download/manifest.json). It points to `places.ndjson.gz`, one place per line, with a checksum for each file. The whole of Australia is about 3 MB.
- **Fields and kinds:** [CONNECTING.md](https://github.com/opencampingdb/data/blob/main/CONNECTING.md) explains each field, the 32 kinds of place, the site features and how to keep a copy up to date.
- **Credit:** show "© OpenStreetMap contributors, Open Camping DB" wherever the data appears.

## Send feedback from your app

The [feedback engine](https://github.com/opencampingdb/feedback-engine) is a small SDK for reports, reviews, checks and fees, including corrections to a place's name, description and kind. It queues them offline and sends them to the intake. Agreed changes reach the data as reviewed pull requests, under fixed quality rules. For example, a changed fact needs two independent reports. Ask for an app key at dev@example.org.

## Owners

If you run a campground or caravan park, you can [claim your place](https://opencampingdb.github.io/owners/claim.html) and keep its details right. Owners of farms, stations and wineries can [list their private property](https://opencampingdb.github.io/owners/list.html). It's free, with no commission, and guests book directly with you.

## Repositories

| Repository | What it holds |
|---|---|
| [data](https://github.com/opencampingdb/data) | The places, the nightly OpenStreetMap sync, validation and the releases (ODbL 1.0) |
| [feedback-engine](https://github.com/opencampingdb/feedback-engine) | SDK, intake and the rules that turn feedback into changes (Apache 2.0) |
| [opencampingdb.github.io](https://github.com/opencampingdb/opencampingdb.github.io) | The owner pages |

Questions and corrections: open an issue in [data](https://github.com/opencampingdb/data/issues/new/choose). Takedown requests: the Takedown form there. Security problems and anything private: **Report a vulnerability** on the repository's Security tab. App keys: the App key form in [feedback-engine](https://github.com/opencampingdb/feedback-engine/issues/new/choose).
