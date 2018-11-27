# Automated testing on Pegasus

Using Selenium with Java.
[Selenium](https://docs.seleniumhq.org) automates browsers. That's it!



## Requirements

  * [Java (JDK)](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html?ssSourceSiteId=otnpt)
  * [Eclipse](https://www.eclipse.org/downloads/)
  * [ChromeDriver - WebDriver for Chrome](https://sites.google.com/a/chromium.org/chromedriver/downloads)

## Install

```
$ sudo pico /etc/paths
```

## Development

  | params | type    | required | default   | obs                                      |
  | ----- | ------- | -------- | --------- | ----------------------------------------- |
  | -p    | string  | false    | 3000      | port number                               |
  | -i    | string  | false    | localhost | especify an IP 			       |
  | -b    | bool    | false    | false     | open the bundle-visualizer                |

```
$ cd app/
$ ./npm start -- -p 3005 -i 192.168.1.101 -b true

...
=> App running at: http://192.168.1.101:3005

```
Reset everything (meteor app, dbs & cache):
```
$ ./npm run reset
```

## Deployment

**Building**

  Check the [application releases](https://github.com/Integration-Alpha/palyx-pegasus/releases).

  | params | type    | required | default   | obs                                       |
  | ------ | ------- | -------- | --------- | ----------------------------------------- |
  | -v     | string  | true     |           | version number                            |

```
$ ./npm run build -- -v 0.0.1
```

**Pushing**

  Push the new image to docker.hub registry.

  | params | type    | required | default   | obs                                       |
  | ---- | ------- | -------- | --------- | ----------------------------------------- |
  | -v   | string  | true     |           | version number                            |  

```
$ npm run push -- -v 0.0.1
```

**Deployment - not using on new infra**

  | params | type    | required | default   | obs                                     |
  | ---- | ------- | -------- | --------- | ----------------------------------------- |
  | -v   | string  | true     |           | version number                            |

```
$ npm run deploy -- -v 0.0.1
```

**Logs - not using on new infra**

  Check logs from the host container

```
$ npm run deploy:logs
```
