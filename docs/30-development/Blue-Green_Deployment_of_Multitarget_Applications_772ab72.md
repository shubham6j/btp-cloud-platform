<!-- loio772ab72204f04946b79ce2d962e64970 -->

# Blue-Green Deployment of Multitarget Applications

Run two identical production environments to employ the blue-green deployment technique.

> ### Restriction:  
> Blue-green deployment is supported only for Cloud Foundry applications. It is not supported for bound services, such as service instances and their configuration, workflow content, and HTML5 repository content, among others. Live and idle applications are bound to the same service instances.

By using the blue-green deployment technique, you can update the system without downtime and with reduced risk. During the process, you can perform tests and validation of the new application version using productive data. A classical blue-green deployment of stateless applications, which are modeled as an MTA, is supported.

In the context of Multitarget applications, you have the following options for using blue-green deployment:

-   [Legacy Blue-Green Deployment](Legacy_Blue-Green_Deployment_764308c.md) - where the productive environments are called “blue” and “green”
-   [Blue-Green Deployment Strategy](Blue-Green_Deployment_Strategy_7c83810.md) - where the production environments are called “live” and “idle”.

**Related Information**  


[https://docs.cloudfoundry.org/devguide/deploy-apps/blue-green.html](https://docs.cloudfoundry.org/devguide/deploy-apps/blue-green.html)

