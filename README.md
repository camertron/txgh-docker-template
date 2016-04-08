Txgh Docker Template
====

The Txgh Docker template is a quick way to get up-and-running with [Txgh](https://github.com/lumoslabs/txgh) and Docker. It includes a number of handy scripts and a configuration wizard.

What is Txgh?
---

Txgh is a localization automation service. It connects Transifex, a 3rd-party translation management tool, with Github. By watching your repository for changes to translatable content, Txgh is able to automatically push content to Transifex for translation and pull translated content back into your repository. It uses Github and Transifex webhooks along with a bunch of API calls to work its magic.

Getting Started
---

1. Clone this repository.

2. Change directory into your local clone and configure Txgh by running `./bin/configure`. Follow the script's instructions. See the [Txgh README](https://github.com/lumoslabs/txgh#configuring-txgh) for a description of all the configuration options.

3. Run `./bin/update` to pull the latest Txgh Docker image.

4. Run `./bin/run`. Txgh should start on port 9292.

5. Test your running instance by hitting the `health_check` endpoint, eg `curl -v localhost:9292/health_check`. You should get an HTTP 200 response. (Please note that, depending on how your Docker server is configured, your Txgh instance may not be bound to localhost.)

Scripts
---

* **`./bin/configure`**: Walks you through connecting a Transifex project and a Github repo. In other words, adds to or modifies entries in `./config.yml`.
* **`./bin/update`**: Pulls the latest Txgh Docker image.
* **`./bin/run`**: Starts Txgh (not as a daemon).
* **`./bin/start`**: Starts Txgh as a daemon. Container id will be stored in `./txgh.cid`.
* **`./bin/stop`**: Stops a running Txgh daemon.
* **`./bin/status`**: Determines if the Txgh daemon is running or not.

Requirements
---

You'll need Docker and an Internet connection. Other than that, Txgh has no external requirements like a database or cache.

Authors
---

This repository is maintained by [Cameron Dutro](https://github.com/camertron) from Lumos Labs.

License
---

Licensed under the Apache License, Version 2.0. See the LICENSE file included in this repository for the full text.
