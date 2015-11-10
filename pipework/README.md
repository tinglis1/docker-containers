This is an unraid implementation of the [dreamcat4/pipework](https://hub.docker.com/r/dreamcat4/pipework/) image on the Docker Hub.

For more infomation on how to use pipework go to [jpetazzo/pipework](https://github.com/jpetazzo/pipework).

### Pipework docker installation

Add the template repository to unraid Docker Template Repositories:

	https://github.com/tinglis1/docker-containers/tree/master/templates

Install and run the pipework docker container. No configuration is required for the pipework container.


### Setting a ip for a docker container

Pipework is controlled by adding to the additional parameters input in the container advanced configuration.

#### Static IP
To use pipework to set a  static ip:

	-e 'pipework_cmd=br0 @CONTAINER_NAME@ 192.168.1.100/24@192.168.1.1'
	
In this example the ethernet port used is 'br0', the ip is static at 192.168.2.100 with a /24 network and a gateway of 192.168.1.1.

#### Dynamic IP
To use pipework to set a  dynamic ip:

	-e 'pipework_cmd=br0 @CONTAINER_NAME@ dhcpcd'
	
In this example the ethernet port used is 'br0', the ip is dynamic using dhcpcd which is installed in unraid.

