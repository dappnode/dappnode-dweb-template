# DAppNode + Dwebs tutorial

This tutorial will guide you in building and deploying a decentralized website. You will publish it in IPFS and then point an .eth domain to it using the Ethereum Name Service (ENS).

## 1. Installing the tools
### 1.1 Pre-requisites
If you don’t have it installed yet, you need to install Node.js in your laptop.

Last stable version of Node.js (Or 8.12.0) works just fine. 

### 1.2 Clone and setup the template
The template is a simple create-react-app with preconfiguration and deploy scripts. Just run

```
git clone https://github.com/dappnode/dappnode-dweb-template.git
```

then,

```
yarn
yarn start
```
or
```
npm i
npm start
```

## 2. Deploying the dweb
First, let's personalize the website briefly and deploy it to IPFS.

Go to `src/App.js` line 44 and write your name, brand or a just message.

```javascript
<div className="hero-title">  
  Welcome to "name"          // line 44
</div>
```

Then, run:
```
yarn run publish
```
or
```
npm run publish
```

The website files will be bundled and uploaded to IPFS. The result of the command will give you a link to directly access the website by accessing DAppNode's own IPFS gateway:

```bash
...
Uploading files...
Succesfully uploaded files!
                                                       path	                                          hash	   size
-----------------------------------------------------------	----------------------------------------------	-------
                           build/android-chrome-192x192.png	QmVDXMWzpcxJH7dVLy7EcJbiuwMbvW7TzpftQ9WhZJtNYo	  25613
                           build/android-chrome-512x512.png	QmSPVmLSSBo9RdVTxUUGvDt3Qkb62Pu5ai3NPLrvdkKFxY	  82789
                                 build/apple-touch-icon.png	QmV6VnxN2CdcHx7jE9ZWfxYQMhKn3w3isRHpvUdUUzFtnU	  12448
                                  build/asset-manifest.json	Qmdkm4QuWuLpEUxK5Sw6Zc6zxbNYqvvEpuzra6Wdfu29dC	    739
                                    build/favicon-16x16.png	QmQmLYTCac5go87oVPdjqbwKHdrb5dDQxe5pD1SxqDdesF	   1333
                                    build/favicon-32x32.png	QmTyju5LXAnxibNqu14Nv9KT3JSGstgPHJDJzYjyHVX6M1	   2144
                                          build/favicon.ico	Qmbcw7e2P9AGYBEzxSCnscE2Nw6JCpjKCftSS4SMxdRJqS	  15097
                                           build/index.html	QmcfCrDMHYANCU5HtAfGoEPSMJY6W7ujE3vnwBfSJUBnAY	   2078
                                        build/manifest.json	QmYLdnBrbeN8rpbwBC2VLwgSBht4Ft6hBSD6F3DKxqecGG	    435
                                   build/mstile-150x150.png	QmWL2XRaSUsATTwhY1XV61eMSKtfugkLGb2CQ99xrXuvPj	   5072
build/precache-manifest.ddcafeb8e9d7e394cefc3d5a75f6db35.js	QmYqWPHKJSEVZFpjd7jGJz245rbXkQpGfA2iL92qNYKQRT	    516
                                build/safari-pinned-tab.svg	Qmed3oKnRqBpo67pzgJhGEaHZVWBzC3AnP37WeBHXqxSZM	   6147
                                    build/service-worker.js	QmQog54KdYuY6uUfX1yhpzqrvbUCEpLZgevygmV29sMNHw	   1054
                                     build/site.webmanifest	QmRt7SXpWXEKCqerikcqtMxBBT6iiVzCZixCSyKkbk4Suc	    472
                   build/static/css/main.53f33b1d.chunk.css	QmdUKpYyLLDyPj4D4Ym7gPbwnXHWiDFdGPwKQXEK7t1ou4	    790
               build/static/css/main.53f33b1d.chunk.css.map	QmVDtt1eLcfPrRY21VfAqXKrxdd6HjYUtMnk1WVSTgiJi8	   1779
                        build/static/js/1.d7b27eab.chunk.js	QmbCkiGR6htjUrabSm5m9DoRKdtH5m2WgbgonAZ5Zyi3Si	1199095
                     build/static/js/main.3f9a9d22.chunk.js	QmQnViPdjVU7YqN97W5np4WFy2kurq3vdGSVwmgMv2VTri	  13627
                   build/static/js/runtime~main.4a686d48.js	QmVfzdU72f7TuF196YVC629gf2GT18Z9dRhua9oahKFFAR	   1514
                                           build/static/css	QmNN7bhsTL7Z5hJwM7PKhXhuYF9PSaYe7KmdkJovnNHGSp	   2709
                                            build/static/js	QmZgTXSePohAbuRhtNVJhGstDEJYTa7o7ioFJhb1oEmzXi	1214435
                                               build/static	QmawxD5GFXh4NM7mNHjShjccnN5mAHbf1wsKRu3mXdr4b4	1217240
                                                      build	QmcR2GFrcQpLsMfBYMqrfebXizByZ2XbxjRN957LermuXW	1374119




To point an .eth domain to this website, use this hash as value:

   QmcR2GFrcQpLsMfBYMqrfebXizByZ2XbxjRN957LermuXW

To preview you website immediately go to:

   http://my.ipfs.dnp.dappnode.eth:8080/ipfs/QmcR2GFrcQpLsMfBYMqrfebXizByZ2XbxjRN957LermuXW
```

## 3. Use DAppNode providers
The project folder contains the file `providers.json` with the info of all 4 ethereum networks available in this DAppNode.
You can uncommented a component that will all these DAppNode's providers. To do so, uncomment the code block between lines xx - yy

```javascript
{Object.keys(providers).map((provider, i) => (
    <Grid key={i} item xs={3}>
        <ChainCard provider={providers[provider]} />
    </Grid>
))}
```

Now run again:
```
yarn run publish
```
or
```
npm run publish
```

Now go to: dweb.dappnode.eth

Telegram: https://t.me/dappnode

Riot: https://riot.im/app/#/room/#DAppNode:matrix.org



