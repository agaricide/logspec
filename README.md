# logspec

## Goals:

A simple logging spec that I'm using for journaling or logging longterm progress on a particular topic.

Logspec is only pertains to file naming and is file type agnostic.

It's human readable (preferably).  Else, it's unambiguously the most ubiquitous date formatting possible (Unix timestamp, IMO).

## Spec

File names are dates (& optionally times):

| Example           | Description     |
| ----------------- | --------------- |
| `04-11-21.md`     | US conventional |
| `11-04-21.md`     | Int.            |
| `1621306862.json` | Unix timestamp  |

## Principles 

- human readable date `MM/DD/YY` or `DD/MM/YY` format is preferred
- Unix is the default format if second or millisecond specificity is necessary

## Why Unix timestamp?

It's the most obvious choice for file naming because:
- Logging that requires the specificifiy of milliseconds usually occurs on programmatic services deployed to e.g. AWS or etc.
    - These are generally 'nix environments
    - **goal:** write the timestamps in the format of the entity that consumes them
- This is an obvious and unambigous date formatting to parse in code
- Logs will be arranged in temporal order in file exporing software given a standard alphameric sort