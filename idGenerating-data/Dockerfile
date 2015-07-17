FROM learninglayers/base
MAINTAINER Sadik Bakiu <bakiu@dbis.rwth-aachen.de>

# add files to data volume 
ADD etc /build/etc

# Replace variables in config files
CMD sed -i "s#PASSWORD#${PASSWORD}#g" /build/etc/i5.las2peer.services.idGeneratingPackage.IdGeneratingClass.properties && \
	sed -i "s#USERNAME#${USERNAME}#g" /build/etc/i5.las2peer.services.idGeneratingPackage.IdGeneratingClass.properties && \
	sed -i "s#DATABASE#${DATABASE}#g" /build/etc/i5.las2peer.services.idGeneratingPackage.IdGeneratingClass.properties && \
	sed -i "s#EPURL#${EPURL}#g" /build/etc/i5.las2peer.services.idGeneratingPackage.IdGeneratingClass.properties && \
	sed -i "s#PORT#${PORT}#g" /build/etc/i5.las2peer.webConnector.WebConnector.properties

# provide directories etc and log as volumes
VOLUME ["/build/etc/","/build/log/"]