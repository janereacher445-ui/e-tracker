# E-Tracker

A personal HRT tracker in a single HTML file: weekly injections (dose, day, site rotation), blood tests, and a chart that puts your measured estradiol next to the level a pharmacokinetic model estimated for that moment.

## Using it

Open `index.html` in a browser. There is nothing to build or install.

- **Overview**: next injection day, suggested site, estimated level now, and the estimate-vs-measured chart.
- **Injections**: log each injection with time, dose, ester, site and notes.
- **Blood tests**: log results with the time of the blood draw. Each estradiol result is compared with the model's estimate and range for that time.
- **Regimen**: ester, dose, injection day (Tuesday by default), sites, units, your target range, and backup/restore.

## Where the data lives

Everything is stored in your browser's `localStorage`. Nothing is sent to a server, and no health data is in this repository. Use **Regimen → Save backup file** now and then, since clearing browser data erases it.

## The estimate

The curve uses the 3-compartment model, parameters and posterior samples from [estrannaise.js](https://github.com/WHSAH/estrannaise.js) (MIT, see `THIRD_PARTY_LICENSES.md`). The shaded band is the 5th to 95th percentile across 48 of its posterior samples. The models were fitted to intramuscular data and describe a typical response, so individual levels can differ a lot. This is a personal log, not medical advice.
