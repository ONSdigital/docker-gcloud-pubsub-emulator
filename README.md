# Google Cloud Pub/Sub Emulator Image

[*Cloud Pub/Sub*](https://cloud.google.com/pubsub/) is a global service for real-time and reliable messaging and streaming data

This image provides a dockerized version of the *Google Cloud Pub/Sub Emulator*. It is intended to be used as a service on development environments (it **SHOULD NOT** be used in production environments). You can check *Cloud Pub/Sub* documentation on [Google Cloud Platform documentation website](https://cloud.google.com/pubsub/docs/).

## Usage
The following shell statement show the most simple execution of the provided image. It will execute the *Pub/Sub Emulator* that will listen on port 8538.

```sh
docker run --rm --tty --interactive --publish 8538:8538 eu.gcr.io/census-ci/gcloud-pubsub-emulator
```

## Configuration
The most important configuration parameters of the *Pub/Sub emulator* image are the host/port value the server will listen on and the directory where data files will be placed. By default, the image is configured to listen on `0.0.0.0:8538` and store its files in the `/data` directory. This behavior can be changed by providing the correct command-line options.

The following example shows how to start the *Pub/Sub emulator* to listen on `192.168.1.3:12345` and to store its files in the `/pubsub-data` directory.

```sh
docker run --rm --tty --interactive eu.gcr.io/census-ci/gcloud-pubsub-emulator start --host-port=192.168.1.3:12345 --data-dir=/pubsub-data
```
