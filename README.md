# Hyperledger Fabric SDK for Java
This project provides a low-level API for interacting with Hyperledger Fabric blockchain networks, and is used by the
high-level **Hyperledger Fabric Gateway SDK for Java**:
 
For building Hyperledger Fabric blockchain client applications, you are strongly encouraged to use the high level API.

The information below is intended for contributors to this repository.

---

## Introduction for contributors

The SDK provides a layer of abstraction on top of the wire-level protobuf based communication protocol used by client
applications to interact with a Hyperledger Fabric blockchain network. It allows Java applications to manage the
lifecycle of Hyperledger channels and user chaincode. The SDK also provides a means to execute user chaincode, query
blocks and transactions on the channel, and monitor events on the channel.

The SDK acts on behalf of a particular User which is defined by the embedding application through the implementation
of the SDK's `User` interface.

Note, the SDK does **not** provide a means of persistence
  for the application defined channels and user artifacts on the client. This is left for the embedding application to best manage.
  Channels may be serialized via Java serialization in the context of a client.
  Channels deserialized are not in an initialized state.
  Applications need to handle migration of serialized files between versions.

The SDK also provides a client for Hyperledger's certificate authority.  The SDK is however not dependent on this
particular implementation of a certificate authority. Other Certificate authority's maybe used by implementing the
SDK's `Enrollment` interface.

 This provides a summary of steps required to get you started with building and using the Java SDK.
 Please note that this is not the API documentation or a tutorial for the SDK, this will
  only help you familiarize to get started with the SDK if you are new in this domain.





## Checkout SDK from Github
```
git clone https://github.com/hyperledger/fabric-sdk-java.git
cd fabric-sdk-java/
```

## Production Java applications
For Java applications use the latest <b>released</b> version of the SDK v1.4.x releases:
```
     <!-- https://mvnrepository.com/artifact/org.hyperledger.fabric-sdk-java/fabric-sdk-java -->
     <dependency>
         <groupId>org.hyperledger.fabric-sdk-java</groupId>
         <artifactId>fabric-sdk-java</artifactId>
         <version>1.4.7</version>
     </dependency>

```

