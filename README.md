# Black Duck CoPilot pip/Travis CI Example

Shows a working setup for using the Black Duck CoPilot integration to analyze the risk of project dependencies

## Travis CI Setup

The `.travis.yml` file has been modified to upload the generated data to Black Duck CoPilot:

```yaml
after_success:
- pip install hub-pip
- python setup.py hub_pip --DeployHubBdio=false
- bash <(curl -s https://copilot.blackducksoftware.com/bash/travis) ./build/blackduck/*.jsonld
```
