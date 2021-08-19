# Simple Static HTML Website on the IC.
<a href="https://sdk.dfinity.org/docs/"><img src="https://img.shields.io/badge/dfx-0.7.0-yellow"/></a>


## Install the Canister SDK
You can check if `dfx` is already installed with `dfx --version`.
You can find more info [here](https://sdk.dfinity.org/docs/).

To download the DFINITY Canister SDK, run the following command in your terminal:
```
sh -ci "$(curl -fsSL https://sdk.dfinity.org/install.sh)"
```

### Step 1: Configuration File
The file `dfx.json` is the configuration file which contains configurable options for your project.
```json
{
    "canisters": {
        "web": {
            "type": "assets",
            "source": [
                "www",
                "www/css"
            ]
        }
    }
}
```
The example above creates an `assets` canister named `web`.
In `source` all the asset directories are specified which will get uploaded to the canister.

### Step 2: Basic HTML and CSS
In the previous step we specified that the assets will be contained in `www` and `www/css`, which contain `index.html` and `style.css` respectively.

### Step 3: Deploy to IC
If you need help deploying the project, then you can find more information [here](https://sdk.dfinity.org/docs/quickstart/network-quickstart).

```shell
dfx start
```

```shell
# Deploy locally (e.g. localhost:8000)
dfx deploy
# or on the IC itself
dfx deploy --network=ic
```

Depending where you deployed the canister, you can find it on:
- `http://localhost:8000/?canisterId=<canister id>`
- `<canister id>.ic0.app`

---

<img src="index.png">

Updates:
More readings on deployment process: https://sdk.dfinity.org/docs/quickstart/network-quickstart.html
Note: There is not necessary to use npm install or having node package installed as this is assumed that to www folder we copy a coplete content of dist/spa folder build up in other place.
Consider  dfx deploy --network=ic --no-wallet     instead of   dfx deploy --network=ic
To provide smooth usage on mobile browsers rather use https://gsueu-yaaaa-aaaae-aaagq-cai.raw.ic0.app where name of the container is replaced by your name of the asset container.
