This is an unraid implementation of the [dreamcat4/pipework](https://hub.docker.com/r/dreamcat4/pipework/) image on the Docker Hub.

For more infomation on how to use pipework go to [jpetazzo/pipework](https://github.com/jpetazzo/pipework).

### Pipework docker installation

Add the template repository to unraid Docker Template Repositories:

	https://github.com/tinglis1/docker-containers/tree/master/tinglis1-templates

Install and run the pipework docker container. No configuration is required for the pipework container.


### Setting a ip for a docker container

Set the container network mode to 'none' and then add the additional parameters input in the container advanced configuration.


#### Static IP
To use pipework to set a  static ip:

	-e 'pipework_cmd=br0 @CONTAINER_NAME@ 192.168.1.100/24@192.168.1.1'
	
In this example the ethernet port used is 'br0', the ip is static at 192.168.2.100 with a /24 network and a gateway of 192.168.1.1.

#### Dynamic IP
To use pipework to set a  dynamic ip:

	-e 'pipework_cmd=br0 @CONTAINER_NAME@ dhcpcd'
	
In this example the ethernet port used is 'br0', the ip is dynamic using dhcpcd which is installed in unraid.


#### Notes

**This docker container has the most customisation I have ever used and dont really know what most of it does. If any of these additional parameters are of concern to the security or stability of unraid let me know ASAP.**

*This could probably have been made as a plugin with more gui control and less additional configuration. I didnt have the time or skill to implement that and this seems to work for me. Feel free to make a proper plugin for pipework. I have some ideas on how it could work if you want to dicuss it.*

*Pipework didnt appear to have a logo so I have used the 'd' from docker and turned it upside down. If someone has a proper logo for pipework let me know.*