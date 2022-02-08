This is a reproducer for the BouncyCastle problem based on the quarkus getting started project.

> mvn clean package -Pnative
> 
> ./target/getting-started-1.0.0-SNAPSHOT-runner

Open following URL: http://localhost:8080/hello/greeting/BouncyCastle

> 2022-02-08 17:57:45,900 ERROR [io.qua.ver.htt.run.QuarkusErrorHandler] (executor-thread-0) HTTP Request to /hello/greeting/BouncyCastle failed, error id: d871f66a-e065-4857-aafc-4f6654bf23dc-2: org.jboss.resteasy.spi.UnhandledException: com.oracle.svm.core.jdk.UnsupportedFeatureError: Trying to verify a provider that was not registered at build time: BC version 1.7. All providers must be registered and verified in the Native Image builder. 


Looks like this is not working:
https://quarkus.io/guides/security-customization#bouncy-castle
