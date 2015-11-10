This is an unraid implementation of the [dreamcat4/pipework](https://hub.docker.com/r/dreamcat4/pipework/)
image on the Docker Hub.

Install and run the pipework docker container.

To use pipework to seta  static ip and gateway add the following to the additional parameters in the docker settings:

	-e 'pipework_cmd=br0 @CONTAINER_NAME@ 192.168.1.100/24@192.168.1.1'
	
In this example the ethernete port used is 'br0', the ip is static at 192.168.2.100 with a /24 network i.e. a subnetmask of 255.255.255.0 [Wikipedia Subnetwork](https://en.wikipedia.org/wiki/Subnetwork) and a gateway of 192.168.1.1.

For more infomation on how to use pipework go to [jpetazzo/pipework](https://github.com/jpetazzo/pipework).
Note that unraid uses dhcpcd as the dhcp client.