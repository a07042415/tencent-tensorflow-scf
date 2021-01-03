[中文](README.md) | [Screencast](https://youtu.be/Thoi7XrIKvE) | [Live demo!](https://sls-website-ap-hongkong-m5jv9m8-1302315972.cos-website.ap-hongkong.myqcloud.com/)

# Quick start

Make sure that you have the [Serverless Framework](https://www.serverless.com/framework/docs/providers/tencent/guide/installation/) installed. Clone this repo, and do the following.

```
$ sls deploy
... ...
  website:       https://sls-website-ap-hongkong-kfdilz-1302315972.cos-website.ap-hongkong.myqcloud.com
  vendorMessage: null

63s › tencent-tensorflow-scf › "deploy" ran for 3 apps successfully.
```

Load the website URL in any web browser and start to use this function to identify objects in photos.

# Build your own Tensorflow cloud function

Fork this repo and use the `Code | Open with Codespaces` button to launch Github Codespaces IDE in your browser. It may take a few minutes to start the first time. 

## Low code development

Once the Codespaaces IDE starts, you can make simple changes to the source code to customize it for your own applications. [See a tutorial](https://www.secondstate.io/articles/faas-image-classification/)

* Make changes to the Tensorflow model and data pre-processing and post-processing logic in `src/lib.rs` file. 
* Make changes to the front end UI in the `website/content/index.html` file.

## Build

Open a `Terminal` windon in the Codespaces IDE, and run the following command to build your cloud function.

```
$ ssvmup build --enable-aot
```

## Deploy

In the `Terminal` window, run the following command to deploy the Tensorflow cloud function to the Tencent Cloud.

```
$ cp pkg/scf.so scf/
$ sls deploy
... ...
  website:       https://sls-website-ap-hongkong-kfdilz-1302315972.cos-website.ap-hongkong.myqcloud.com
```

Load the deployed URL in any web browser and have fun!

# Develop on your own computer

If you cannot or do not wish to use Github Codespaces, you can install the ssvmup and serverless framework toolchains on your own computer (or Docker image) to build and deploy Tensorflow serverless functions.

[Install the ssvmup tool](https://www.secondstate.io/articles/ssvmup/)

Install the Serverless Framework via the NPM.

```
$ npm install -g serverless
```

That's it. You can now follow the Codespaces' build and deploy instructions above.
