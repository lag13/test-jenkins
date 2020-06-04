# test-jenkins
Running through the Jenkins tutorial: https://www.jenkins.io/doc/pipeline/tour/hello-world/

I had to manually install this plugin to get the `agent { docker ...`
configuration to work: https://plugins.jenkins.io/docker-workflow/
That's really strange to me though because the docs say that Pipeline
version 2.5 or higher comes with support for interacting with docker
and the docs also never seem to mention this plugin:
https://www.jenkins.io/doc/book/pipeline/docker/
