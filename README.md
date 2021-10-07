# DASH-IF Codecs Catalogue

This repository collects the list of codecs and parameters on how to add to DASH. Note that this does not act as a formal registration authority. Requests for adding an codecs are formally submitted via a Pull Request here. The simplest way to submit a Pull Request is described bellow.

## Submission process

1. Login on GitHub using your personal account (create one if needed)
2. Fork the repository into your own area at GitHub
3. Go to that fork, and edit the CSV files in the folder /csv according to your submission (e.g. adding, removing codecs ...)
4. When it is right, submit a Pull Request to the repository here.

## Guidelines for CSV formatting (step 3)

The codecs are grouped per type in different CSV files. Each line of 
the CSV files is composed of exactly 5 fields following the same pattern
`name|specification|codec|profile|comment`.

- `name`: the media profile name
- `specification`: name and version of the corresponding specification, e.g. ISO/IEC 23009-2
- `codec`: the `@codecs` parameter to be used in the dash MPD
- `profile`: the CMAF media profile 4CC brand to be added to the `@containerProfiles`
- `comment`: free form comment related to the codec

To make a valid Pull Request, it boils down to:

1. Choosing the right CSV file corresponding to your codec
2. Modifying the chosen CSV file with your proposed codec according to the pattern above
3. Committing your changes
4. Submitting the Pull Request

## For maintainer

Whenever there is a commit pushed to this repository, it triggers the CI script
.travis.yml. This script executes an HTTP call to trigger the DASH-IF website
build script. This call is sent to the Travis CI API. The call to the API is
authenticated using a Travis Token of someone having permission access to the
DASH-IF website repository on Travis. The Token is inserted into the script
using the key TRAVIS_TOKEN.
