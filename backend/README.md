# brXM Developer Trial
[![License](https://img.shields.io/github/license/bloomreach/brxm-developer-trial.svg)](http://www.apache.org/licenses/LICENSE-2.0)

Bloomreach Experience Developer Trial provides a simplified Docker-based setup for the Enterprise Edition.

## What is Bloomreach Experience Manager?
Bloomreach Experience Manager (brXM) is an open and flexible CMS designed for developers and marketers. As the original headless CMS, brXM allows developers to build quickly and integrate with the systems. While it’s built for speed, it also provides top-notch personalization and channel management capabilities for marketers to drive results.

## Get Started
The following Docker image is built as part of the [Bloomreach Experience Developer Trial](https://github.com/bloomreach/brxm-developer-trial). To get it running, you can follow the instructions provided in that repository.

## Usage
To run your project with this Docker image, you can mount your project directory as `/app`:
```bash
$ docker run -v /path/to/your/project:/app -p 8080:8080 bloomreach/developer-trial:latest
```

## Enterprise Repository
You can access Bloomreach Enterprise repository to get the latest versions of the dependencies by providing your user credentials in `MAVEN_USER` and `MAVEN_PASSWORD` environment variables:
```bash
$ docker run \
  -e MAVEN_USER=user \
  -e MAVEN_PASSWORD=password \
  -v /path/to/your/project:/app \
  -p 8080:8080 \
  bloomreach/developer-trial:latest
```

## License
[Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0)
