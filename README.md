# maven-import-bom


This is an import BOM for a specific version of Maven.

It's job is to pin dependencies within a given installation of Maven so that external IB projects can use those pinned versions without conflict.


## Some changes

Changed
Property	Was	Now (lib jar)
maven.version	3.9.11	3.9.16
maven.resolver.version	2.0.11	1.9.27
commons.cli.version	1.10.0	1.11.0
commons.codec.version	1.19.0	1.21.0
eclipse.sisu.inject.version	0.9.0.M4	1.0.0
eclipse.sisu.plexus.version	0.9.0.M4	1.0.0
google.guava.version	33.4.8-jre	33.6.0-jre
google.guice.version	7.0.0	5.1.0
plexus.cipher.version	3.0.0	2.0
plexus.interpolation.version	1.28	1.29
plexus.sec.dispatcher.version	3.0.0	2.0
plexus.utils.version	4.0.2	3.6.1
Already matching: apache.httpclient 4.5.14, apache.httpcore 4.4.16, javax.annotationapi 1.3.2, maven.shared.utils 3.4.2, maven.wagon 3.5.3, plexus.component.annotations 2.2.0.

Note on Guice: the lib jar is guice-5.1.0-classes.jar (the classes classifier — no shaded deps). The BOM manages com.google.inject:guice and guice-assistedinject without a classifier, so consumers get the fat jar unless they add <classifier>classes</classifier>. Guice 5.1.0 is also javax.inject-based, not jakarta — a real behavioral difference from the 7.0.0 you had.

