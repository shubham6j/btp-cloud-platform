<!-- loio7c5c565f37c946faa154909004331d57 -->

# Protecting Your Application

Developers create authorization information for business users in their environment; this information is deployed in an application and made available to administrators who complete the authorization setup and assign the authorizations to business users.



<a name="loio7c5c565f37c946faa154909004331d57__section_dnt_kjn_n4b"/>

## Lifecycle of Security Artifacts for Developers and Administrators

Developers store authorization information as design-time role templates in the application security descriptor file `(xs-security.json)`. Using the `xsuaa` service broker, they deploy the security information to the `xsuaa` service. The administrators view the authorization information in role templates, which they use as part of the run-time configuration. They use the role templates to build roles, which are aggregated in role collections. The role collections are then assigned, in turn, to business users.

The tasks required to set up authorization artifacts are performed by two distinct user roles: the application developer and the administrator of the Cloud Foundry environment. After the deployment of the authorization artifacts as role templates, the administrator of the application uses the role templates provided by the developers for building role collections and assigning them to business users.

> ### Note:  
> To test authorization artifacts after deployment, developers can use the role templates to build role collections and assign authorization to business users in an authorization tool based on a REST API.



<a name="loio7c5c565f37c946faa154909004331d57__table_f5k_xsz_m4b"/>Setting Up Authorization Artifacts \(Developers\)


<table>
<tr>
<th valign="top">

Step



</th>
<th valign="top">

Task



</th>
<th valign="top">

User Role



</th>
<th valign="top">

Tool



</th>
</tr>
<tr>
<td valign="top">

1



</td>
<td valign="top">

Specify the application security descriptor file containing the functional authorization scopes for your application.



</td>
<td valign="top">

Application developer



</td>
<td valign="top">

Text editor



</td>
</tr>
<tr>
<td valign="top">

 



</td>
<td valign="top">

\(If applicable\) If you want to create an OAuth 2.0 client in an application-related subaccount, you must use a separate security descriptor file where you specify the subaccount.



</td>
<td valign="top">

Application developer



</td>
<td valign="top">

CF command line interface



</td>
</tr>
<tr>
<td valign="top">

2



</td>
<td valign="top">

Create role templates for the application using the application security descriptor file.



</td>
<td valign="top">

Application developer



</td>
<td valign="top">

Text editor



</td>
</tr>
<tr>
<td valign="top">

3



</td>
<td valign="top">

Create a service instance from the `xsuaa` service using the service broker



</td>
<td valign="top">

Application developer



</td>
<td valign="top">

CF command line interface



</td>
</tr>
<tr>
<td valign="top">

4



</td>
<td valign="top">

Bind the service instance to the application by including it into the manifest file



</td>
<td valign="top">

Application developer



</td>
<td valign="top">

Text editor



</td>
</tr>
<tr>
<td valign="top">

5



</td>
<td valign="top">

Deploy the application



</td>
<td valign="top">

Application developer



</td>
<td valign="top">

CF command line interface or SAP BTP cockpit



</td>
</tr>
</table>

> ### Note:  
> For more information about the different steps in setting up authorization artificats as an application developer, refer to the associated procedures in this section.
> 
> [Add Authentication and Functional Authorization Checks to Your Application](Add_Authentication_and_Functional_Authorization_Checks_to_Your_Application_0a69484.md)
> 
> [Propagate User Information Between Applications or Services](Propagate_User_Information_Between_Applications_or_Services_7daed6d.md)
> 
> [Set Up Your Application for Multitenancy](Set_Up_Your_Application_for_Multitenancy_6083d3c.md)
> 
> [Setting Up Instance-Based Authorizations](Setting_Up_Instance-Based_Authorizations_519965c.md)

<a name="loio7c5c565f37c946faa154909004331d57__table_xlr_qvs_qbb"/>Setting Up Authorization Artifacts \(Administrators\)


<table>
<tr>
<th valign="top">

Task



</th>
<th valign="top">

User Role



</th>
<th valign="top">

Tool



</th>
</tr>
<tr>
<td valign="top">

Use an existing role or create a new one using role templates

[Add Roles to Role Collections on the Application Level](../50-administration-and-ops/Add_Roles_to_Role_Collections_on_the_Application_Level_7596a0b.md)



</td>
<td valign="top">

Administrator of the Cloud Foundry environment



</td>
<td valign="top">

SAP BTP cockpit

Command line interface for SAP BTP



</td>
</tr>
<tr>
<td valign="top">

Create a role collection and assign roles to it

[Maintain Role Collections](../50-administration-and-ops/Maintain_Role_Collections_d5f1612.md)



</td>
<td valign="top">

Administrator of the Cloud Foundry environment



</td>
<td valign="top">

SAP BTP cockpit

Command line interface for SAP BTP



</td>
</tr>
<tr>
<td valign="top">

Assign the role collections to users

[Managing Users and Their Authorizations Using the btp CLI](../50-administration-and-ops/Managing_Users_and_Their_Authorizations_Using_the_btp_CLI_94bb593.md) or [Assigning Role Collections](../50-administration-and-ops/Assigning_Role_Collections_9e1bf57.md)



</td>
<td valign="top">

Administrator of the Cloud Foundry environment



</td>
<td valign="top">

SAP BTP cockpit

Command line interface for SAP BTP



</td>
</tr>
<tr>
<td valign="top">

\(If you do not use `SAP ID Service`\) Assign the role collections to user groups \(cloud management tools feature set A regions\)

[Map Role Collections to User Groups](../50-administration-and-ops/Map_Role_Collections_to_User_Groups_51acfc8.md)



</td>
<td valign="top">

Administrator of the Cloud Foundry environment



</td>
<td valign="top">

SAP BTP cockpit



</td>
</tr>
<tr>
<td valign="top">

Assign the role collection to the business users provided by an identity provider \(cloud management tools feature set A\)

[Directly Assign Role Collections to Users](../50-administration-and-ops/Directly_Assign_Role_Collections_to_Users_a55a3fe.md)



</td>
<td valign="top">

Administrator of the Cloud Foundry environment



</td>
<td valign="top">

SAP BTP cockpit



</td>
</tr>
</table>

**Related Information**  


[Application Security Descriptor Configuration Syntax](Application_Security_Descriptor_Configuration_Syntax_517895a.md "The syntax required to set the properties and values defined in the xs-security.json application security descriptor file.")

