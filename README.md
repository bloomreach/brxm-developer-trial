# brXM Developer Trial
[![License](https://img.shields.io/github/license/bloomreach/brxm-developer-trial.svg)](http://www.apache.org/licenses/LICENSE-2.0)

Bloomreach Experience Developer Trial provides a simplified Docker-based setup for the Enterprise Edition.

## What is Bloomreach Experience Manager?
Bloomreach Experience Manager (brXM) is an open and flexible CMS designed for developers and marketers. As the original headless CMS, brXM allows developers to build quickly and integrate with the systems. While it’s built for speed, it also provides top-notch personalization and channel management capabilities for marketers to drive results.

## Get Started
Clone the repository to run it locally:
```bash
$ git clone --single-branch --branch master https://github.com/dokmic/brxm-developer-trial.git
```

Download projects source code and place it in `backend/app` and `frontend/app` folders:
```bash
$ git clone <your-backend-repo> backend/app
$ git clone <your-frontend-repo> frontend/app
```

Then, copy `.env.dist` file to `.env`:
```bash
$ cp .env.dist .env
```

Finally, you can run the project using [docker-compose](https://docs.docker.com/compose/):
```bash
$ docker-compose up
```

To stop the project you can run:
```bash
$ docker-compose down
```

## Enterprise Repository
You can access Bloomreach Enterprise repository to get the latest versions of the dependencies by providing your user credentials in `.env` file:

```
MAVEN_USER=user
MAVEN_PASSWORD=password
```

## Build
To be able to rebuild [bloomreach/developer-trial](https://hub.docker.com/r/bloomreach/developer-trial) Docker image locally, you need to provide your Enterprise Repository credentials as it is described above.
Then you can build the image by running:
```bash
$ docker-compose build
```

## License
[Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0)
