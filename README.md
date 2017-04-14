# Black Duck CoPilot pip/Travis CI Example

[![Build Status](https://travis-ci.org/BlackDuckCoPilot/example-pip-travis.svg?branch=master)](https://travis-ci.org/BlackDuckCoPilot/example-pip-travis) [![Black Duck Security Risk](https://copilot.blackducksoftware.com/github/groups/BlackDuckCoPilot/locations/example-pip-travis/public/results/branches/master/badge-risk.svg)](https://copilot.blackducksoftware.com/github/groups/BlackDuckCoPilot/locations/example-pip-travis/public/results/branches/master)

Shows a working setup for using the Black Duck CoPilot integration to analyze the risk of project dependencies

## Travis CI Setup

The `.travis.yml` file has been modified to upload the generated data to Black Duck CoPilot:

```yaml
after_success:
- pip install hub-pip==1.0.0
- python setup.py hub_pip --DeployHubBdio=false
- bash <(curl -s https://copilot.blackducksoftware.com/bash/travis) ./build/blackduck/*.jsonld
```
