# KeycloakRestAPI 
Keycloak REST API v18.0

#Old Versions (add /auth to the path)

Keycloak Admin Rest API v10 ([https://www.keycloak.org/docs-api/10.0/rest-api/index.html](https://www.keycloak.org/docs-api/10.0/rest-api/index.html))

TODO

*   Don't forget to give reaml-admin to your client

## Table of Contents 
<details><summary>View table of contents</summary>

1. [Access Token](#18383acc-d460-4000-83f1-59b61469a400)
	1. [Folder1](#18383acc-d470-4000-8885-dbb3efa13600)
		1. [Folder1.1](#18383acc-d470-4000-8923-43e4af88b200)
			1. [New Request](#18383acc-d470-4000-8554-ada9e46a5f00)
				1. [Ex: New Example](#18383acc-d470-4000-8554-ada9e46a5f00_example_0)
				1. [Ex: New Example 2](#18383acc-d470-4000-8554-ada9e46a5f00_example_1)
			1. [form data](#18383acc-d4a0-4000-8b09-854efcda7200)
			1. [New binary](#18383acc-d4b0-4000-8de9-9da76964d800)
			1. [New None](#18383acc-d4b0-4000-873c-2dc3b86cb200)
			1. [New graph](#18383acc-d4b0-4000-8323-fb73ec9cf800)
		1. [New Request](#18383acc-d4c0-4000-80e9-2029ede92d00)
		1. [New Request](#18383acc-d4c0-4000-816a-ab8540e27400)
	1. [[UAT] Obtain access token for a user](#18383acc-d4c0-4000-8f4a-f4fd92ff2100)
	1. [[SAT] Obtain accsess token from a service account](#18383acc-d4d0-4000-84a6-b6950dddfc00)
		1. [Ex: [SAT] Obtain accsess token from a service account](#18383acc-d4d0-4000-84a6-b6950dddfc00_example_0)
	1. [[UAT] Retrieve-token](#18383acc-d4e0-4000-889e-ffc6e570b200)
1. [Authentication Management](#18383acc-d4f0-4000-881c-756848744b00)
	1. [Authenticator providers [SAT]](#18383acc-d4f0-4000-8374-2947ed475400)
	1. [Client authenticator providers [SAT] ](#18383acc-d4f0-4000-8ff3-1fe9368ce400)
	1. [Form action authenticator providers [SAT] ](#18383acc-d500-4000-8e94-ad64273b1500)
	1. [Form authenticator providers [SAT]](#18383acc-d500-4000-885e-5f3273da1e00)
	1. [Get configuration descriptions for all clients [SAT]](#18383acc-d500-4000-88ce-fe1c081e5a00)
	1. [Client authenticator providers description [SAT]](#18383acc-d510-4000-8153-a9838611cf00)
	1. [Authenticator configuration [SAT]](#18383acc-d550-4000-8223-a9f77df54c00)
	1. [Get authentication execution [SAT]](#18383acc-d550-4000-848b-01aff600c700)
	1. [Update authentication execution [SAT]](#18383acc-d560-4000-87fa-5a82a5e31e00)
	1. [Lower authentication execution priority [SAT]](#18383acc-d560-4000-8732-a92887e77900)
	1. [Raise authentication execution priority [SAT]](#18383acc-d560-4000-8e8d-533c8b41e600)
	1. [Create a new authentication flow [SAT]](#18383acc-d570-4000-8380-25f47fb67800)
	1. [Copy existing authentication flow [SAT]](#18383acc-d570-4000-871e-44942669b500)
	1. [Get authentication flows [SAT]](#18383acc-d570-4000-8c22-17f178e9bf00)
	1. [Get authentication executions for a flow [SAT]](#18383acc-d580-4000-8514-9e1c5191c800)
	1. [Get authentication executions for a flow [SAT]](#18383acc-d580-4000-8bc7-8745e2146500)
	1. [Update an authentication flow [SAT]](#18383acc-d580-4000-8136-2cbfca651a00)
	1. [Delete an authentication flow [SAT]](#18383acc-d590-4000-89e4-c3062adb0900)
	1. [Update authentication executions of a flow [SAT]](#18383acc-d590-4000-8885-3c00afafa400)
	1. [Add new authentication executions to a flow [SAT]](#18383acc-d590-4000-8b57-13746dd98000)
	1. [Register a new required actions [SAT]](#18383acc-d5a0-4000-8231-d823c7ed7900)
	1. [Get required actions [SAT]](#18383acc-d5a0-4000-8f34-e78ca450d100)
	1. [Get unregistered required actions [SAT]](#18383acc-d5a0-4000-8e85-648700bb5200)
	1. [Lower required actionâ€™s priority [SAT]](#18383acc-d5b0-4000-89c3-5ab0e5b2c000)
	1. [Raise required actionâ€™s priority [SAT]](#18383acc-d5b0-4000-82e6-c3ab41fc7b00)
	1. [Update required action [SAT]](#18383acc-d5b0-4000-81fa-89d5be2ab800)
	1. [Delete required action [SAT]](#18383acc-d5c0-4000-8257-cd82970ce400)
	1. [Get required actions for alias [SAT]](#18383acc-d5c0-4000-8fe6-8358978db300)
	1. [Add new flow with new execution to existing flow [SAT]](#18383acc-d5c0-4000-86ef-8896bd812f00)
	1. [Delete authentication execution [SAT]](#18383acc-d5c0-4000-8014-0ad23a0b3200)
	1. [Update authenticator configuration [SAT]](#18383acc-d5d0-4000-885d-db3d4cb40800)
	1. [Add authenticator configuration [SAT] Copy](#18383acc-d5d0-4000-80ac-5f51cb153000)
	1. [Delete authenticator configuration [SAT] ](#18383acc-d5d0-4000-846b-ba793474da00)
1. [Attack Detection](#18383acc-d5e0-4000-8e16-8275a2ca7f00)
	1. [Brute force users [SAT]](#18383acc-d5e0-4000-8d27-1a4eb44efe00)
	1. [Brute force specific user [SAT]](#18383acc-d5e0-4000-85a7-c88d2ca25b00)
	1. [Brute force specific user [SAT] Copy](#18383acc-d5e0-4000-8b17-b5672ec7cb00)
1. [Client Attribute Certificate](#18383acc-d5e0-4000-8be0-3eeaa088b400)
	1. [Get key info [SAT]](#18383acc-d5f0-4000-8d84-6ebae7ca9c00)
	1. [Get a keystore file for the client [SAT]](#18383acc-d5f0-4000-86b7-efe1a7790100)
	1. [Upload certificate and eventually private key [SAT]](#18383acc-d5f0-4000-8625-283a2d59f200)
	1. [Upload only certificate, not private key [SAT]](#18383acc-d5f0-4000-8a41-5a35a73b4d00)
	1. [Generate a new keypair and certificate [SAT]](#18383acc-d600-4000-8b49-91ee5bcba200)
	1. [Generate a new certificate with new key pair [SAT]](#18383acc-d600-4000-83f1-9245f2b23100)
1. [Client Initial Access](#18383acc-d600-4000-8971-bca39376a900)
	1. [Create a new initial access token [SAT]](#18383acc-d600-4000-819c-1b763861a400)
	1. [Get new initial access tokens [SAT]](#18383acc-d610-4000-8ed2-0b8c7f505e00)
	1. [Delete initial access token with id [SAT] Copy](#18383acc-d610-4000-894f-256c02646500)
1. [Client Registration Policy](#18383acc-d610-4000-8ec0-2cb2ba033c00)
	1. [Base path for retrieve providers  [SAT]](#18383acc-d610-4000-87d2-7f0d33103100)
1. [Client Role Mappings](#18383acc-d610-4000-83dd-b4e2957d3400)
	1. [Add client-level roles to the user role mapping [SAT]](#18383acc-d610-4000-898c-7fdb076c6700)
	1. [Add client-level roles to the user role mapping - without group [SAT]](#18383acc-d620-4000-885d-558419372e00)
	1. [Delete client-level roles from user role mapping [SAT]](#18383acc-d620-4000-828a-d8c6b7e4e600)
	1. [Get client-level role mappings for the user, and the app [SAT]](#18383acc-d620-4000-8944-aca726491d00)
	1. [Get available client-level roles that can be mapped to the user [SAT]](#18383acc-d630-4000-822a-67d3c82cae00)
	1. [Get effective client-level role mappings  - composite roles [SAT]](#18383acc-d630-4000-8b4f-102043bdc600)
	1. [Delete client-level roles from user role mapping [SAT]](#18383acc-d630-4000-8c97-050be4ec9000)
	1. [Get client-level role mappings for the user, and the app [SAT]](#18383acc-d630-4000-81be-77ecccc25000)
	1. [Get available client-level roles that can be mapped to the user [SAT]](#18383acc-d640-4000-858a-3111468ac500)
	1. [Get effective client-level role mapping + composite roles [SAT]](#18383acc-d640-4000-8a6c-9b3cb1bfb400)
1. [Client Scopes](#18383acc-d640-4000-890f-7b0dd3ada300)
	1. [Get client scopes belonging [SAT]](#18383acc-d640-4000-8d3e-c75cba4dbc00)
	1. [Get representation of the client scope [SAT]](#18383acc-d640-4000-8c69-3c10b104b400)
	1. [Delete the client scope[SAT]](#18383acc-d650-4000-8da5-85d9e4fc7a00)
	1. [Update the client scope [SAT]](#18383acc-d650-4000-85c3-3ee81f0f8800)
	1. [Create a new client scope [SAT]](#18383acc-d650-4000-8121-21d28f3da200)
1. [Clients](#18383acc-d660-4000-8c68-36911457b500)
	1. [Get clients [SAT]](#18383acc-d660-4000-82a2-af3fd77db700)
	1. [Get representation of the client [SAT]](#18383acc-d660-4000-8cb7-20e4fb7c5f00)
	1. [Generate a new secret for the client [SAT]](#18383acc-d660-4000-8b8c-408b3390b300)
	1. [Get secret for the client [SAT]](#18383acc-d660-4000-8f91-1db154fc8300)
	1. [Get the client providers [SAT]](#18383acc-d670-4000-8d14-375212d0ca00)
	1. [Register a cluster node with the client  [SAT]](#18383acc-d670-4000-8649-2bc99800d600)
	1. [Register a cluster node with the client  [SAT] Copy](#18383acc-d680-4000-8816-c56697b8a400)
	1. [Get client authorization permissions [SAT]](#18383acc-d680-4000-8a16-59a893605400)
	1. [Update client authorization permissions [SAT]](#18383acc-d690-4000-8b2c-69b259e8fd00)
	1. [Get representation of the client [SAT] Copy](#18383acc-d690-4000-81d4-b8a1dd104900)
	1. [Create a new client [SAT]](#18383acc-d690-4000-897d-9cc70a915100)
	1. [Create a new client [SAT] Copy](#18383acc-d6a0-4000-89e0-eb2293962500)
	1. [Get default client scopes [SAT]](#18383acc-d6a0-4000-8049-1721a8c11100)
	1. [Create JSON with payload of example access token [SAT]](#18383acc-d6a0-4000-87ca-485cc7611600)
	1. [Get effective scope mapping of all roles [SAT]](#18383acc-d6a0-4000-8b4b-16f990948900)
	1. [Get roles without scope and access token [SAT]](#18383acc-d6b0-4000-827c-753dfa5bb500)
	1. [Get all protocol mappers [SAT]](#18383acc-d6b0-4000-82bc-35b716a5d000)
	1. [Get application offline session count [SAT]](#18383acc-d6b0-4000-8bb1-cff6e31e3900)
	1. [Get application offline sessions [SAT]](#18383acc-d6b0-4000-822d-e7b64032e700)
	1. [Get optional client scopes[SAT]](#18383acc-d6c0-4000-85b6-6198549a2c00)
	1. [Add optional client scope to client [SAT]](#18383acc-d6c0-4000-8add-191a8d39f000)
	1. [Delete optional client scope to client [SAT]](#18383acc-d6c0-4000-892a-c48c83777200)
	1. [Add default client scope to client [SAT]](#18383acc-d6c0-4000-8901-f855ec487400)
	1. [Delete default client scope to client [SAT]](#18383acc-d6d0-4000-8583-e7eb51b64b00)
	1. [Push the clientâ€™s revocation policy to its admin URL [SAT] ](#18383acc-d6d0-4000-88b3-e1a863f0ad00)
	1. [Generate a new registration access token for the client [SAT] ](#18383acc-d6d0-4000-814a-59d8f4b20300)
	1. [Get a user dedicated to the service account [SAT] ](#18383acc-d6d0-4000-8aa5-51e6b9dad500)
	1. [Get application session count associated with this client [SAT] ](#18383acc-d6e0-4000-89ca-c9444b891e00)
	1. [Test if registered cluster nodes are available [SAT] ](#18383acc-d6e0-4000-87c5-dc09548a3c00)
	1. [Get user sessions associated with this client [SAT] ](#18383acc-d6e0-4000-8f5b-1a82a8119300)
1. [General information](#18383acc-d6e0-4000-819d-d9920636aa00)
	1. [Get certs information](#18383acc-d6e0-4000-851f-2437b3c08800)
	1. [Well known configuration](#18383acc-d6f0-4000-8c2c-49115d6de900)
	1. [User Info](#18383acc-d6f0-4000-8446-293aea810d00)
1. [Component](#18383acc-d6f0-4000-8fb6-74afb8216000)
	1. [Add components [SAT] ](#18383acc-d6f0-4000-8f68-c96931220f00)
	1. [Get components [SAT] ](#18383acc-d700-4000-8930-ebb3dcac3300)
	1. [Get a specific component [SAT]](#18383acc-d700-4000-8e2d-2eb0ea1e8800)
	1. [Get subcomponents [SAT]](#18383acc-d700-4000-8e2e-f192666e3800)
	1. [Update a specific component [SAT]](#18383acc-d700-4000-886b-c170d03ca000)
	1. [Update a specific component [SAT] Copy](#18383acc-d710-4000-80fa-b22d7f03de00)
1. [Groups](#18383acc-d710-4000-8a29-b7a571816000)
	1. [Get groups [SAT] ](#18383acc-d710-4000-8e1d-63899cc6d500)
	1. [Get specific group [SAT] ](#18383acc-d710-4000-8b6c-c0deb02dd700)
	1. [Get groups count [SAT] ](#18383acc-d710-4000-8a78-3b3e1335a600)
	1. [Create a group [SAT] ](#18383acc-d720-4000-8e41-5e8f0826f000)
	1. [Update group [SAT]](#18383acc-d720-4000-890d-0deab34d0500)
	1. [Delete group [SAT]](#18383acc-d720-4000-8e5c-2cf220f86700)
	1. [Add  subgroup [SAT] ](#18383acc-d720-4000-8baf-d179fde79400)
	1. [Return object authorization permissions [SAT] ](#18383acc-d730-4000-8fee-aa943aabc900)
	1. [Get group members [SAT] ](#18383acc-d730-4000-8d0f-19129cc1b800)
	1. [Update return object authorization permissions [SAT] ](#18383acc-d730-4000-82bb-5da0b5deab00)
1. [Identity Providers](#18383acc-d740-4000-81e9-417cba042800)
	1. [Import identity provider from uploaded JSON file [SAT] ](#18383acc-d740-4000-8188-9145b5186100)
	1. [Create a new identity provider [SAT] ](#18383acc-d740-4000-8236-ae64aefcda00)
	1. [Get identity providers [SAT] ](#18383acc-d740-4000-8564-b2cdb5186600)
	1. [Get the identity provider from alias [SAT] ](#18383acc-d740-4000-8d8d-0b55be28a900)
	1. [Return object stating client Authorization [SAT] ](#18383acc-d750-4000-8f5e-030f6f7dc100)
	1. [Return object stating client Authorization [SAT]  Copy](#18383acc-d750-4000-8038-2bc5d645ea00)
	1. [Export public broker configuration for identity provider [SAT] ](#18383acc-d750-4000-813c-347cb4360a00)
	1. [Update the identity provider [SAT] ](#18383acc-d750-4000-8722-1a8c4c0b6e00)
	1. [Delete the identity provider [SAT] ](#18383acc-d760-4000-8c3c-7f9444a4d400)
	1. [Get mapper types for identity provider [SAT] ](#18383acc-d760-4000-8038-99b64df24400)
	1. [Add a mapper to identity provider [SAT] ](#18383acc-d760-4000-8dbb-e0437e00c600)
	1. [Get mappes for the identity provider [SAT] ](#18383acc-d770-4000-8eae-4f865a616300)
	1. [Get mapper by id for the identity provider  [SAT] ](#18383acc-d770-4000-8f1e-247817146800)
	1. [Get identity providers  [SAT] ](#18383acc-d770-4000-81f8-ec40910eca00)
	1. [Update a mapper for the identity provider  [SAT] ](#18383acc-d770-4000-8460-41750d1c7d00)
	1. [Delete a mapper for the identity provider  [SAT]](#18383acc-d780-4000-8900-2cb931068300)
1. [Key](#18383acc-d780-4000-8f5a-40047456f400)
	1. [Get realm keys  [SAT] ](#18383acc-d780-4000-86a1-9b41f7e9a400)
1. [Protocol Mappers](#18383acc-d780-4000-8db1-010895bd6200)
	1. [Create mappers to identity provider [SAT] ](#18383acc-d780-4000-8306-a5102c75a400)
	1. [Create a mapper to identity provider [SAT] ](#18383acc-d790-4000-8ac7-9368e0605600)
	1. [Update the mapper[SAT] ](#18383acc-d790-4000-8238-f0b7f3845a00)
	1. [Update the mapper[SAT]  Copy](#18383acc-d790-4000-8579-13bb0ce83600)
	1. [Get mappers [SAT]  ](#18383acc-d790-4000-8b6c-bbb85ab62a00)
	1. [Get mappers by name for a specific protocol [SAT] ](#18383acc-d7a0-4000-8c77-41a4c5dd5f00)
	1. [Get exact mapper [SAT] ](#18383acc-d7a0-4000-86ec-a883eea22300)
	1. [Create multiple mappers for a client [SAT] ](#18383acc-d7a0-4000-84dd-d41c8c70ef00)
	1. [Create a mapper for a client [SAT] ](#18383acc-d7a0-4000-8edd-ffd9d904be00)
	1. [Get mappers for a client [SAT] ](#18383acc-d7b0-4000-8e26-2aa84c08dd00)
	1. [Get mapper for a specific client [SAT] ](#18383acc-d7b0-4000-8b81-b196f4c93200)
	1. [Get mappers by name for a specific protocol [SAT] ](#18383acc-d7b0-4000-8254-64cfe7fa4000)
	1. [Update the mapper [SAT] ](#18383acc-d7c0-4000-8dfa-1c485f9bf600)
	1. [Update the mapper [SAT]  Copy](#18383acc-d7c0-4000-805f-acffe3a75800)
1. [Realms Admin](#18383acc-d7c0-4000-856a-98f19e5d2900)
	1. [Get realm info [SAT] ](#18383acc-d7c0-4000-8b0a-21dc7e2e9300)
	1. [Get admin events of the realm [SAT] ](#18383acc-d7d0-4000-8d31-6826a3ac7300)
	1. [Delete all admin events [SAT] ](#18383acc-d7d0-4000-88d0-4b9dd602f300)
	1. [Add realm [SAT] ](#18383acc-d7d0-4000-82e9-a50e11088f00)
	1. [Update realm [SAT] ](#18383acc-d7d0-4000-8319-69f24104fb00)
	1. [Delete realm [SAT] ](#18383acc-d7e0-4000-8fa2-a23ca4dc7000)
	1. [Clear keys cache [SAT] ](#18383acc-d7e0-4000-88bd-c5a80c107100)
	1. [Clear realm cache [SAT] ](#18383acc-d7e0-4000-87ea-d0e1eb69f100)
	1. [Clear user cache [SAT] ](#18383acc-d7f0-4000-8208-ccdabfbc7200)
	1. [Base path for importing clients under this realm[SAT] ](#18383acc-d7f0-4000-86ef-b3261b5bd900)
	1. [Get client session stats Returns a JSON map [SAT]](#18383acc-d7f0-4000-8f1b-4797f8743200)
	1. [Get credential registrators [SAT]](#18383acc-d7f0-4000-85d3-6d584f3a2000)
	1. [Get realm default client scopes [SAT]](#18383acc-d800-4000-840b-57bd86f02e00)
	1. [Update a realm default client scope [SAT]](#18383acc-d800-4000-8708-03cda0738a00)
	1. [Delete a realm default client scope[SAT]](#18383acc-d800-4000-8723-6c4840737000)
	1. [Get group hierarchy [SAT]](#18383acc-d800-4000-813e-b6022bb32700)
	1. [Update group hierarchy [SAT]](#18383acc-d810-4000-889f-a69d04ffb300)
	1. [Delete group hierarchy [SAT]](#18383acc-d810-4000-83dc-2db4fa73f200)
	1. [Get realm optional client scopes [SAT]](#18383acc-d810-4000-8de9-432d559b4b00)
	1. [Update realm optional client scopes [SAT] ](#18383acc-d810-4000-8e8e-51a176704200)
	1. [Delete realm optional client scopes [SAT] ](#18383acc-d820-4000-840e-838ed3216500)
	1. [Get events [SAT] ](#18383acc-d820-4000-8545-743f8b46a200)
	1. [Delete events [SAT] ](#18383acc-d820-4000-8315-9b8113953a00)
	1. [Get events config [SAT] ](#18383acc-d820-4000-8426-2cc71f48dd00)
	1. [Update events config [SAT] ](#18383acc-d830-4000-8622-ec0222b1b900)
	1. [Get group from path [SAT] ](#18383acc-d830-4000-82e4-e941c0510e00)
	1. [Logout all users from session [SAT] ](#18383acc-d830-4000-860b-42459a8acb00)
	1. [Partial export of existing realm into a JSON file [SAT] ](#18383acc-d840-4000-894d-885b44425200)
	1. [Partial import from a JSON file to an existing realm [SAT] ](#18383acc-d840-4000-8e2c-8702d4957a00)
	1. [Push the realmâ€™s revocation policy [SAT] ](#18383acc-d840-4000-8b89-7939d0eba600)
	1. [Remove a specific user session [SAT] ](#18383acc-d850-4000-8787-3e6445851e00)
	1. [Test LDAP connection [SAT] ](#18383acc-d850-4000-8369-d31ecf248b00)
	1. [Test SMTP connection [SAT] ](#18383acc-d850-4000-8218-b2edecbbc100)
	1. [Get users-management-permissions [SAT] ](#18383acc-d860-4000-8a2f-8e76bdde7b00)
	1. [Update users-management-permissions [SAT] ](#18383acc-d860-4000-8816-f700439f0400)
1. [Role Mapper](#18383acc-d860-4000-8131-7c2610089c00)
	1. [Get role mappings [SAT] ](#18383acc-d860-4000-8c81-868b4c127d00)
	1. [Update role mappings [SAT] ](#18383acc-d860-4000-862c-f45738104200)
	1. [Get realm-level role mappings  [SAT] ](#18383acc-d870-4000-8d34-f2cf330a8800)
	1. [Get available realm-level role mappings  [SAT] ](#18383acc-d870-4000-861b-8dfa071dda00)
	1. [Delete realm-level role mappings  [SAT] ](#18383acc-d870-4000-8067-cc76916dab00)
	1. [Get effective realm-level role mappings  [SAT] ](#18383acc-d880-4000-81f6-43af14023b00)
	1. [Get role mappings [SAT] ](#18383acc-d880-4000-8003-80e3241fe400)
	1. [Get realm-level role mappings [SAT] ](#18383acc-d880-4000-895b-18f15db68f00)
	1. [Add realm-level role mappings to the user [SAT] ](#18383acc-d880-4000-8e90-0c0f91216700)
	1. [Delete realm-level role mappings to the user [SAT] ](#18383acc-d890-4000-8d1e-db55ab989a00)
	1. [Get realm-level roles that can be mapped [SAT] ](#18383acc-d890-4000-844b-028f8ba82300)
	1. [Get effective realm-level roles that can be mapped [SAT] ](#18383acc-d890-4000-8ca0-e90bea68f400)
1. [Roles](#18383acc-d890-4000-831f-d617e873ca00)
	1. [Get all roles for the realm or client [SAT] ](#18383acc-d890-4000-8bec-b348a7171700)
	1. [Create a new role for the realm or client [SAT] ](#18383acc-d8a0-4000-89b4-48228e520d00)
	1. [Get a role by name [SAT] ](#18383acc-d8a0-4000-83f8-0cc341ed0e00)
	1. [Update a role by name [SAT] ](#18383acc-d8a0-4000-8722-0e1adc9fbb00)
	1. [Delete a role by name [SAT] ](#18383acc-d8a0-4000-8832-c179d1839900)
	1. [Get a role by name composite [SAT] ](#18383acc-d8b0-4000-8820-d08e6030ce00)
	1. [Update a role by name composite [SAT]  ](#18383acc-d8b0-4000-8543-696aa2f12c00)
	1. [Delete a role by name composite [SAT] ](#18383acc-d8b0-4000-80d2-4b9b63e99e00)
	1. [Get an app-level roles for specified app role's composite [SAT] ](#18383acc-d8b0-4000-80b9-e34a5186e600)
	1. [Get realm-level roles of the roleâ€™s composite [SAT] ](#18383acc-d8c0-4000-81ab-1e03816dce00)
	1. [Return List of Groups that have the specified role name [SAT] ](#18383acc-d8c0-4000-83ef-9ba5faccca00)
	1. [Return initialized auth permissions [SAT] ](#18383acc-d8c0-4000-8301-1e428b358c00)
	1. [Update initialized auth permissions [SAT] ](#18383acc-d8d0-4000-836a-c2c7088eaf00)
	1. [Return List of Users that have the specified role name [SAT] ](#18383acc-d8d0-4000-8a73-e154307bc900)
	1. [Get all roles for the realm or client [SAT] ](#18383acc-d8d0-4000-8d8f-fec92db3a800)
	1. [Create a new role for the realm or client [SAT] ](#18383acc-d8e0-4000-8d18-b795c957eb00)
	1. [Get a role by name[SAT] ](#18383acc-d8e0-4000-83d1-38c68ce3a500)
	1. [Delete a role by name[SAT] ](#18383acc-d8e0-4000-843e-74d5eff9c500)
	1. [Update a role by name[SAT] ](#18383acc-d8e0-4000-8932-e13dbb5db000)
	1. [Add a composite to the role [SAT] ](#18383acc-d8e0-4000-8fbf-aa6566721200)
	1. [Delete a composite to the role [SAT] ](#18383acc-d8f0-4000-846a-cde5cf0bf000)
	1. [Get a composite to the role [SAT] ](#18383acc-d8f0-4000-88e0-01e66ac71a00)
	1. [Get an app-level roles for the specified app [SAT] ](#18383acc-d8f0-4000-8515-31333ff6ef00)
	1. [Get realm-level roles of the roleâ€™s composite [SAT] ](#18383acc-d8f0-4000-85b9-b350990afc00)
	1. [Return List of Groups that have the specified role name [SAT] ](#18383acc-d900-4000-8a3a-3b752d728300)
	1. [Get Authoirzation permissions have been initialized [SAT] ](#18383acc-d900-4000-8bd4-2d08af45dc00)
	1. [Update Authoirzation permissions have been initialized [SAT] ](#18383acc-d900-4000-8d2e-869981202300)
	1. [Return List of Users that have the specified role name [SAT] ](#18383acc-d900-4000-811b-950fc27bc100)
1. [Roles (by ID)](#18383acc-d910-4000-83e6-d9ffa798e600)
	1. [Get a specific roleâ€™s representation [SAT] ](#18383acc-d910-4000-84a5-a0acb1da4500)
	1. [Update a specific roleâ€™s representation [SAT]  Copy](#18383acc-d910-4000-8cd2-f35723134900)
	1. [Update a specific roleâ€™s representation [SAT]  Copy Copy](#18383acc-d910-4000-8e24-21eca6ec5f00)
	1. [Make the role a composite role by associating some child roles [SAT]](#18383acc-d910-4000-84a9-f0acbe46df00)
	1. [Get roleâ€™s children by providing the role is a composite [SAT]](#18383acc-d920-4000-8888-e6a40a654700)
	1. [Delete roleâ€™s children by providing the role is a composite [SAT]](#18383acc-d920-4000-8ea8-ab8513773e00)
	1. [Get client-level roles for the client that are in the roleâ€™s composite [SAT]](#18383acc-d920-4000-8bd0-badbe1e9d200)
	1. [Get realm-level roles that are in the roleâ€™s composite [SAT]](#18383acc-d930-4000-8215-f3cedbc05d00)
	1. [Get role Authoirzation permissions  [SAT]](#18383acc-d930-4000-8069-76bd190c5f00)
	1. [Get role Authoirzation permissions  [SAT] Copy](#18383acc-d930-4000-8269-d90294972d00)
1. [Scope Mappings](#18383acc-d930-4000-8919-87f632529200)
	1. [Get all scope mappings for the client [SAT]](#18383acc-d930-4000-851e-5edcdc0b2400)
	1. [Add client-level roles to the clientâ€™s scope [SAT]](#18383acc-d940-4000-8093-823928ba2200)
	1. [Get the roles associated with a clientâ€™s scope Returns roles for the client  [SAT]](#18383acc-d940-4000-81d7-0228b5b81700)
	1. [Get the roles associated with a clientâ€™s scope Returns roles for the client  [SAT]](#18383acc-d940-4000-827a-f5067ceb6b00)
	1. [Get the roles of the client  [SAT] ](#18383acc-d940-4000-8521-7bcd191a6b00)
	1. [Get the  effective client roles  [SAT] ](#18383acc-d950-4000-852c-ef64eec40600)
	1. [Add a set of realm-level roles to the clientâ€™s scope [SAT] ](#18383acc-d950-4000-84f6-59e9f79a8f00)
	1. [Get realm-level roles associated with the clientâ€™s scope [SAT] ](#18383acc-d950-4000-8247-42473be84c00)
	1. [Get realm-level roles associated with the clientâ€™s scope [SAT] ](#18383acc-d950-4000-8373-f06b85d13a00)
	1. [Get realm-level roles that are available to attach to this clientâ€™s scope [SAT] ](#18383acc-d960-4000-866a-e18ebca67100)
	1. [Get  a comprehensive total view of realm-level roles associated with the client [SAT] ](#18383acc-d960-4000-8e41-1af6b0133d00)
	1. [Get all scope mappings for the client  [SAT] ](#18383acc-d960-4000-8f17-6d0e7924c000)
	1. [Add client-level roles to the clientâ€™s scope  [SAT] ](#18383acc-d960-4000-8002-d502a944a500)
	1. [Delete client-level roles to the clientâ€™s scope  [SAT] ](#18383acc-d970-4000-8498-54971bd62200)
	1. [Get client-level roles to the clientâ€™s scope  [SAT] ](#18383acc-d970-4000-8a69-827de6034800)
	1. [Get available client-level roles to the clientâ€™s scope  [SAT] ](#18383acc-d970-4000-8a14-6f49cb7db200)
	1. [Get effective client-level roles to the clientâ€™s scope  [SAT] ](#18383acc-d970-4000-85a9-bd8ba8a10700)
	1. [Add a set of realm-level roles to the clientâ€™s scope  [SAT] ](#18383acc-d980-4000-88c8-478eeb252600)
	1. [Delete a set of realm-level roles to the clientâ€™s scope  [SAT] ](#18383acc-d980-4000-87ce-47b55f760500)
	1. [Get realm-level roles associated with the clientâ€™s scope  [SAT] ](#18383acc-d980-4000-889e-608f30ce6c00)
	1. [Get realm-level roles that are available to attach to this clientâ€™s scope  [SAT] ](#18383acc-d980-4000-8ed0-20a300006600)
	1. [Get effective realm-level roles that are available to attach to this clientâ€™s scope  [SAT] ](#18383acc-d990-4000-8e12-f230b9627000)
1. [User Storage Provider](#18383acc-d990-4000-8455-f5e92e4e3000)
	1. [Display simple name of usage provider  [SAT] ](#18383acc-d990-4000-8902-80a68b04bb00)
	1. [Remove imported users  [SAT] ](#18383acc-d990-4000-8d6b-9f2079d98c00)
	1. [Trigger sync  [SAT] ](#18383acc-d990-4000-87f7-48873caa6c00)
	1. [Unlink imported users from a storage provider  [SAT] ](#18383acc-d9a0-4000-84a2-803c7ca5a900)
	1. [Trigger sync to ldap mapper  [SAT] ](#18383acc-d9a0-4000-880b-7ed6bd6f8c00)
1. [Users](#18383acc-d9a0-4000-817a-e57ba63b8f00)
	1. [Get users  [SAT]](#18383acc-d9a0-4000-8596-20d9cf7f9800)
		1. [Ex: Get users  [SAT]](#18383acc-d9a0-4000-8596-20d9cf7f9800_example_0)
	1. [Create user [SAT]](#18383acc-d9b0-4000-8bcd-449e43069600)
	1. [Returns the number of users that match the given criteria [SAT]](#18383acc-d9b0-4000-89bf-094fc8d44e00)
	1. [Get representation of the user [SAT]](#18383acc-d9c0-4000-8db6-7a1f886dea00)
		1. [Ex: Get user [SAT]](#18383acc-d9c0-4000-8db6-7a1f886dea00_example_0)
	1. [Update the user [SAT]](#18383acc-d9c0-4000-85ac-8f234bfce900)
	1. [Delete the user [SAT]](#18383acc-d9d0-4000-8889-30612782a300)
	1. [Return credential types  [SAT]](#18383acc-d9d0-4000-82b1-205f29331b00)
	1. [Get consents granted by the user  [SAT]](#18383acc-d9d0-4000-85b5-8d5f1b30fb00)
	1. [Delete consents granted by the user  [SAT]](#18383acc-d9d0-4000-8a71-721aebb93300)
	1. [Get credentials  [SAT]](#18383acc-d9e0-4000-8cda-9b463cc7c600)
		1. [Ex: Get credentials [SAT]](#18383acc-d9e0-4000-8cda-9b463cc7c600_example_0)
	1. [Remove a credential for a user  [SAT]](#18383acc-d9e0-4000-883e-009d2bd52e00)
	1. [Move a credential to a position behind another credential  [SAT]](#18383acc-d9f0-4000-881d-4e19f3af6500)
	1. [Move a credential to a first position in the credentials list of the user [SAT]](#18383acc-da00-4000-87c0-7bafc66a7100)
	1. [Update a credential label for a user [SAT]](#18383acc-da00-4000-871d-35f1800f5100)
	1. [Disable all credentials for a user of a specific type [SAT]](#18383acc-da00-4000-8ba1-3656f8f0cf00)
	1. [Send an update account email to the user [SAT]](#18383acc-da00-4000-81d2-4a1adc9fc200)
	1. [Deprecated: Reset password email [SAT]](#18383acc-da10-4000-8fe8-76cb361f7d00)
	1. [Get social logins associated with the user [SAT]](#18383acc-da10-4000-8b6a-f28aa1928b00)
	1. [Add a social login provider to the user [SAT]](#18383acc-da10-4000-8152-d62ba0a05300)
	1. [Remove a social login provider from user [SAT]](#18383acc-da10-4000-888a-85456549f000)
	1. [Get groups [SAT] ](#18383acc-da10-4000-8cbe-17cacc809400)
		1. [Ex: Get groups [SAT] ](#18383acc-da10-4000-8cbe-17cacc809400_example_0)
	1. [Get groups count [SAT] ](#18383acc-da20-4000-832f-ab6e3677f100)
	1. [Add group [SAT] ](#18383acc-da20-4000-8bed-ce88f8ebc800)
	1. [Delete group [SAT] ](#18383acc-da30-4000-8c1c-c309bd451900)
	1. [Impersonate the user [SAT] ](#18383acc-da30-4000-86ea-73c236fb7100)
		1. [Ex: Impersonate the user [SAT] ](#18383acc-da30-4000-86ea-73c236fb7100_example_0)
	1. [Logout user [SAT]](#18383acc-da30-4000-893a-f8a7989a2d00)
	1. [Get offline sessions associated with the user and client [SAT]](#18383acc-da30-4000-81a9-40dcf398a600)
	1. [Set up a new password for the user [SAT]](#18383acc-da40-4000-8509-69db35abd300)
	1. [Send an email-verification email  [SAT]](#18383acc-da40-4000-8d3c-2a7338024b00)
	1. [Get sessions associated with the user  [SAT]](#18383acc-da40-4000-8df8-964b9ba3f400)
		1. [Ex: Get sessions associated with the user  [SAT]](#18383acc-da40-4000-8df8-964b9ba3f400_example_0)
1. [Root](#18383acc-da50-4000-8720-402fc9f8ec00)
	1. [Get all  [SAT]](#18383acc-da50-4000-84bc-10fcc987ea00)
		1. [Ex: Get sessions associated with the user  [SAT] Copy](#18383acc-da50-4000-84bc-10fcc987ea00_example_0)
</details>


## Access Token <a name="18383acc-d460-4000-83f1-59b61469a400"></a>

asdasdsadas

## Folder1 <a name="18383acc-d470-4000-8885-dbb3efa13600"></a>



## Folder1.1 <a name="18383acc-d470-4000-8923-43e4af88b200"></a>



### GET New Request <a name="18383acc-d470-4000-8554-ada9e46a5f00"></a>


`https://api.fis.vn:9999/fis/api/checkout_all`


**Request Headers**

N/A

**Request Body** `json`


```json
{
  "short_name": "Time Sheet",
  "name": "Timesheet Management",
  "description": "Timesheet Management Tool",
  "permissions": [
    "storage"
  ],
  "action": {
    "default_popup": "index.html",
    "default_title": "Timesheet Management"
  },
  "manifest_version": 3,
  "version": "1.3.1",
  "icons": {
    "16": "favicon.ico",
    "48": "icon.png",
    "128": "icon.png"
  }
}
```


**Example**  *New Example* <a name="18383acc-d470-4000-8554-ada9e46a5f00_example_0"></a>


`https://api.fis.vn:9999/fis/api/checkout_all`

**Request Headers**

N/A

**Request Body** `json`


```json
{
  "short_name": "Time Sheet",
  "name": "Timesheet Management",
  "description": "Timesheet Management Tool",
  "permissions": [
    "storage"
  ],
  "action": {
    "default_popup": "index.html",
    "default_title": "Timesheet Management"
  },
  "manifest_version": 3,
  "version": "1.3.1",
  "icons": {
    "16": "favicon.ico",
    "48": "icon.png",
    "128": "icon.png"
  }
}
```


**Example Response**


```json
{
    "short_name": "Time Sheet",
    "name": "Timesheet Management",
    "description": "Timesheet Management Tool",
    "permissions": [
        "storage"
    ],
    "action": {
        "default_popup": "index.html",
        "default_title": "Timesheet Management"
    },
    "manifest_version": 3,
    "version": "1.3.1",
    "icons": {
        "16": "favicon.ico",
        "48": "icon.png",
        "128": "icon.png"
    }
}
```


**Example**  *New Example 2* <a name="18383acc-d470-4000-8554-ada9e46a5f00_example_1"></a>


`https://api.fis.vn:9999/fis/api/checkout_all`

**Request Headers**

N/A

**Request Body** `json`


```json
{
  "short_name": "2222222"
}
```


**Example Response**


```json
{
    "short_name": "2222222"
}
```


### GET form data <a name="18383acc-d4a0-4000-8b09-854efcda7200"></a>


`N/A`


**Request Headers**

N/A

**Request Body** `formdata`


|Key|Value|
| --- | --- |
|abc|123|



### GET New binary <a name="18383acc-d4b0-4000-8de9-9da76964d800"></a>


`https://api.fis.vn:9999/fis/api/checkout_all`


**Request Headers**

N/A

**Request Body** `file`

Does not support display!

### GET New None <a name="18383acc-d4b0-4000-873c-2dc3b86cb200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/push-revocation`


**Request Headers**

N/A

**Request Body**

N/A

### GET New graph <a name="18383acc-d4b0-4000-8323-fb73ec9cf800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/push-revocation`


**Request Headers**

N/A

**Request Body** `graphql`


```json
query {
    
}
```


### GET New Request <a name="18383acc-d4c0-4000-80e9-2029ede92d00"></a>


`N/A`


**Request Headers**

N/A

**Request Body** `raw`


```json
<request body="">anc</request>
```


### GET New Request <a name="18383acc-d4c0-4000-816a-ab8540e27400"></a>


`N/A`


**Request Headers**

N/A

**Request Body**

N/A

### POST [UAT] Obtain access token for a user <a name="18383acc-d4c0-4000-8f4a-f4fd92ff2100"></a>


`{{keycloak_url}}/realms/{{realm}}/protocol/openid-connect/token`

Obtain UAT = user access token from a user in realm

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/x-www-form-urlencoded|



**Request Body** `urlencoded`


|Key|Value|
| --- | --- |
|client_id|admin-cli|
|username|thor|
|password|thor|
|grant_type|password|



### POST [SAT] Obtain accsess token from a service account <a name="18383acc-d4d0-4000-84a6-b6950dddfc00"></a>


`{{keycloak_url}}/realms/{{realm}}/protocol/openid-connect/token`

Obtain SAT (service account token)

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/x-www-form-urlencoded|



**Request Body** `urlencoded`


|Key|Value|
| --- | --- |
|client_id|service-account|
|client_secret|boqvkrklrBVRR3fzLnnabyukP4JNiTCL|
|grant_type|client_credentials|



**Example**  *[SAT] Obtain accsess token from a service account* <a name="18383acc-d4d0-4000-84a6-b6950dddfc00_example_0"></a>


`{{keycloak_url}}/realms/{{realm}}/protocol/openid-connect/token`


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/x-www-form-urlencoded|



**Request Body** `urlencoded`


|Key|Value|
| --- | --- |
|client_id|service-account|
|client_secret|e405ebed-432a-4625-bff7-bd4f688d4340|
|grant_type|client_credentials|



**Example Response**


```json
{
    "access_token": "eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJZTE1yUlJ5OEJ1WmFSZ2otcFIydGZTWmZ4TWVZM3dNM01rYUQyUndiN3pFIn0.eyJleHAiOjE1ODkxMzc3NzIsImlhdCI6MTU4OTEzNzQ3MiwianRpIjoiOTY2ODY4NzAtOWU2My00YjE5LWFiNWYtYzI0Nzg3OGY2NTYxIiwiaXNzIjoiaHR0cDovLzEyNy4wLjAuMTo4MDgwL2F1dGgvcmVhbG1zL2hlcm9lcyIsImF1ZCI6WyJyZWFsbS1tYW5hZ2VtZW50IiwiYWNjb3VudCJdLCJzdWIiOiIzY2QwMmZjYS0wZjkyLTRkMjYtODViMC04NzJlODIwNGRiOTEiLCJ0eXAiOiJCZWFyZXIiLCJhenAiOiJzZXJ2aWNlLWFjY291bnQiLCJzZXNzaW9uX3N0YXRlIjoiYmE5YTA5ZmYtMTIyYi00YmRkLWI1ODUtODg2ZTQwN2ExMjk5IiwiYWNyIjoiMSIsInJlYWxtX2FjY2VzcyI6eyJyb2xlcyI6WyJvZmZsaW5lX2FjY2VzcyIsInVtYV9hdXRob3JpemF0aW9uIl19LCJyZXNvdXJjZV9hY2Nlc3MiOnsicmVhbG0tbWFuYWdlbWVudCI6eyJyb2xlcyI6WyJ2aWV3LWlkZW50aXR5LXByb3ZpZGVycyIsInZpZXctcmVhbG0iLCJtYW5hZ2UtaWRlbnRpdHktcHJvdmlkZXJzIiwiaW1wZXJzb25hdGlvbiIsInJlYWxtLWFkbWluIiwiY3JlYXRlLWNsaWVudCIsIm1hbmFnZS11c2VycyIsInF1ZXJ5LXJlYWxtcyIsInZpZXctYXV0aG9yaXphdGlvbiIsInF1ZXJ5LWNsaWVudHMiLCJxdWVyeS11c2VycyIsIm1hbmFnZS1ldmVudHMiLCJtYW5hZ2UtcmVhbG0iLCJ2aWV3LWV2ZW50cyIsInZpZXctdXNlcnMiLCJ2aWV3LWNsaWVudHMiLCJtYW5hZ2UtYXV0aG9yaXphdGlvbiIsIm1hbmFnZS1jbGllbnRzIiwicXVlcnktZ3JvdXBzIl19LCJhY2NvdW50Ijp7InJvbGVzIjpbIm1hbmFnZS1hY2NvdW50IiwibWFuYWdlLWFjY291bnQtbGlua3MiLCJ2aWV3LXByb2ZpbGUiXX19LCJzY29wZSI6InByb2ZpbGUgZW1haWwiLCJjbGllbnRIb3N0IjoiMTcyLjE3LjAuMSIsImNsaWVudElkIjoic2VydmljZS1hY2NvdW50IiwiZW1haWxfdmVyaWZpZWQiOmZhbHNlLCJwcmVmZXJyZWRfdXNlcm5hbWUiOiJzZXJ2aWNlLWFjY291bnQtc2VydmljZS1hY2NvdW50IiwiY2xpZW50QWRkcmVzcyI6IjE3Mi4xNy4wLjEifQ.QjsnpAubiCn6ymCkFL4yNe-D4sYMfFEiNxN1TXXbYy1MlVYWAYemEWE8RI3aYnnzdvwiwMnXTnlChN-PjI6W8hMjRsAKpWAduA-xkULCU9GHv-p57KvB6ad0nNV01B4SSnJNjfOx-qw5zQM3-yBKIDNZLUOgwdqC-hRQkpDqSUMvE1e3POSbEi4LjGA0fk4vdB5pphe7F5iXOPwG6bt-VErN8CVXFemS8JfKkCU-YcZlaVOTXXoCJdaqwbcOR8gBiJhwWfhe7XR2w3eQJuZZa3cMp9S7RqUmTHE8b9N2VHmUNun_UO2adOCobZRQ2oRsw3tV-N6Y54NU_W-ZQEnqcw",
    "expires_in": 300,
    "refresh_expires_in": 1800,
    "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICIxYmVmYmM2NS0zN2EyLTQxZTctYjM2NC1lMjc0NWQ4NDRmNzcifQ.eyJleHAiOjE1ODkxMzkyNzIsImlhdCI6MTU4OTEzNzQ3MiwianRpIjoiMDI5ODAxYzEtODliZi00MTIxLTlhZDMtNzFkYTVlYzQ5NzNlIiwiaXNzIjoiaHR0cDovLzEyNy4wLjAuMTo4MDgwL2F1dGgvcmVhbG1zL2hlcm9lcyIsImF1ZCI6Imh0dHA6Ly8xMjcuMC4wLjE6ODA4MC9hdXRoL3JlYWxtcy9oZXJvZXMiLCJzdWIiOiIzY2QwMmZjYS0wZjkyLTRkMjYtODViMC04NzJlODIwNGRiOTEiLCJ0eXAiOiJSZWZyZXNoIiwiYXpwIjoic2VydmljZS1hY2NvdW50Iiwic2Vzc2lvbl9zdGF0ZSI6ImJhOWEwOWZmLTEyMmItNGJkZC1iNTg1LTg4NmU0MDdhMTI5OSIsInNjb3BlIjoicHJvZmlsZSBlbWFpbCJ9.AoD5T4OTm4ueUp4Hi1YTL4Wk2XuqqCJE-7pqUjco5sM",
    "token_type": "bearer",
    "not-before-policy": 1589105644,
    "session_state": "ba9a09ff-122b-4bdd-b585-886e407a1299",
    "scope": "profile email"
}
```


### POST [UAT] Retrieve-token <a name="18383acc-d4e0-4000-889e-ffc6e570b200"></a>


`{{keycloak_url}}/realms/{{realm}}/protocol/openid-connect/token`



**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/x-www-form-urlencoded|



**Request Body** `urlencoded`


|Key|Value|
| --- | --- |
|username|tester|
|password|test|
|grant_type|password|
|client_id|{{clientId}}|
|client_secret|{{clientSecret}}|
|scope|openid|



## Authentication Management <a name="18383acc-d4f0-4000-881c-756848744b00"></a>



### GET Authenticator providers [SAT] <a name="18383acc-d4f0-4000-8374-2947ed475400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/authenticator-providers`

Get authenticator providers Returns a list of authenticator providers.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/x-www-form-urlencoded|



**Request Body**

N/A

### GET Client authenticator providers [SAT] <a name="18383acc-d4f0-4000-8ff3-1fe9368ce400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/client-authenticator-providers`

Get client authenticator providers Returns a list of client authenticator providers.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/x-www-form-urlencoded|



**Request Body**

N/A

### GET Form action authenticator providers [SAT] <a name="18383acc-d500-4000-8e94-ad64273b1500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/form-action-providers`

Get form action providers Returns a list of form action providers.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/x-www-form-urlencoded|



**Request Body**

N/A

### GET Form authenticator providers [SAT] <a name="18383acc-d500-4000-885e-5f3273da1e00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/form-providers`

Get form providers Returns a list of form providers.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/x-www-form-urlencoded|



**Request Body**

N/A

### GET Get configuration descriptions for all clients [SAT] <a name="18383acc-d500-4000-88ce-fe1c081e5a00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/per-client-config-description`

Get configuration descriptions for all clients

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/x-www-form-urlencoded|



**Request Body**

N/A

### GET Client authenticator providers description [SAT] <a name="18383acc-d510-4000-8153-a9838611cf00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/config-description/{{providerId}}`

Get authenticator providerâ€™s configuration description (e.g. client-jwt)

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/x-www-form-urlencoded|



**Request Body**

N/A

### GET Authenticator configuration [SAT] <a name="18383acc-d550-4000-8223-a9f77df54c00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/config/{{configurationId}}`

Get authenticator configuration

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/x-www-form-urlencoded|



**Request Body**

N/A

### GET Get authentication execution [SAT] <a name="18383acc-d550-4000-848b-01aff600c700"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/executions/{{executionId}}`

Get Single Execution

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/x-www-form-urlencoded|



**Request Body**

N/A

### POST Update authentication execution [SAT] <a name="18383acc-d560-4000-87fa-5a82a5e31e00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/executions/{{executionId}}`

Update Execution

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "23e192b0-2811-4441-9f66-99bd1c4687f6",
    "authenticator": "auth-cookie",
    "authenticatorFlow": false,
    "requirement": "ALTERNATIVE",
    "priority": 10,
    "parentFlow": "bf2ffb04-39eb-4de9-b302-29f8d2735cbb",
    "enabled": true,
    "alternative": true,
    "required": false,
    "conditional": false,
    "disabled": false
}
```


### POST Lower authentication execution priority [SAT] <a name="18383acc-d560-4000-8732-a92887e77900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/executions/{{executionId}}/lower-priority`

Lower executionâ€™s priority

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Raise authentication execution priority [SAT] <a name="18383acc-d560-4000-8e8d-533c8b41e600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/executions/{{executionId}}/raise-priority`

Raise executionâ€™s priority

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Create a new authentication flow [SAT] <a name="18383acc-d570-4000-8380-25f47fb67800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/flows`

Create a new authentication flow

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
        "alias": "browser-for-fun",
        "description": "browser based authentication",
        "providerId": "basic-flow",
        "topLevel": true,
        "builtIn": true,
        "authenticationExecutions": [
            {
                "authenticator": "auth-cookie",
                "requirement": "ALTERNATIVE",
                "priority": 10,
                "userSetupAllowed": false,
                "autheticatorFlow": false
            },
            {
                "authenticator": "auth-spnego",
                "requirement": "DISABLED",
                "priority": 20,
                "userSetupAllowed": false,
                "autheticatorFlow": false
            },
            {
                "authenticator": "identity-provider-redirector",
                "requirement": "ALTERNATIVE",
                "priority": 25,
                "userSetupAllowed": false,
                "autheticatorFlow": false
            },
            {
                "requirement": "ALTERNATIVE",
                "priority": 30,
                "flowAlias": "forms",
                "userSetupAllowed": false,
                "autheticatorFlow": true
            }
        ]
    }
```


### POST Copy existing authentication flow [SAT] <a name="18383acc-d570-4000-871e-44942669b500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/flows/{{LowerCaseAliasFlow}}/copy`

Copy existing authentication flow under a new name The new name is given as 'newName' attribute of the passed JSON object

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"newName": "newName"
}
```


### GET Get authentication flows [SAT] <a name="18383acc-d570-4000-8c22-17f178e9bf00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/flows`

Get authentication flows Returns a list of authentication flows.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get authentication executions for a flow [SAT] <a name="18383acc-d580-4000-8514-9e1c5191c800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/flows/{{LowerCaseAliasFlow}}/executions`

Get authentication executions for a flow

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get authentication executions for a flow [SAT] <a name="18383acc-d580-4000-8bc7-8745e2146500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/flows/{{flowId}}`

Get authentication flow for id

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update an authentication flow [SAT] <a name="18383acc-d580-4000-8136-2cbfca651a00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/flows/{{flowId}}`

Update an authentication flow

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "alias": "browser",
    "description": "browser based authentication - still getting error, but updates me",
    "providerId": "basic-flow",
    "topLevel": true,
    "builtIn": true
}
```


### DELETE Delete an authentication flow [SAT] <a name="18383acc-d590-4000-89e4-c3062adb0900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/flows/{{deleteFlowId}}`

Delete an authentication flow
*** Replace the deleteFlowId variable with the flow id you want to delete
Be aware that an original flow cannot be deleted

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update authentication executions of a flow [SAT] <a name="18383acc-d590-4000-8885-3c00afafa400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/flows/{{LowerCaseAliasFlow}}/executions`

Update authentication executions of a flow

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
	{
        "id": "23e192b0-2811-4441-9f66-99bd1c4687f6",
        "requirement": "ALTERNATIVE",
        "displayName": "Cookie",
        "requirementChoices": [
            "REQUIRED",
            "ALTERNATIVE",
            "DISABLED"
        ],
        "configurable": false,
        "providerId": "auth-cookie",
        "level": 0,
        "index": 0
    }
```


### POST Add new authentication executions to a flow [SAT] <a name="18383acc-d590-4000-8b57-13746dd98000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/flows/{{LowerCaseAliasFlow}}/executions/execution`

Add new authentication execution to a flow
*** works only with a copied Flow!! 

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{"provider":"reset-password"}
```


### POST Register a new required actions [SAT] <a name="18383acc-d5a0-4000-8231-d823c7ed7900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/register-required-action`

Register a new required actions

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"providerId":"reset-password",
	"name": "new-reset-password"
}
```


### GET Get required actions [SAT] <a name="18383acc-d5a0-4000-8f34-e78ca450d100"></a>


`{{keycloak_url}}/auth/admin/realms/{{realm}}/authentication/required-actions`

Get required actions Returns a list of required actions.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get unregistered required actions [SAT] <a name="18383acc-d5a0-4000-8e85-648700bb5200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/unregistered-required-actions`

Get unregistered required actions Returns a list of unregistered required actions.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Lower required actionâ€™s priority [SAT] <a name="18383acc-d5b0-4000-89c3-5ab0e5b2c000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/required-actions/{{aliasRequiredAction}}/lower-priority`

Lower required actionâ€™s priority

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Raise required actionâ€™s priority [SAT] <a name="18383acc-d5b0-4000-82e6-c3ab41fc7b00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/required-actions/{{aliasRequiredAction}}/raise-priority`

Raise required actionâ€™s priority

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update required action [SAT] <a name="18383acc-d5b0-4000-81fa-89d5be2ab800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/required-actions/{{aliasRequiredAction}}`

Update required action

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
    {
    	"alias": "UPDATE_PASSWORD",
        "name": "Update Password +",
        "providerId": "UPDATE_PASSWORD",
        "enabled": true,
        "defaultAction": false,
        "priority": 30,
        "config": {}
    }
```


### DELETE Delete required action [SAT] <a name="18383acc-d5c0-4000-8257-cd82970ce400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/required-actions/{{aliasRequiredAction}}`

Delete required action

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get required actions for alias [SAT] <a name="18383acc-d5c0-4000-8fe6-8358978db300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/required-actions/{{aliasRequiredAction}}`

Get required action for alias

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Add new flow with new execution to existing flow [SAT] <a name="18383acc-d5c0-4000-86ef-8896bd812f00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/flows/{{LowerCaseAliasFlow}}/executions/flow`

Add new flow with new execution to existing flow

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{"provider":"reset-password",
	"alias": "bff",
	"type": "generic",
	"description": "new flow bff"
}
```


### DELETE Delete authentication execution [SAT] <a name="18383acc-d5c0-4000-8014-0ad23a0b3200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/executions/{{executionId}}`

Delete execution

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/x-www-form-urlencoded|



**Request Body**

N/A

### PUT Update authenticator configuration [SAT] <a name="18383acc-d5d0-4000-885d-db3d4cb40800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/config/{{configurationId}}`

Update authenticator configuration

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
"config": {
        "update.profile.on.first.login": "on"
    }
}
```


### POST Add authenticator configuration [SAT] Copy <a name="18383acc-d5d0-4000-80ac-5f51cb153000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/config/{{configurationId}}`

Add new authentication execution

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
"config": {
        "update.profile.on.first.login": "on"
    }
}
```


### DELETE Delete authenticator configuration [SAT] <a name="18383acc-d5d0-4000-846b-ba793474da00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/authentication/config/{{configurationId}}`

Delete authenticator configuration

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

## Attack Detection <a name="18383acc-d5e0-4000-8e16-8275a2ca7f00"></a>



### DELETE Brute force users [SAT] <a name="18383acc-d5e0-4000-8d27-1a4eb44efe00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/attack-detection/brute-force/users`

Clear any user login failures for all users This can release temporary disabled users
**Request Headers**

N/A

**Request Body**

N/A

### DELETE Brute force specific user [SAT] <a name="18383acc-d5e0-4000-85a7-c88d2ca25b00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/attack-detection/brute-force/users/{{userId}}`

Clear any user login failures for the user This can release temporary disabled user
* Add userId
**Request Headers**

N/A

**Request Body**

N/A

### GET Brute force specific user [SAT] Copy <a name="18383acc-d5e0-4000-8b17-b5672ec7cb00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/attack-detection/brute-force/users/{{userId}}`

Get status of a username in brute force detection. 
* Add userId
**Request Headers**

N/A

**Request Body**

N/A

## Client Attribute Certificate <a name="18383acc-d5e0-4000-8be0-3eeaa088b400"></a>



### GET Get key info [SAT] <a name="18383acc-d5f0-4000-8d84-6ebae7ca9c00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/certificates/{{attr}}`

Get key info

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Get a keystore file for the client [SAT] <a name="18383acc-d5f0-4000-86b7-efe1a7790100"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/certificates/{{attr}}/download`

Get a keystore file for the client, containing private key and public certificate

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"storePassword": "app",
	"format": "JKS"
}
```


### POST Upload certificate and eventually private key [SAT] <a name="18383acc-d5f0-4000-8625-283a2d59f200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/certificates/{{attr}}/upload`

Upload certificate and eventually private key

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|multipart/form-data|



**Request Body** `file`

Does not support display!

### POST Upload only certificate, not private key [SAT] <a name="18383acc-d5f0-4000-8a41-5a35a73b4d00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/certificates/{{attr}}/upload-certificate`

Upload only certificate, not private key

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|multipart/form-data|



**Request Body** `file`

Does not support display!

### POST Generate a new keypair and certificate [SAT] <a name="18383acc-d600-4000-8b49-91ee5bcba200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/certificates/{{attr}}/generate-and-download`

Generate a new keypair and certificate, and get the private key file Generates a keypair and certificate and serves the private key in a specified keystore format.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"storePassword": "app",
	"format": "JKS"
}
```


### POST Generate a new certificate with new key pair [SAT] <a name="18383acc-d600-4000-83f1-9245f2b23100"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/certificates/{{attr}}/generate`

Generate a new certificate with new key pair

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

## Client Initial Access <a name="18383acc-d600-4000-8971-bca39376a900"></a>



### POST Create a new initial access token [SAT] <a name="18383acc-d600-4000-819c-1b763861a400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients-initial-access`

Create a new initial access token.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"count": 5,
	"expiration": 5
}
```


### GET Get new initial access tokens [SAT] <a name="18383acc-d610-4000-8ed2-0b8c7f505e00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients-initial-access`

Get a list of new initial access tokens

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Delete initial access token with id [SAT] Copy <a name="18383acc-d610-4000-894f-256c02646500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients-initial-access/50fadd33-d8ee-47cc-b094-33fff7535787`



**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

## Client Registration Policy <a name="18383acc-d610-4000-8ec0-2cb2ba033c00"></a>



### GET Base path for retrieve providers  [SAT] <a name="18383acc-d610-4000-87d2-7f0d33103100"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-registration-policy/providers`

Base path for retrieve providers with the configProperties properly filled

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

## Client Role Mappings <a name="18383acc-d610-4000-83dd-b4e2957d3400"></a>



### POST Add client-level roles to the user role mapping [SAT] <a name="18383acc-d610-4000-898c-7fdb076c6700"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}/role-mappings/clients/{{clientId}}`

Add client-level roles to the user role mapping

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
[ 
	{
        "id": "647ba3cc-5d4d-4a5a-a67f-ed594f43a5b6",
        "name": "Sneaky",
        "composite": false,
        "clientRole": true,
        "containerId": "5725d549-faac-4a30-bab3-7b8370c19ce3"
    }
]

```


### POST Add client-level roles to the user role mapping - without group [SAT] <a name="18383acc-d620-4000-885d-558419372e00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/role-mappings/clients/{{clientId}}`

Add client-level roles to the user role mapping

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
[ 
	{
        "id": "647ba3cc-5d4d-4a5a-a67f-ed594f43a5b6",
        "name": "Sneaky",
        "composite": false,
        "clientRole": true,
        "containerId": "5725d549-faac-4a30-bab3-7b8370c19ce3"
    }
]

```


### DELETE Delete client-level roles from user role mapping [SAT] <a name="18383acc-d620-4000-828a-d8c6b7e4e600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/role-mappings/clients/{{clientId}}`

Delete client-level roles from user role mapping

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
[ 
	{
        "id": "647ba3cc-5d4d-4a5a-a67f-ed594f43a5b6",
        "name": "Sneaky",
        "composite": false,
        "clientRole": true,
        "containerId": "5725d549-faac-4a30-bab3-7b8370c19ce3"
    }
]

```


### GET Get client-level role mappings for the user, and the app [SAT] <a name="18383acc-d620-4000-8944-aca726491d00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/role-mappings/clients/{{clientId}}`

Get client-level role mappings for the user, and the app

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get available client-level roles that can be mapped to the user [SAT] <a name="18383acc-d630-4000-822a-67d3c82cae00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/role-mappings/clients/{{clientId}}/available`

Get available client-level roles that can be mapped to the user

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get effective client-level role mappings  - composite roles [SAT] <a name="18383acc-d630-4000-8b4f-102043bdc600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/role-mappings/clients/{{clientId}}/composite`

Get effective client-level role mappings This recurses any composite roles

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Delete client-level roles from user role mapping [SAT] <a name="18383acc-d630-4000-8c97-050be4ec9000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}/role-mappings/clients/{{clientId}}`

Delete client-level roles from user role mapping

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
[ 
	{
        "id": "647ba3cc-5d4d-4a5a-a67f-ed594f43a5b6",
        "name": "Sneaky",
        "composite": false,
        "clientRole": true,
        "containerId": "5725d549-faac-4a30-bab3-7b8370c19ce3"
    }
]

```


### GET Get client-level role mappings for the user, and the app [SAT] <a name="18383acc-d630-4000-81be-77ecccc25000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}/role-mappings/clients/{{clientId}}`

Get client-level role mappings for the user, and the app

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get available client-level roles that can be mapped to the user [SAT] <a name="18383acc-d640-4000-858a-3111468ac500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}/role-mappings/clients/{{clientId}}/available`

Get available client-level roles that can be mapped to the user

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get effective client-level role mapping + composite roles [SAT] <a name="18383acc-d640-4000-8a6c-9b3cb1bfb400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}/role-mappings/clients/{{clientId}}/composite`

Get effective client-level role mappings This recurses any composite roles

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

## Client Scopes <a name="18383acc-d640-4000-890f-7b0dd3ada300"></a>



### GET Get client scopes belonging [SAT] <a name="18383acc-d640-4000-8d3e-c75cba4dbc00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes`

Get client scopes belonging to the realm Returns a list of client scopes belonging to the realm

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get representation of the client scope [SAT] <a name="18383acc-d640-4000-8c69-3c10b104b400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{clientScopeId}}`

Get representation of the client scope

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Delete the client scope[SAT] <a name="18383acc-d650-4000-8da5-85d9e4fc7a00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{clientScopeId}}`

Delete the client scope

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update the client scope [SAT] <a name="18383acc-d650-4000-85c3-3ee81f0f8800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{clientScopeId}}`

Update the client scope

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "4f841085-b7be-4596-b99b-15422e16bf0b",
    "name": "email",
    "description": "OpenID Connect built-in scope: email +",
    "protocol": "openid-connect",
    "attributes": {
        "include.in.token.scope": "true",
        "display.on.consent.screen": "true",
        "consent.screen.text": "${emailScopeConsentText}"
    },
    "protocolMappers": [
        {
            "id": "62224d4c-7181-4790-a3c9-71cdbf1516a5",
            "name": "email",
            "protocol": "openid-connect",
            "protocolMapper": "oidc-usermodel-property-mapper",
            "consentRequired": false,
            "config": {
                "userinfo.token.claim": "true",
                "user.attribute": "email",
                "id.token.claim": "true",
                "access.token.claim": "true",
                "claim.name": "email",
                "jsonType.label": "String"
            }
        },
        {
            "id": "e7b52fef-f525-4314-abf3-267d9f48082e",
            "name": "email verified",
            "protocol": "openid-connect",
            "protocolMapper": "oidc-usermodel-property-mapper",
            "consentRequired": false,
            "config": {
                "userinfo.token.claim": "true",
                "user.attribute": "emailVerified",
                "id.token.claim": "true",
                "access.token.claim": "true",
                "claim.name": "email_verified",
                "jsonType.label": "boolean"
            }
        }
    ]
}
```


### POST Create a new client scope [SAT] <a name="18383acc-d650-4000-8121-21d28f3da200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes`

Create a new client scope Client Scopeâ€™s name must be unique!

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
    {
        "name": "test_scope",
        "description": "OpenID Connect built-in scope: offline_access",
        "protocol": "openid-connect",
        "attributes": {
            "consent.screen.text": "${offlineAccessScopeConsentText}",
            "display.on.consent.screen": "true"
        }
    }
```


## Clients <a name="18383acc-d660-4000-8c68-36911457b500"></a>



### GET Get clients [SAT] <a name="18383acc-d660-4000-82a2-af3fd77db700"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients`

Get clients belonging to the realm Returns a list of clients belonging to the realm

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get representation of the client [SAT] <a name="18383acc-d660-4000-8cb7-20e4fb7c5f00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}`

Get representation of the client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Generate a new secret for the client [SAT] <a name="18383acc-d660-4000-8b8c-408b3390b300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/client-secret`

Generate a new secret for the client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get secret for the client [SAT] <a name="18383acc-d660-4000-8f91-1db154fc8300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/client-secret`

Get the client secret

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get the client providers [SAT] <a name="18383acc-d670-4000-8d14-375212d0ca00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/installation/providers/keycloak-oidc`

Get the client providers

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Register a cluster node with the client  [SAT] <a name="18383acc-d670-4000-8649-2bc99800d600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/nodes`

Register a cluster node with the client Manually register cluster node to this client - usually itâ€™s not needed to call this directly as adapter should handle by sending registration request to Keycloak

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"formParams": []
}
```


### DELETE Register a cluster node with the client  [SAT] Copy <a name="18383acc-d680-4000-8816-c56697b8a400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/nodes/{{node}}`

Register a cluster node with the client Manually register cluster node to this client - usually itâ€™s not needed to call this directly as adapter should handle by sending registration request to Keycloak

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get client authorization permissions [SAT] <a name="18383acc-d680-4000-8a16-59a893605400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/management/permissions`

Has client authorization permissions initialized?


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update client authorization permissions [SAT] <a name="18383acc-d690-4000-8b2c-69b259e8fd00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/management/permissions`

Return object stating whether client Authorization permissions have been initialized or not and a reference

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"enabled": "false"
}
```


### DELETE Get representation of the client [SAT] Copy <a name="18383acc-d690-4000-81d4-b8a1dd104900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}`

Get representation of the client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Create a new client [SAT] <a name="18383acc-d690-4000-897d-9cc70a915100"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients`

Create a new client Clientâ€™s client_id must be unique!

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
    {
        "clientId": "new-client-from-rest-api",
        "name": "new-client-from-rest-api",
        "adminUrl": "http://localhost:4200",
        "alwaysDisplayInConsole": false,
        "access": {
            "view": true,
            "configure": true,
            "manage": true
        },
        "attributes": {},
        "authenticationFlowBindingOverrides" : {},
        "authorizationServicesEnabled": false,
        "bearerOnly": false,
        "directAccessGrantsEnabled": true,
        "enabled": true,
        "protocol": "openid-connect",
        "description": "rest-api",

        "rootUrl": "${authBaseUrl}",
        "baseUrl": "/realms/heroes/account/",
        "surrogateAuthRequired": false,
        "clientAuthenticatorType": "client-secret",
        "defaultRoles": [
            "manage-account",
            "view-profile"
        ],
        "redirectUris": [
            "/realms/heroes/account/*"
        ],
        "webOrigins": [],
        "notBefore": 0,
        "consentRequired": false,
        "standardFlowEnabled": true,
        "implicitFlowEnabled": false,
        "serviceAccountsEnabled": false,
        "publicClient": false,
        "frontchannelLogout": false,
        "fullScopeAllowed": false,
        "nodeReRegistrationTimeout": 0,
        "defaultClientScopes": [
            "web-origins",
            "role_list",
            "profile",
            "roles",
            "email"
        ],
        "optionalClientScopes": [
            "address",
            "phone",
            "offline_access",
            "microprofile-jwt"
        ]
    }
```


### PUT Create a new client [SAT] Copy <a name="18383acc-d6a0-4000-89e0-eb2293962500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}`

Create a new client Clientâ€™s client_id must be unique!

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "enabled": false
}
```


### GET Get default client scopes [SAT] <a name="18383acc-d6a0-4000-8049-1721a8c11100"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/default-client-scopes`

Get default client scopes from a client.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Create JSON with payload of example access token [SAT] <a name="18383acc-d6a0-4000-87ca-485cc7611600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/evaluate-scopes/generate-example-access-token?userId={{userId}}`

Create JSON with payload of example access token

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get effective scope mapping of all roles [SAT] <a name="18383acc-d6a0-4000-8b4b-16f990948900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/evaluate-scopes/scope-mappings/{{containerId}}/granted`

Get effective scope mapping of all roles of particular role container, which this client is defacto allowed to have in the accessToken issued for him.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get roles without scope and access token [SAT] <a name="18383acc-d6b0-4000-827c-753dfa5bb500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/evaluate-scopes/scope-mappings/{{containerId}}/not-granted`

Get roles, which this client doesnâ€™t have scope for and canâ€™t have them in the accessToken issued for him.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get all protocol mappers [SAT] <a name="18383acc-d6b0-4000-82bc-35b716a5d000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/evaluate-scopes/protocol-mappers`

Return list of all protocol mappers, which will be used when generating tokens issued for particular client.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get application offline session count [SAT] <a name="18383acc-d6b0-4000-8bb1-cff6e31e3900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/offline-session-count`

Get application offline session count Returns a number of offline user sessions associated with this client { "count": number }

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get application offline sessions [SAT] <a name="18383acc-d6b0-4000-822d-e7b64032e700"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/offline-sessions`

Get offline sessions for client Returns a list of offline user sessions associated with this client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get optional client scopes[SAT] <a name="18383acc-d6c0-4000-85b6-6198549a2c00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/optional-client-scopes`

Get optional client scopes.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Add optional client scope to client [SAT] <a name="18383acc-d6c0-4000-8add-191a8d39f000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/optional-client-scopes/{{clientScopeId}}`

Add optional client scope to client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Delete optional client scope to client [SAT] <a name="18383acc-d6c0-4000-892a-c48c83777200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/optional-client-scopes/{{clientScopeId}}`

Delete optional client scope to client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Add default client scope to client [SAT] <a name="18383acc-d6c0-4000-8901-f855ec487400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/default-client-scopes/{{clientScopeId}}`

Add default client scope to client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Delete default client scope to client [SAT] <a name="18383acc-d6d0-4000-8583-e7eb51b64b00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/default-client-scopes/{{clientScopeId}}`

Delete default client scope to client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Push the clientâ€™s revocation policy to its admin URL [SAT] <a name="18383acc-d6d0-4000-88b3-e1a863f0ad00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/push-revocation`

Push the clientâ€™s revocation policy to its admin URL If the client has an admin URL, push revocation policy to it.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Generate a new registration access token for the client [SAT] <a name="18383acc-d6d0-4000-814a-59d8f4b20300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/registration-access-token`

Generate a new registration access token for the client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get a user dedicated to the service account [SAT] <a name="18383acc-d6d0-4000-8aa5-51e6b9dad500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientIdServiceAccount}}/service-account-user`

Get a user dedicated to the service account

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get application session count associated with this client [SAT] <a name="18383acc-d6e0-4000-89ca-c9444b891e00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientIdServiceAccount}}/session-count`

Get application session count Returns a number of user sessions associated with this client { "count": number }

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Test if registered cluster nodes are available [SAT] <a name="18383acc-d6e0-4000-87c5-dc09548a3c00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientIdServiceAccount}}/test-nodes-available`

Test if registered cluster nodes are available Tests availability by sending 'ping' request to all cluster nodes

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get user sessions associated with this client [SAT] <a name="18383acc-d6e0-4000-8f5b-1a82a8119300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientIdServiceAccount}}/user-sessions`

Get user sessions for client Returns a list of user sessions associated with this client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

## General information <a name="18383acc-d6e0-4000-819d-d9920636aa00"></a>



### GET Get certs information <a name="18383acc-d6e0-4000-851f-2437b3c08800"></a>


`{{keycloak_url}}/realms/{{realm}}/protocol/openid-connect/certs`


**Request Headers**

N/A

**Request Body**

N/A

### GET Well known configuration <a name="18383acc-d6f0-4000-8c2c-49115d6de900"></a>


`{{keycloak_url}}/realms/{{realm}}/.well-known/openid-configuration`

Get configuration information

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/x-www-form-urlencoded|



**Request Body**

N/A

### GET User Info <a name="18383acc-d6f0-4000-8446-293aea810d00"></a>


`{{keycloak_url}}/realms/{{realm}}/protocol/openid-connect/userinfo`

Get configuration information

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/x-www-form-urlencoded|



**Request Body**

N/A

## Component <a name="18383acc-d6f0-4000-8fb6-74afb8216000"></a>



### POST Add components [SAT] <a name="18383acc-d6f0-4000-8f68-c96931220f00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/components`

Add components

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"name": "test",
    "providerId": "max-clients",
    "providerType": "org.keycloak.services.clientregistration.policy.ClientRegistrationPolicy",
    "parentId": "heroes",
    "subType": "anonymous",
    "config": {
        "max-clients": [
            "200"
        ]
    }
}
```


### GET Get components [SAT] <a name="18383acc-d700-4000-8930-ebb3dcac3300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/components`

Get components

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get a specific component [SAT] <a name="18383acc-d700-4000-8e2d-2eb0ea1e8800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/components/{{componentId}}`

Get component from id

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get subcomponents [SAT] <a name="18383acc-d700-4000-8e2e-f192666e3800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/components/{{componentId}}/sub-component-types?type=org.keycloak.keys.KeyProvider`

List of subcomponent types that are available to configure for a particular parent component.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update a specific component [SAT] <a name="18383acc-d700-4000-886b-c170d03ca000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/components/{{componentId}}`

Update a component from id

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "7a084caa-36f4-4ea4-8dcb-56b1b189c2fa",
    "name": "Trusted Hosts",
    "providerId": "trusted-hosts",
    "providerType": "org.keycloak.services.clientregistration.policy.ClientRegistrationPolicy",
    "parentId": "heroes",
    "subType": "anonymous",
    "config": {
        "host-sending-registration-request-must-match": [
            "true"
        ],
        "client-uris-must-match": [
            "true"
        ]
    }
}
```


### DELETE Update a specific component [SAT] Copy <a name="18383acc-d710-4000-80fa-b22d7f03de00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/components/{{componentId}}`

Update a component from id

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

## Groups <a name="18383acc-d710-4000-8a29-b7a571816000"></a>



### GET Get groups [SAT] <a name="18383acc-d710-4000-8e1d-63899cc6d500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups`

Get groups

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get specific group [SAT] <a name="18383acc-d710-4000-8b6c-c0deb02dd700"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}`

Get group for a specific id

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get groups count [SAT] <a name="18383acc-d710-4000-8a78-3b3e1335a600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/count`

Get groups count

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Create a group [SAT] <a name="18383acc-d720-4000-8e41-5e8f0826f000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups`

create or add a top level realm groupSet or create child

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"name": "anime",
	"path": "/anime",
	"subGroups": []
}
```


### PUT Update group [SAT] <a name="18383acc-d720-4000-890d-0deab34d0500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}`

Update group, ignores subgroups.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
        "id": "67722639-5e88-4635-b641-522c2461fef3",
        "name": "marvel",
        "path": "/marVel",
        "subGroups": []
    }
```


### DELETE Delete group [SAT] <a name="18383acc-d720-4000-8e5c-2cf220f86700"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/91f732ae-509f-4520-a246-abe570f9b52d`

Delete group

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Add  subgroup [SAT] <a name="18383acc-d720-4000-8baf-d179fde79400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}/children`

Add subgroup

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"name": "movies",
	"path": "/movies",
	"subGroups": []
}
```


### GET Return object authorization permissions [SAT] <a name="18383acc-d730-4000-8fee-aa943aabc900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}/management/permissions`

Return object stating whether client Authorization permissions have been initialized or not and a reference

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"name": "movies",
	"path": "/movies",
	"subGroups": []
}
```


### GET Get group members [SAT] <a name="18383acc-d730-4000-8d0f-19129cc1b800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}/members`

Get users Returns a list of users, filtered according to query parameters

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"name": "movies",
	"path": "/movies",
	"subGroups": []
}
```


### PUT Update return object authorization permissions [SAT] <a name="18383acc-d730-4000-82bb-5da0b5deab00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}/management/permissions`

Return object stating whether client Authorization permissions have been initialized or not and a reference

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"enabled": "false"
}
```


## Identity Providers <a name="18383acc-d740-4000-81e9-417cba042800"></a>



### POST Import identity provider from uploaded JSON file [SAT] <a name="18383acc-d740-4000-8188-9145b5186100"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/import-config`

Import identity provider from uploaded JSON file

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|multipart/form-data|



**Request Body** `file`

Does not support display!

### POST Create a new identity provider [SAT] <a name="18383acc-d740-4000-8236-ae64aefcda00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/instances`

Create a new identity provider

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
        "alias": "keycloak-oidc-2",
        "providerId": "keycloak-oidc",
        "enabled": true,
        "updateProfileFirstLoginMode": "on",
        "trustEmail": false,
        "storeToken": false,
        "addReadTokenRoleOnCreate": false,
        "authenticateByDefault": false,
        "linkOnly": false,
        "firstBrokerLoginFlowAlias": "first broker login",
        "config": {}
    }
```


### GET Get identity providers [SAT] <a name="18383acc-d740-4000-8564-b2cdb5186600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/instances`

Get identity providers

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|multipart/form-data|



**Request Body**

N/A

### GET Get the identity provider from alias [SAT] <a name="18383acc-d740-4000-8d8d-0b55be28a900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/instances/{{providerAlias}}`

Get the identity provider from alias

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|multipart/form-data|



**Request Body**

N/A

### GET Return object stating client Authorization [SAT] <a name="18383acc-d750-4000-8f5e-030f6f7dc100"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/instances/{{providerAlias}}/management/permissions`

Return object stating whether client Authorization permissions have been initialized or not and a reference

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|multipart/form-data|



**Request Body**

N/A

### PUT Return object stating client Authorization [SAT]  Copy <a name="18383acc-d750-4000-8038-2bc5d645ea00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/instances/{{providerAlias}}/management/permissions`

Return object stating whether client Authorization permissions have been initialized or not and a reference

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"enabled": true
}
```


### GET Export public broker configuration for identity provider [SAT] <a name="18383acc-d750-4000-813c-347cb4360a00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/instances/{{providerAlias}}/export?format=json`

Export public broker configuration for identity provider

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|multipart/form-data|



**Request Body**

N/A

### PUT Update the identity provider [SAT] <a name="18383acc-d750-4000-8722-1a8c4c0b6e00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/instances/{{providerAlias}}`

Update the identity provider

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "alias": "keycloak-oidc-2",
    "internalId": "0df24d90-d39e-4e02-ab3d-7150efa40b1d",
    "providerId": "keycloak-oidc",
    "enabled": true,
    "updateProfileFirstLoginMode": "on",
    "trustEmail": true,
    "storeToken": false,
    "addReadTokenRoleOnCreate": false,
    "authenticateByDefault": false,
    "linkOnly": false,
    "firstBrokerLoginFlowAlias": "first broker login",
    "config": {}
}
```


### DELETE Delete the identity provider [SAT] <a name="18383acc-d760-4000-8c3c-7f9444a4d400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/instances/{{providerAlias}}`

Delete the identity provider

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get mapper types for identity provider [SAT] <a name="18383acc-d760-4000-8038-99b64df24400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/instances/{{providerAlias}}/mapper-types`

Get mapper types for identity provider

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/octet-stream|



**Request Body**

N/A

### POST Add a mapper to identity provider [SAT] <a name="18383acc-d760-4000-8dbb-e0437e00c600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/instances/{{providerAlias}}/mappers`

Add a mapper to identity provider

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"name": "test-mapper",
	"identityProviderAlias": "keycloak-oidc2",
	"identityProviderMapper": "keycloak-oidc",
	"config": {}
}
```


### GET Get mappes for the identity provider [SAT] <a name="18383acc-d770-4000-8eae-4f865a616300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/instances/{{providerAlias}}/mappers`

Get mappes for the identity provider 

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get mapper by id for the identity provider  [SAT] <a name="18383acc-d770-4000-8f1e-247817146800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/instances/{{providerAlias}}/mappers/ea65c956-24c7-4587-8fe7-c07222e3485d`

Get mapper by id for the identity provider

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get identity providers  [SAT] <a name="18383acc-d770-4000-81f8-ec40910eca00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/providers/keycloak-oidc`

Get identity providers

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update a mapper for the identity provider  [SAT] <a name="18383acc-d770-4000-8460-41750d1c7d00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/instances/{{providerAlias}}/mappers/ea65c956-24c7-4587-8fe7-c07222e3485d`

Update a mapper for the identity provider

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "ea65c956-24c7-4587-8fe7-c07222e3485d",
    "name": "test",
    "identityProviderAlias": "keycloak-oidc-2",
    "identityProviderMapper": "hardcoded-user-session-attribute-idp-mapper",
    "config": {
        "syncMode": "INHERIT"
    }
}
```


### DELETE Delete a mapper for the identity provider  [SAT] <a name="18383acc-d780-4000-8900-2cb931068300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/identity-provider/instances/{{providerAlias}}/mappers/ea65c956-24c7-4587-8fe7-c07222e3485d`

Delete a mapper for the identity provider

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

## Key <a name="18383acc-d780-4000-8f5a-40047456f400"></a>



### GET Get realm keys  [SAT] <a name="18383acc-d780-4000-86a1-9b41f7e9a400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/keys`

Get realm keys 

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

## Protocol Mappers <a name="18383acc-d780-4000-8db1-010895bd6200"></a>



### POST Create mappers to identity provider [SAT] <a name="18383acc-d780-4000-8306-a5102c75a400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{clientScopeId}}/protocol-mappers/add-models`

Create mappers to identity provider 

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
[{
	"name": "protocol-mapper-2",
	"protocol": "openid-connect",
	"protocolMapper": "oidc-usermodel-property-mapper",
	"config": {}
}]
```


### POST Create a mapper to identity provider [SAT] <a name="18383acc-d790-4000-8ac7-9368e0605600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{clientScopeId}}/protocol-mappers/models`

Add a mapper to identity provider

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"name": "protocol-mapper",
	"protocol": "openid-connect",
	"protocolMapper": "oidc-usermodel-property-mapper",
	"config": {}
}
```


### PUT Update the mapper[SAT] <a name="18383acc-d790-4000-8238-f0b7f3845a00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{clientScopeId}}/protocol-mappers/models/62224d4c-7181-4790-a3c9-71cdbf1516a5`

Update the mapper

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
        "id": "62224d4c-7181-4790-a3c9-71cdbf1516a5",
        "name": "email",
        "protocol": "openid-connect",
        "protocolMapper": "oidc-usermodel-property-mapper",
        "consentRequired": false,
        "config": {
            "userinfo.token.claim": "true",
            "user.attribute": "email",
            "id.token.claim": "true",
            "access.token.claim": "true",
            "claim.name": "email",
            "jsonType.label": "String"
        }
}
```


### DELETE Update the mapper[SAT]  Copy <a name="18383acc-d790-4000-8579-13bb0ce83600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{clientScopeId}}/protocol-mappers/models/62224d4c-7181-4790-a3c9-71cdbf1516a5`

Update the mapper

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get mappers [SAT] <a name="18383acc-d790-4000-8b6c-bbb85ab62a00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{clientScopeId}}/protocol-mappers/models`

Get mappers

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get mappers by name for a specific protocol [SAT] <a name="18383acc-d7a0-4000-8c77-41a4c5dd5f00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{clientScopeId}}/protocol-mappers/protocol/62224d4c-7181-4790-a3c9-71cdbf1516a5`

Get mappers by name for a specific protocol

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get exact mapper [SAT] <a name="18383acc-d7a0-4000-86ec-a883eea22300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{clientScopeId}}/protocol-mappers/models/62224d4c-7181-4790-a3c9-71cdbf1516a5`

Get specific mapper

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Create multiple mappers for a client [SAT] <a name="18383acc-d7a0-4000-84dd-d41c8c70ef00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/protocol-mappers/add-models`

Create multiple mappers

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
[{
	"name": "protocol-mapper-2",
	"protocol": "openid-connect",
	"protocolMapper": "oidc-usermodel-property-mapper",
	"config": {}
}]
```


### POST Create a mapper for a client [SAT] <a name="18383acc-d7a0-4000-8edd-ffd9d904be00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/protocol-mappers/models`

Create a mapper for a client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"name": "protocol-mapper-2",
	"protocol": "openid-connect",
	"protocolMapper": "oidc-usermodel-property-mapper",
	"config": {}
}
```


### GET Get mappers for a client [SAT] <a name="18383acc-d7b0-4000-8e26-2aa84c08dd00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/protocol-mappers/models`

Get mappers for a client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get mapper for a specific client [SAT] <a name="18383acc-d7b0-4000-8b81-b196f4c93200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/protocol-mappers/models/af0bf361-7882-4d10-a38c-40ffddba9a59`

Get mapper for a specific client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get mappers by name for a specific protocol [SAT] <a name="18383acc-d7b0-4000-8254-64cfe7fa4000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/protocol-mappers/protocol/openid-connect`

Get mappers by name for a specific protocol

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update the mapper [SAT] <a name="18383acc-d7c0-4000-8dfa-1c485f9bf600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/protocol-mappers/models/af0bf361-7882-4d10-a38c-40ffddba9a59`

Update the mapper

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "af0bf361-7882-4d10-a38c-40ffddba9a59",
    "name": "protocol-mapper-2",
    "protocol": "openid-connect",
    "protocolMapper": "oidc-usermodel-property-mapper",
    "consentRequired": false,
    "config": {}
}
```


### DELETE Update the mapper [SAT]  Copy <a name="18383acc-d7c0-4000-805f-acffe3a75800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/protocol-mappers/models/af0bf361-7882-4d10-a38c-40ffddba9a59`

Update the mapper

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

## Realms Admin <a name="18383acc-d7c0-4000-856a-98f19e5d2900"></a>



### GET Get realm info [SAT] <a name="18383acc-d7c0-4000-8b0a-21dc7e2e9300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}`

Get realm info

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get admin events of the realm [SAT] <a name="18383acc-d7d0-4000-8d31-6826a3ac7300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/admin-events`

Get admin events Returns all admin events, or filters events based on URL query parameters listed here

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Delete all admin events [SAT] <a name="18383acc-d7d0-4000-88d0-4b9dd602f300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/admin-events`

Delete all admin events

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Add realm [SAT] <a name="18383acc-d7d0-4000-82e9-a50e11088f00"></a>


`{{keycloak_url}}/admin/realms`

Add realm

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "heroes",
    "realm": "heroes",
    "notBefore": 0,
    "revokeRefreshToken": false,
    "refreshTokenMaxReuse": 0,
    "accessTokenLifespan": 300,
    "accessTokenLifespanForImplicitFlow": 900,
    "ssoSessionIdleTimeout": 1800,
    "ssoSessionMaxLifespan": 36000,
    "ssoSessionIdleTimeoutRememberMe": 0,
    "ssoSessionMaxLifespanRememberMe": 0,
    "offlineSessionIdleTimeout": 2592000,
    "offlineSessionMaxLifespanEnabled": false,
    "offlineSessionMaxLifespan": 5184000,
    "clientSessionIdleTimeout": 0,
    "clientSessionMaxLifespan": 0,
    "accessCodeLifespan": 60,
    "accessCodeLifespanUserAction": 300,
    "accessCodeLifespanLogin": 1800,
    "actionTokenGeneratedByAdminLifespan": 43200,
    "actionTokenGeneratedByUserLifespan": 300,
    "enabled": true,
    "sslRequired": "external",
    "registrationAllowed": false,
    "registrationEmailAsUsername": false,
    "rememberMe": false,
    "verifyEmail": false,
    "loginWithEmailAllowed": true,
    "duplicateEmailsAllowed": false,
    "resetPasswordAllowed": false,
    "editUsernameAllowed": false,
    "bruteForceProtected": false,
    "permanentLockout": false,
    "maxFailureWaitSeconds": 900,
    "minimumQuickLoginWaitSeconds": 60,
    "waitIncrementSeconds": 60,
    "quickLoginCheckMilliSeconds": 1000,
    "maxDeltaTimeSeconds": 43200,
    "failureFactor": 30,
    "defaultRoles": [
        "offline_access",
        "uma_authorization"
    ],
    "requiredCredentials": [
        "password"
    ],
    "otpPolicyType": "totp",
    "otpPolicyAlgorithm": "HmacSHA1",
    "otpPolicyInitialCounter": 0,
    "otpPolicyDigits": 6,
    "otpPolicyLookAheadWindow": 1,
    "otpPolicyPeriod": 30,
    "otpSupportedApplications": [
        "FreeOTP",
        "Google Authenticator"
    ],
    "webAuthnPolicyRpEntityName": "keycloak",
    "webAuthnPolicySignatureAlgorithms": [
        "ES256"
    ],
    "webAuthnPolicyRpId": "",
    "webAuthnPolicyAttestationConveyancePreference": "not specified",
    "webAuthnPolicyAuthenticatorAttachment": "not specified",
    "webAuthnPolicyRequireResidentKey": "not specified",
    "webAuthnPolicyUserVerificationRequirement": "not specified",
    "webAuthnPolicyCreateTimeout": 0,
    "webAuthnPolicyAvoidSameAuthenticatorRegister": false,
    "webAuthnPolicyAcceptableAaguids": [],
    "webAuthnPolicyPasswordlessRpEntityName": "keycloak",
    "webAuthnPolicyPasswordlessSignatureAlgorithms": [
        "ES256"
    ],
    "webAuthnPolicyPasswordlessRpId": "",
    "webAuthnPolicyPasswordlessAttestationConveyancePreference": "not specified",
    "webAuthnPolicyPasswordlessAuthenticatorAttachment": "not specified",
    "webAuthnPolicyPasswordlessRequireResidentKey": "not specified",
    "webAuthnPolicyPasswordlessUserVerificationRequirement": "not specified",
    "webAuthnPolicyPasswordlessCreateTimeout": 0,
    "webAuthnPolicyPasswordlessAvoidSameAuthenticatorRegister": false,
    "webAuthnPolicyPasswordlessAcceptableAaguids": [],
    "browserSecurityHeaders": {
        "contentSecurityPolicyReportOnly": "",
        "xContentTypeOptions": "nosniff",
        "xRobotsTag": "none",
        "xFrameOptions": "SAMEORIGIN",
        "contentSecurityPolicy": "frame-src 'self'; frame-ancestors 'self'; object-src 'none';",
        "xXSSProtection": "1; mode=block",
        "strictTransportSecurity": "max-age=31536000; includeSubDomains"
    },
    "smtpServer": {},
    "eventsEnabled": false,
    "eventsListeners": [
        "jboss-logging"
    ],
    "enabledEventTypes": [],
    "adminEventsEnabled": false,
    "adminEventsDetailsEnabled": false,
    "identityProviders": [
        {
            "alias": "keycloak-oidc",
            "internalId": "d79d0d65-8ee1-47f0-8611-f9e6eea71f20",
            "providerId": "keycloak-oidc",
            "enabled": true,
            "updateProfileFirstLoginMode": "on",
            "trustEmail": false,
            "storeToken": false,
            "addReadTokenRoleOnCreate": false,
            "authenticateByDefault": false,
            "linkOnly": false,
            "firstBrokerLoginFlowAlias": "first broker login",
            "config": {
                "clientId": "ssss",
                "tokenUrl": "http://localhost",
                "authorizationUrl": "http://localhost",
                "clientAuthMethod": "client_secret_basic",
                "syncMode": "IMPORT",
                "clientSecret": "assaasa",
                "useJwksUrl": "true"
            }
        },
        {
            "alias": "keycloak-oidc-2",
            "internalId": "7cf3fd74-8d3a-4c8d-b651-fcc885df8a31",
            "providerId": "keycloak-oidc",
            "enabled": true,
            "updateProfileFirstLoginMode": "on",
            "trustEmail": false,
            "storeToken": false,
            "addReadTokenRoleOnCreate": false,
            "authenticateByDefault": false,
            "linkOnly": false,
            "firstBrokerLoginFlowAlias": "first broker login",
            "config": {}
        }
    ],
    "identityProviderMappers": [
        {
            "id": "42c7b62d-4383-42c9-a8a0-65519e2c2543",
            "name": "test-mapper",
            "identityProviderAlias": "keycloak-oidc2",
            "identityProviderMapper": "keycloak-oidc",
            "config": {}
        },
        {
            "id": "ea65c956-24c7-4587-8fe7-c07222e3485d",
            "name": "test",
            "identityProviderAlias": "keycloak-oidc-2",
            "identityProviderMapper": "hardcoded-user-session-attribute-idp-mapper",
            "config": {
                "syncMode": "INHERIT"
            }
        }
    ],
    "internationalizationEnabled": false,
    "supportedLocales": [],
    "browserFlow": "browser",
    "registrationFlow": "registration",
    "directGrantFlow": "direct grant",
    "resetCredentialsFlow": "reset credentials",
    "clientAuthenticationFlow": "clients",
    "dockerAuthenticationFlow": "docker auth",
    "attributes": {},
    "userManagedAccessAllowed": false
}
```


### PUT Update realm [SAT] <a name="18383acc-d7d0-4000-8319-69f24104fb00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}`

Update realm

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "heroes",
    "realm": "heroes",
    "notBefore": 0,
    "revokeRefreshToken": false,
    "refreshTokenMaxReuse": 0,
    "accessTokenLifespan": 300,
    "accessTokenLifespanForImplicitFlow": 900,
    "ssoSessionIdleTimeout": 1800,
    "ssoSessionMaxLifespan": 36000,
    "ssoSessionIdleTimeoutRememberMe": 0,
    "ssoSessionMaxLifespanRememberMe": 0,
    "offlineSessionIdleTimeout": 2592000,
    "offlineSessionMaxLifespanEnabled": false,
    "offlineSessionMaxLifespan": 5184000,
    "clientSessionIdleTimeout": 0,
    "clientSessionMaxLifespan": 0,
    "accessCodeLifespan": 60,
    "accessCodeLifespanUserAction": 300,
    "accessCodeLifespanLogin": 1800,
    "actionTokenGeneratedByAdminLifespan": 43200,
    "actionTokenGeneratedByUserLifespan": 300,
    "enabled": true,
    "sslRequired": "external",
    "registrationAllowed": false,
    "registrationEmailAsUsername": false,
    "rememberMe": false,
    "verifyEmail": false,
    "loginWithEmailAllowed": true,
    "duplicateEmailsAllowed": false,
    "resetPasswordAllowed": false,
    "editUsernameAllowed": false,
    "bruteForceProtected": false,
    "permanentLockout": false,
    "maxFailureWaitSeconds": 900,
    "minimumQuickLoginWaitSeconds": 60,
    "waitIncrementSeconds": 60,
    "quickLoginCheckMilliSeconds": 1000,
    "maxDeltaTimeSeconds": 43200,
    "failureFactor": 30,
    "defaultRoles": [
        "offline_access",
        "uma_authorization"
    ],
    "requiredCredentials": [
        "password"
    ],
    "otpPolicyType": "totp",
    "otpPolicyAlgorithm": "HmacSHA1",
    "otpPolicyInitialCounter": 0,
    "otpPolicyDigits": 6,
    "otpPolicyLookAheadWindow": 1,
    "otpPolicyPeriod": 30,
    "otpSupportedApplications": [
        "FreeOTP",
        "Google Authenticator"
    ],
    "webAuthnPolicyRpEntityName": "keycloak",
    "webAuthnPolicySignatureAlgorithms": [
        "ES256"
    ],
    "webAuthnPolicyRpId": "",
    "webAuthnPolicyAttestationConveyancePreference": "not specified",
    "webAuthnPolicyAuthenticatorAttachment": "not specified",
    "webAuthnPolicyRequireResidentKey": "not specified",
    "webAuthnPolicyUserVerificationRequirement": "not specified",
    "webAuthnPolicyCreateTimeout": 0,
    "webAuthnPolicyAvoidSameAuthenticatorRegister": false,
    "webAuthnPolicyAcceptableAaguids": [],
    "webAuthnPolicyPasswordlessRpEntityName": "keycloak",
    "webAuthnPolicyPasswordlessSignatureAlgorithms": [
        "ES256"
    ],
    "webAuthnPolicyPasswordlessRpId": "",
    "webAuthnPolicyPasswordlessAttestationConveyancePreference": "not specified",
    "webAuthnPolicyPasswordlessAuthenticatorAttachment": "not specified",
    "webAuthnPolicyPasswordlessRequireResidentKey": "not specified",
    "webAuthnPolicyPasswordlessUserVerificationRequirement": "not specified",
    "webAuthnPolicyPasswordlessCreateTimeout": 0,
    "webAuthnPolicyPasswordlessAvoidSameAuthenticatorRegister": false,
    "webAuthnPolicyPasswordlessAcceptableAaguids": [],
    "browserSecurityHeaders": {
        "contentSecurityPolicyReportOnly": "",
        "xContentTypeOptions": "nosniff",
        "xRobotsTag": "none",
        "xFrameOptions": "SAMEORIGIN",
        "contentSecurityPolicy": "frame-src 'self'; frame-ancestors 'self'; object-src 'none';",
        "xXSSProtection": "1; mode=block",
        "strictTransportSecurity": "max-age=31536000; includeSubDomains"
    },
    "smtpServer": {},
    "eventsEnabled": false,
    "eventsListeners": [
        "jboss-logging"
    ],
    "enabledEventTypes": [],
    "adminEventsEnabled": false,
    "adminEventsDetailsEnabled": false,
    "identityProviders": [
        {
            "alias": "keycloak-oidc",
            "internalId": "d79d0d65-8ee1-47f0-8611-f9e6eea71f20",
            "providerId": "keycloak-oidc",
            "enabled": true,
            "updateProfileFirstLoginMode": "on",
            "trustEmail": false,
            "storeToken": false,
            "addReadTokenRoleOnCreate": false,
            "authenticateByDefault": false,
            "linkOnly": false,
            "firstBrokerLoginFlowAlias": "first broker login",
            "config": {
                "clientId": "ssss",
                "tokenUrl": "http://localhost",
                "authorizationUrl": "http://localhost",
                "clientAuthMethod": "client_secret_basic",
                "syncMode": "IMPORT",
                "clientSecret": "assaasa",
                "useJwksUrl": "true"
            }
        },
        {
            "alias": "keycloak-oidc-2",
            "internalId": "7cf3fd74-8d3a-4c8d-b651-fcc885df8a31",
            "providerId": "keycloak-oidc",
            "enabled": true,
            "updateProfileFirstLoginMode": "on",
            "trustEmail": false,
            "storeToken": false,
            "addReadTokenRoleOnCreate": false,
            "authenticateByDefault": false,
            "linkOnly": false,
            "firstBrokerLoginFlowAlias": "first broker login",
            "config": {}
        }
    ],
    "identityProviderMappers": [
        {
            "id": "42c7b62d-4383-42c9-a8a0-65519e2c2543",
            "name": "test-mapper",
            "identityProviderAlias": "keycloak-oidc2",
            "identityProviderMapper": "keycloak-oidc",
            "config": {}
        },
        {
            "id": "ea65c956-24c7-4587-8fe7-c07222e3485d",
            "name": "test",
            "identityProviderAlias": "keycloak-oidc-2",
            "identityProviderMapper": "hardcoded-user-session-attribute-idp-mapper",
            "config": {
                "syncMode": "INHERIT"
            }
        }
    ],
    "internationalizationEnabled": false,
    "supportedLocales": [],
    "browserFlow": "browser",
    "registrationFlow": "registration",
    "directGrantFlow": "direct grant",
    "resetCredentialsFlow": "reset credentials",
    "clientAuthenticationFlow": "clients",
    "dockerAuthenticationFlow": "docker auth",
    "attributes": {},
    "userManagedAccessAllowed": false
}
```


### DELETE Delete realm [SAT] <a name="18383acc-d7e0-4000-8fa2-a23ca4dc7000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}`

Delete realm

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Clear keys cache [SAT] <a name="18383acc-d7e0-4000-88bd-c5a80c107100"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clear-keys-cache`

Clear cache of external public keys (Public keys of clients or Identity providers)

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Clear realm cache [SAT] <a name="18383acc-d7e0-4000-87ea-d0e1eb69f100"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clear-realm-cache`

Clear realm cache

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Clear user cache [SAT] <a name="18383acc-d7f0-4000-8208-ccdabfbc7200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clear-user-cache`

Clear user cache


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Base path for importing clients under this realm[SAT] <a name="18383acc-d7f0-4000-86ef-b3261b5bd900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-description-converter`

Base path for importing clients under this realm.


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{ 
	"description": "some description"
}

```


### GET Get client session stats Returns a JSON map [SAT] <a name="18383acc-d7f0-4000-8f1b-4797f8743200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-session-stats`

The key is the client id, the value is the number of sessions that currently are active with that client. Only clients that actually have a session associated with them will be in this map.




**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{ 
	"description": "some description"
}

```


### GET Get credential registrators [SAT] <a name="18383acc-d7f0-4000-85d3-6d584f3a2000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/credential-registrators`

Get credential registrators 


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{ 
	"description": "some description"
}

```


### GET Get realm default client scopes [SAT] <a name="18383acc-d800-4000-840b-57bd86f02e00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/default-default-client-scopes`

Only name and ids are returned.




**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{ 
	"description": "some description"
}

```


### PUT Update a realm default client scope [SAT] <a name="18383acc-d800-4000-8708-03cda0738a00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/default-default-client-scopes/{{clientScopeId}}`

Update a realm default client scope

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Delete a realm default client scope[SAT] <a name="18383acc-d800-4000-8723-6c4840737000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/default-default-client-scopes/{{clientScopeId}}`

Delete a realm default client scope



**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get group hierarchy [SAT] <a name="18383acc-d800-4000-813e-b6022bb32700"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/default-groups`

Get group hierarchy.




**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update group hierarchy [SAT] <a name="18383acc-d810-4000-889f-a69d04ffb300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/default-groups/{{groupId}}`

Update group hierarchy.




**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Delete group hierarchy [SAT] <a name="18383acc-d810-4000-83dc-2db4fa73f200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/default-groups/{{groupId}}`

Delete group hierarchy.




**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get realm optional client scopes [SAT] <a name="18383acc-d810-4000-8de9-432d559b4b00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/default-optional-client-scopes`

Get realm optional client scopes




**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update realm optional client scopes [SAT] <a name="18383acc-d810-4000-8e8e-51a176704200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/default-optional-client-scopes/{{realmClientScopeId}}`

Update realm optional client scopes




**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Delete realm optional client scopes [SAT] <a name="18383acc-d820-4000-840e-838ed3216500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/default-optional-client-scopes/{{realmClientScopeId}}`

Delete realm optional client scopes




**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get events [SAT] <a name="18383acc-d820-4000-8545-743f8b46a200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/events`

Get events Returns all events, or filters them based on URL query parameters listed here





**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Delete events [SAT] <a name="18383acc-d820-4000-8315-9b8113953a00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/events`

Delete all events





**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get events config [SAT] <a name="18383acc-d820-4000-8426-2cc71f48dd00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/events/config`

Get the events provider configuration Returns JSON object with events provider configuration






**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update events config [SAT] <a name="18383acc-d830-4000-8622-ec0222b1b900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/events/config`

Update the events provider Change the events provider and/or its configuration





**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "eventsEnabled": false,
    "eventsListeners": [
        "jboss-logging"
    ],
    "enabledEventTypes": [
        "LOGIN",
        "LOGIN_ERROR",
        "REGISTER",
        "REGISTER_ERROR",
        "LOGOUT",
        "LOGOUT_ERROR",
        "CODE_TO_TOKEN",
        "CODE_TO_TOKEN_ERROR",
        "CLIENT_LOGIN",
        "CLIENT_LOGIN_ERROR",
        "FEDERATED_IDENTITY_LINK",
        "FEDERATED_IDENTITY_LINK_ERROR",
        "REMOVE_FEDERATED_IDENTITY",
        "REMOVE_FEDERATED_IDENTITY_ERROR",
        "UPDATE_EMAIL",
        "UPDATE_EMAIL_ERROR",
        "UPDATE_PROFILE",
        "UPDATE_PROFILE_ERROR",
        "UPDATE_PASSWORD",
        "UPDATE_PASSWORD_ERROR",
        "UPDATE_TOTP",
        "UPDATE_TOTP_ERROR",
        "VERIFY_EMAIL",
        "VERIFY_EMAIL_ERROR",
        "REMOVE_TOTP",
        "REMOVE_TOTP_ERROR",
        "GRANT_CONSENT",
        "GRANT_CONSENT_ERROR",
        "UPDATE_CONSENT",
        "UPDATE_CONSENT_ERROR",
        "REVOKE_GRANT",
        "REVOKE_GRANT_ERROR",
        "SEND_VERIFY_EMAIL",
        "SEND_VERIFY_EMAIL_ERROR",
        "SEND_RESET_PASSWORD",
        "SEND_RESET_PASSWORD_ERROR",
        "SEND_IDENTITY_PROVIDER_LINK",
        "SEND_IDENTITY_PROVIDER_LINK_ERROR",
        "RESET_PASSWORD",
        "RESET_PASSWORD_ERROR",
        "RESTART_AUTHENTICATION",
        "RESTART_AUTHENTICATION_ERROR",
        "IDENTITY_PROVIDER_LINK_ACCOUNT",
        "IDENTITY_PROVIDER_LINK_ACCOUNT_ERROR",
        "IDENTITY_PROVIDER_FIRST_LOGIN",
        "IDENTITY_PROVIDER_FIRST_LOGIN_ERROR",
        "IDENTITY_PROVIDER_POST_LOGIN",
        "IDENTITY_PROVIDER_POST_LOGIN_ERROR",
        "IMPERSONATE",
        "IMPERSONATE_ERROR",
        "CUSTOM_REQUIRED_ACTION",
        "CUSTOM_REQUIRED_ACTION_ERROR",
        "EXECUTE_ACTIONS",
        "EXECUTE_ACTIONS_ERROR",
        "EXECUTE_ACTION_TOKEN",
        "EXECUTE_ACTION_TOKEN_ERROR",
        "CLIENT_REGISTER",
        "CLIENT_REGISTER_ERROR",
        "CLIENT_UPDATE",
        "CLIENT_UPDATE_ERROR",
        "CLIENT_DELETE",
        "CLIENT_DELETE_ERROR",
        "CLIENT_INITIATED_ACCOUNT_LINKING",
        "CLIENT_INITIATED_ACCOUNT_LINKING_ERROR",
        "TOKEN_EXCHANGE",
        "TOKEN_EXCHANGE_ERROR",
        "PERMISSION_TOKEN"
    ],
    "adminEventsEnabled": false,
    "adminEventsDetailsEnabled": false
}
```


### GET Get group from path [SAT] <a name="18383acc-d830-4000-82e4-e941c0510e00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/group-by-path/dc`

Get group from path 





**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "eventsEnabled": false,
    "eventsListeners": [
        "jboss-logging"
    ],
    "enabledEventTypes": [
        "LOGIN",
        "LOGIN_ERROR",
        "REGISTER",
        "REGISTER_ERROR",
        "LOGOUT",
        "LOGOUT_ERROR",
        "CODE_TO_TOKEN",
        "CODE_TO_TOKEN_ERROR",
        "CLIENT_LOGIN",
        "CLIENT_LOGIN_ERROR",
        "FEDERATED_IDENTITY_LINK",
        "FEDERATED_IDENTITY_LINK_ERROR",
        "REMOVE_FEDERATED_IDENTITY",
        "REMOVE_FEDERATED_IDENTITY_ERROR",
        "UPDATE_EMAIL",
        "UPDATE_EMAIL_ERROR",
        "UPDATE_PROFILE",
        "UPDATE_PROFILE_ERROR",
        "UPDATE_PASSWORD",
        "UPDATE_PASSWORD_ERROR",
        "UPDATE_TOTP",
        "UPDATE_TOTP_ERROR",
        "VERIFY_EMAIL",
        "VERIFY_EMAIL_ERROR",
        "REMOVE_TOTP",
        "REMOVE_TOTP_ERROR",
        "GRANT_CONSENT",
        "GRANT_CONSENT_ERROR",
        "UPDATE_CONSENT",
        "UPDATE_CONSENT_ERROR",
        "REVOKE_GRANT",
        "REVOKE_GRANT_ERROR",
        "SEND_VERIFY_EMAIL",
        "SEND_VERIFY_EMAIL_ERROR",
        "SEND_RESET_PASSWORD",
        "SEND_RESET_PASSWORD_ERROR",
        "SEND_IDENTITY_PROVIDER_LINK",
        "SEND_IDENTITY_PROVIDER_LINK_ERROR",
        "RESET_PASSWORD",
        "RESET_PASSWORD_ERROR",
        "RESTART_AUTHENTICATION",
        "RESTART_AUTHENTICATION_ERROR",
        "IDENTITY_PROVIDER_LINK_ACCOUNT",
        "IDENTITY_PROVIDER_LINK_ACCOUNT_ERROR",
        "IDENTITY_PROVIDER_FIRST_LOGIN",
        "IDENTITY_PROVIDER_FIRST_LOGIN_ERROR",
        "IDENTITY_PROVIDER_POST_LOGIN",
        "IDENTITY_PROVIDER_POST_LOGIN_ERROR",
        "IMPERSONATE",
        "IMPERSONATE_ERROR",
        "CUSTOM_REQUIRED_ACTION",
        "CUSTOM_REQUIRED_ACTION_ERROR",
        "EXECUTE_ACTIONS",
        "EXECUTE_ACTIONS_ERROR",
        "EXECUTE_ACTION_TOKEN",
        "EXECUTE_ACTION_TOKEN_ERROR",
        "CLIENT_REGISTER",
        "CLIENT_REGISTER_ERROR",
        "CLIENT_UPDATE",
        "CLIENT_UPDATE_ERROR",
        "CLIENT_DELETE",
        "CLIENT_DELETE_ERROR",
        "CLIENT_INITIATED_ACCOUNT_LINKING",
        "CLIENT_INITIATED_ACCOUNT_LINKING_ERROR",
        "TOKEN_EXCHANGE",
        "TOKEN_EXCHANGE_ERROR",
        "PERMISSION_TOKEN"
    ],
    "adminEventsEnabled": false,
    "adminEventsDetailsEnabled": false
}
```


### POST Logout all users from session [SAT] <a name="18383acc-d830-4000-860b-42459a8acb00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/logout-all`

Any client that has an admin url will also be told to invalidate any sessions they have.





**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Partial export of existing realm into a JSON file [SAT] <a name="18383acc-d840-4000-894d-885b44425200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/partial-export`

Partial export of existing realm into a JSON file.





**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
 "exportClients": true,
 "exportGroupsAndRoles": true
}
```


### POST Partial import from a JSON file to an existing realm [SAT] <a name="18383acc-d840-4000-8e2c-8702d4957a00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/partialImport`

Partial import from a JSON file to an existing realm.




**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "heroes",
    "realm": "heroes",
    "notBefore": 1589105644,
    "revokeRefreshToken": false,
    "refreshTokenMaxReuse": 0,
    "accessTokenLifespan": 300,
    "accessTokenLifespanForImplicitFlow": 900,
    "ssoSessionIdleTimeout": 1800,
    "ssoSessionMaxLifespan": 36000,
    "ssoSessionIdleTimeoutRememberMe": 0,
    "ssoSessionMaxLifespanRememberMe": 0,
    "offlineSessionIdleTimeout": 2592000,
    "offlineSessionMaxLifespanEnabled": false,
    "offlineSessionMaxLifespan": 5184000,
    "clientSessionIdleTimeout": 0,
    "clientSessionMaxLifespan": 0,
    "accessCodeLifespan": 60,
    "accessCodeLifespanUserAction": 300,
    "accessCodeLifespanLogin": 1800,
    "actionTokenGeneratedByAdminLifespan": 43200,
    "actionTokenGeneratedByUserLifespan": 300,
    "enabled": true,
    "sslRequired": "external",
    "registrationAllowed": false,
    "registrationEmailAsUsername": false,
    "rememberMe": false,
    "verifyEmail": false,
    "loginWithEmailAllowed": true,
    "duplicateEmailsAllowed": false,
    "resetPasswordAllowed": false,
    "editUsernameAllowed": false,
    "bruteForceProtected": false,
    "permanentLockout": false,
    "maxFailureWaitSeconds": 900,
    "minimumQuickLoginWaitSeconds": 60,
    "waitIncrementSeconds": 60,
    "quickLoginCheckMilliSeconds": 1000,
    "maxDeltaTimeSeconds": 43200,
    "failureFactor": 30,
    "defaultRoles": [
        "offline_access",
        "uma_authorization"
    ],
    "requiredCredentials": [
        "password"
    ],
    "otpPolicyType": "totp",
    "otpPolicyAlgorithm": "HmacSHA1",
    "otpPolicyInitialCounter": 0,
    "otpPolicyDigits": 6,
    "otpPolicyLookAheadWindow": 1,
    "otpPolicyPeriod": 30,
    "otpSupportedApplications": [
        "FreeOTP",
        "Google Authenticator"
    ],
    "webAuthnPolicyRpEntityName": "keycloak",
    "webAuthnPolicySignatureAlgorithms": [
        "ES256"
    ],
    "webAuthnPolicyRpId": "",
    "webAuthnPolicyAttestationConveyancePreference": "not specified",
    "webAuthnPolicyAuthenticatorAttachment": "not specified",
    "webAuthnPolicyRequireResidentKey": "not specified",
    "webAuthnPolicyUserVerificationRequirement": "not specified",
    "webAuthnPolicyCreateTimeout": 0,
    "webAuthnPolicyAvoidSameAuthenticatorRegister": false,
    "webAuthnPolicyAcceptableAaguids": [],
    "webAuthnPolicyPasswordlessRpEntityName": "keycloak",
    "webAuthnPolicyPasswordlessSignatureAlgorithms": [
        "ES256"
    ],
    "webAuthnPolicyPasswordlessRpId": "",
    "webAuthnPolicyPasswordlessAttestationConveyancePreference": "not specified",
    "webAuthnPolicyPasswordlessAuthenticatorAttachment": "not specified",
    "webAuthnPolicyPasswordlessRequireResidentKey": "not specified",
    "webAuthnPolicyPasswordlessUserVerificationRequirement": "not specified",
    "webAuthnPolicyPasswordlessCreateTimeout": 0,
    "webAuthnPolicyPasswordlessAvoidSameAuthenticatorRegister": false,
    "webAuthnPolicyPasswordlessAcceptableAaguids": [],
    "scopeMappings": [
        {
            "clientScope": "offline_access",
            "roles": [
                "offline_access"
            ]
        }
    ],
    "clientScopes": [
        {
            "id": "c428dc50-0677-44ff-aee8-a3568046fd30",
            "name": "address",
            "description": "OpenID Connect built-in scope: address",
            "protocol": "openid-connect",
            "attributes": {
                "include.in.token.scope": "true",
                "display.on.consent.screen": "true",
                "consent.screen.text": "${addressScopeConsentText}"
            },
            "protocolMappers": [
                {
                    "id": "b8adec7c-78a4-447d-a1f6-07945407de39",
                    "name": "address",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-address-mapper",
                    "consentRequired": false,
                    "config": {
                        "user.attribute.formatted": "formatted",
                        "user.attribute.country": "country",
                        "user.attribute.postal_code": "postal_code",
                        "userinfo.token.claim": "true",
                        "user.attribute.street": "street",
                        "id.token.claim": "true",
                        "user.attribute.region": "region",
                        "access.token.claim": "true",
                        "user.attribute.locality": "locality"
                    }
                }
            ]
        },
        {
            "id": "4f841085-b7be-4596-b99b-15422e16bf0b",
            "name": "email",
            "description": "OpenID Connect built-in scope: email +",
            "protocol": "openid-connect",
            "attributes": {
                "include.in.token.scope": "true",
                "display.on.consent.screen": "true",
                "consent.screen.text": "${emailScopeConsentText}"
            },
            "protocolMappers": [
                {
                    "id": "62224d4c-7181-4790-a3c9-71cdbf1516a5",
                    "name": "email",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-property-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "email",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "email",
                        "jsonType.label": "String"
                    }
                },
                {
                    "id": "af6262f6-6b60-4e47-899e-248ebbe55705",
                    "name": "protocol-mapper-2",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-property-mapper",
                    "consentRequired": false,
                    "config": {}
                },
                {
                    "id": "e7b52fef-f525-4314-abf3-267d9f48082e",
                    "name": "email verified",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-property-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "emailVerified",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "email_verified",
                        "jsonType.label": "boolean"
                    }
                },
                {
                    "id": "ab13e658-d258-483a-b6d2-93cd7f45672d",
                    "name": "protocol-mapper",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-property-mapper",
                    "consentRequired": false,
                    "config": {}
                }
            ]
        },
        {
            "id": "51925c34-1804-4159-a970-e1a65d3323c0",
            "name": "microprofile-jwt",
            "description": "Microprofile - JWT built-in scope",
            "protocol": "openid-connect",
            "attributes": {
                "include.in.token.scope": "true",
                "display.on.consent.screen": "false"
            },
            "protocolMappers": [
                {
                    "id": "cccf4cd9-401d-48e9-ae86-5c2bf720220f",
                    "name": "groups",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-realm-role-mapper",
                    "consentRequired": false,
                    "config": {
                        "multivalued": "true",
                        "user.attribute": "foo",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "groups",
                        "jsonType.label": "String"
                    }
                },
                {
                    "id": "b00e8121-fb23-44fa-9592-09e6d3650436",
                    "name": "upn",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-property-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "username",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "upn",
                        "jsonType.label": "String"
                    }
                }
            ]
        },
        {
            "id": "42eb8c36-025e-424a-b43e-3e67305db9cb",
            "name": "offline_access",
            "description": "OpenID Connect built-in scope: offline_access",
            "protocol": "openid-connect",
            "attributes": {
                "consent.screen.text": "${offlineAccessScopeConsentText}",
                "display.on.consent.screen": "true"
            }
        },
        {
            "id": "22369324-bf37-426e-8704-f648f62d27f8",
            "name": "phone",
            "description": "OpenID Connect built-in scope: phone",
            "protocol": "openid-connect",
            "attributes": {
                "include.in.token.scope": "true",
                "display.on.consent.screen": "true",
                "consent.screen.text": "${phoneScopeConsentText}"
            },
            "protocolMappers": [
                {
                    "id": "d7d5a1cc-f343-49b3-aa46-b42e6b274e83",
                    "name": "phone number verified",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-attribute-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "phoneNumberVerified",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "phone_number_verified",
                        "jsonType.label": "boolean"
                    }
                },
                {
                    "id": "d41cc5c8-9401-491f-adea-b5806c3adacd",
                    "name": "phone number",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-attribute-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "phoneNumber",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "phone_number",
                        "jsonType.label": "String"
                    }
                }
            ]
        },
        {
            "id": "082e427a-aef5-4461-b8c3-970a90991b1e",
            "name": "profile",
            "description": "OpenID Connect built-in scope: profile",
            "protocol": "openid-connect",
            "attributes": {
                "include.in.token.scope": "true",
                "display.on.consent.screen": "true",
                "consent.screen.text": "${profileScopeConsentText}"
            },
            "protocolMappers": [
                {
                    "id": "a322869a-9430-4aa9-b8b0-29bed1905160",
                    "name": "locale",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-attribute-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "locale",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "locale",
                        "jsonType.label": "String"
                    }
                },
                {
                    "id": "62e05562-a7e4-40a6-954e-13473ceb34c2",
                    "name": "given name",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-property-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "firstName",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "given_name",
                        "jsonType.label": "String"
                    }
                },
                {
                    "id": "9a98e8d2-238d-40da-b07c-968bc494ad5f",
                    "name": "nickname",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-attribute-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "nickname",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "nickname",
                        "jsonType.label": "String"
                    }
                },
                {
                    "id": "4ea62cf5-f2be-449b-8e62-19d82ee3bf25",
                    "name": "gender",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-attribute-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "gender",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "gender",
                        "jsonType.label": "String"
                    }
                },
                {
                    "id": "8003e7da-6bbe-41cb-b44a-8ae5fb5305e0",
                    "name": "full name",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-full-name-mapper",
                    "consentRequired": false,
                    "config": {
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "userinfo.token.claim": "true"
                    }
                },
                {
                    "id": "30e14266-1aeb-4a59-a337-3e6393a4a111",
                    "name": "family name",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-property-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "lastName",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "family_name",
                        "jsonType.label": "String"
                    }
                },
                {
                    "id": "c1d92d15-7d19-4260-af10-37a69b9cd193",
                    "name": "website",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-attribute-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "website",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "website",
                        "jsonType.label": "String"
                    }
                },
                {
                    "id": "5a559fe9-a688-4d6f-9b0f-aa03f041e3e3",
                    "name": "birthdate",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-attribute-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "birthdate",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "birthdate",
                        "jsonType.label": "String"
                    }
                },
                {
                    "id": "1cdde753-3ee5-441b-8df2-60da7ecca9d6",
                    "name": "profile",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-attribute-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "profile",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "profile",
                        "jsonType.label": "String"
                    }
                },
                {
                    "id": "6308310b-daee-461f-9eba-b8c922c04dfd",
                    "name": "middle name",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-attribute-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "middleName",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "middle_name",
                        "jsonType.label": "String"
                    }
                },
                {
                    "id": "b2871f34-48d3-437a-aa40-7c293ce63827",
                    "name": "updated at",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-attribute-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "updatedAt",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "updated_at",
                        "jsonType.label": "String"
                    }
                },
                {
                    "id": "45edbce1-716c-47c1-b1ca-28124ada1e9d",
                    "name": "picture",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-attribute-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "picture",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "picture",
                        "jsonType.label": "String"
                    }
                },
                {
                    "id": "609d8572-b194-4a2a-bc97-d9aecd26daaa",
                    "name": "zoneinfo",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-attribute-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "zoneinfo",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "zoneinfo",
                        "jsonType.label": "String"
                    }
                },
                {
                    "id": "ac373d8f-539c-4242-bdbe-def6b32a8582",
                    "name": "username",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-property-mapper",
                    "consentRequired": false,
                    "config": {
                        "userinfo.token.claim": "true",
                        "user.attribute": "username",
                        "id.token.claim": "true",
                        "access.token.claim": "true",
                        "claim.name": "preferred_username",
                        "jsonType.label": "String"
                    }
                }
            ]
        },
        {
            "id": "393eed37-8c38-4b75-aaac-c3e950cf43fc",
            "name": "role_list",
            "description": "SAML role list",
            "protocol": "saml",
            "attributes": {
                "consent.screen.text": "${samlRoleListScopeConsentText}",
                "display.on.consent.screen": "true"
            },
            "protocolMappers": [
                {
                    "id": "7794d99d-0738-49c9-8b75-8acb188a78e5",
                    "name": "role list",
                    "protocol": "saml",
                    "protocolMapper": "saml-role-list-mapper",
                    "consentRequired": false,
                    "config": {
                        "single": "false",
                        "attribute.nameformat": "Basic",
                        "attribute.name": "Role"
                    }
                }
            ]
        },
        {
            "id": "c799cfa9-fc42-4cf5-8cb2-b1730c4ec012",
            "name": "roles",
            "description": "OpenID Connect scope for add user roles to the access token",
            "protocol": "openid-connect",
            "attributes": {
                "include.in.token.scope": "false",
                "display.on.consent.screen": "true",
                "consent.screen.text": "${rolesScopeConsentText}"
            },
            "protocolMappers": [
                {
                    "id": "efdc6358-b579-4600-8b66-b48a918c041f",
                    "name": "client roles",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-client-role-mapper",
                    "consentRequired": false,
                    "config": {
                        "multivalued": "true",
                        "user.attribute": "foo",
                        "access.token.claim": "true",
                        "claim.name": "resource_access.${client_id}.roles",
                        "jsonType.label": "String"
                    }
                },
                {
                    "id": "c1c51bdd-7165-4b8f-8ba2-eccb9dc32c17",
                    "name": "audience resolve",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-audience-resolve-mapper",
                    "consentRequired": false,
                    "config": {}
                },
                {
                    "id": "c57a0d2e-d119-4ed3-ac27-2d83f86c066c",
                    "name": "realm roles",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-usermodel-realm-role-mapper",
                    "consentRequired": false,
                    "config": {
                        "multivalued": "true",
                        "user.attribute": "foo",
                        "access.token.claim": "true",
                        "claim.name": "realm_access.roles",
                        "jsonType.label": "String"
                    }
                }
            ]
        },
        {
            "id": "59df1f86-bf4b-4962-bc96-c64ed8f93327",
            "name": "test-client-scope",
            "protocol": "openid-connect",
            "attributes": {
                "include.in.token.scope": "true",
                "display.on.consent.screen": "true"
            }
        },
        {
            "id": "3a4f0249-9131-40c1-b8f4-027a778af023",
            "name": "web-origins",
            "description": "OpenID Connect scope for add allowed web origins to the access token",
            "protocol": "openid-connect",
            "attributes": {
                "include.in.token.scope": "false",
                "display.on.consent.screen": "false",
                "consent.screen.text": ""
            },
            "protocolMappers": [
                {
                    "id": "2b84bf32-ed3f-4053-add2-d30eff142db0",
                    "name": "allowed web origins",
                    "protocol": "openid-connect",
                    "protocolMapper": "oidc-allowed-origins-mapper",
                    "consentRequired": false,
                    "config": {}
                }
            ]
        }
    ],
    "defaultDefaultClientScopes": [
        "profile",
        "role_list",
        "web-origins",
        "email",
        "roles"
    ],
    "defaultOptionalClientScopes": [
        "phone",
        "offline_access",
        "microprofile-jwt",
        "test-client-scope",
        "address"
    ],
    "browserSecurityHeaders": {
        "contentSecurityPolicyReportOnly": "",
        "xContentTypeOptions": "nosniff",
        "xRobotsTag": "none",
        "xFrameOptions": "SAMEORIGIN",
        "contentSecurityPolicy": "frame-src 'self'; frame-ancestors 'self'; object-src 'none';",
        "xXSSProtection": "1; mode=block",
        "strictTransportSecurity": "max-age=31536000; includeSubDomains"
    },
    "smtpServer": {},
    "eventsEnabled": false,
    "eventsListeners": [
        "jboss-logging"
    ],
    "enabledEventTypes": [],
    "adminEventsEnabled": false,
    "adminEventsDetailsEnabled": false,
    "identityProviders": [
        {
            "alias": "keycloak-oidc",
            "internalId": "d79d0d65-8ee1-47f0-8611-f9e6eea71f20",
            "providerId": "keycloak-oidc",
            "enabled": true,
            "updateProfileFirstLoginMode": "on",
            "trustEmail": false,
            "storeToken": false,
            "addReadTokenRoleOnCreate": false,
            "authenticateByDefault": false,
            "linkOnly": false,
            "firstBrokerLoginFlowAlias": "first broker login",
            "config": {
                "clientId": "ssss",
                "tokenUrl": "http://localhost",
                "authorizationUrl": "http://localhost",
                "clientAuthMethod": "client_secret_basic",
                "syncMode": "IMPORT",
                "clientSecret": "**********",
                "useJwksUrl": "true"
            }
        },
        {
            "alias": "keycloak-oidc-2",
            "internalId": "7cf3fd74-8d3a-4c8d-b651-fcc885df8a31",
            "providerId": "keycloak-oidc",
            "enabled": true,
            "updateProfileFirstLoginMode": "on",
            "trustEmail": false,
            "storeToken": false,
            "addReadTokenRoleOnCreate": false,
            "authenticateByDefault": false,
            "linkOnly": false,
            "firstBrokerLoginFlowAlias": "first broker login",
            "config": {}
        }
    ],
    "identityProviderMappers": [
        {
            "id": "42c7b62d-4383-42c9-a8a0-65519e2c2543",
            "name": "test-mapper",
            "identityProviderAlias": "keycloak-oidc2",
            "identityProviderMapper": "keycloak-oidc",
            "config": {}
        },
        {
            "id": "ea65c956-24c7-4587-8fe7-c07222e3485d",
            "name": "test",
            "identityProviderAlias": "keycloak-oidc-2",
            "identityProviderMapper": "hardcoded-user-session-attribute-idp-mapper",
            "config": {
                "syncMode": "INHERIT"
            }
        }
    ],
    "components": {
        "org.keycloak.services.clientregistration.policy.ClientRegistrationPolicy": [
            {
                "id": "858f626c-d3b5-465b-b3ef-1a47deeb33b4",
                "name": "test",
                "providerId": "max-clients",
                "subType": "anonymous",
                "subComponents": {},
                "config": {
                    "max-clients": [
                        "200"
                    ]
                }
            },
            {
                "id": "7a084caa-36f4-4ea4-8dcb-56b1b189c2fa",
                "name": "Trusted Hosts",
                "providerId": "trusted-hosts",
                "subType": "anonymous",
                "subComponents": {},
                "config": {
                    "host-sending-registration-request-must-match": [
                        "true"
                    ],
                    "client-uris-must-match": [
                        "true"
                    ]
                }
            },
            {
                "id": "94958c8d-2ca3-4680-8367-e187d295d707",
                "name": "Allowed Client Scopes",
                "providerId": "allowed-client-templates",
                "subType": "anonymous",
                "subComponents": {},
                "config": {
                    "allow-default-scopes": [
                        "true"
                    ]
                }
            },
            {
                "id": "a07ec653-9fe9-4c92-a95e-676e6390bb7e",
                "name": "Full Scope Disabled",
                "providerId": "scope",
                "subType": "anonymous",
                "subComponents": {},
                "config": {}
            },
            {
                "id": "5fbc94d0-5743-480b-9c55-dfe2631ddcd1",
                "name": "Allowed Protocol Mapper Types",
                "providerId": "allowed-protocol-mappers",
                "subType": "anonymous",
                "subComponents": {},
                "config": {
                    "allowed-protocol-mapper-types": [
                        "oidc-usermodel-property-mapper",
                        "saml-role-list-mapper",
                        "oidc-address-mapper",
                        "oidc-usermodel-attribute-mapper",
                        "oidc-sha256-pairwise-sub-mapper",
                        "saml-user-attribute-mapper",
                        "saml-user-property-mapper",
                        "oidc-full-name-mapper"
                    ]
                }
            },
            {
                "id": "9790934a-913c-4027-8e9a-0c5b096a8b55",
                "name": "Allowed Protocol Mapper Types",
                "providerId": "allowed-protocol-mappers",
                "subType": "authenticated",
                "subComponents": {},
                "config": {
                    "allowed-protocol-mapper-types": [
                        "oidc-full-name-mapper",
                        "saml-role-list-mapper",
                        "saml-user-attribute-mapper",
                        "oidc-usermodel-attribute-mapper",
                        "oidc-sha256-pairwise-sub-mapper",
                        "oidc-address-mapper",
                        "oidc-usermodel-property-mapper",
                        "saml-user-property-mapper"
                    ]
                }
            },
            {
                "id": "11951897-c9f1-4f46-9df4-16e05dedd4a2",
                "name": "Consent Required",
                "providerId": "consent-required",
                "subType": "anonymous",
                "subComponents": {},
                "config": {}
            },
            {
                "id": "e3f35697-fc92-4d38-80d9-2f643dca22e0",
                "name": "Allowed Client Scopes",
                "providerId": "allowed-client-templates",
                "subType": "authenticated",
                "subComponents": {},
                "config": {
                    "allow-default-scopes": [
                        "true"
                    ]
                }
            },
            {
                "id": "4751745f-877b-4414-80c5-27dbf3dc2e88",
                "name": "Max Clients Limit",
                "providerId": "max-clients",
                "subType": "anonymous",
                "subComponents": {},
                "config": {
                    "max-clients": [
                        "200"
                    ]
                }
            }
        ],
        "org.keycloak.keys.KeyProvider": [
            {
                "id": "60ae5de8-bef8-40ad-ab08-ccd72894202e",
                "name": "hmac-generated",
                "providerId": "hmac-generated",
                "subComponents": {},
                "config": {
                    "priority": [
                        "100"
                    ],
                    "algorithm": [
                        "HS256"
                    ]
                }
            },
            {
                "id": "362b0a6a-8a0c-4394-851e-b6ad6be75ea1",
                "name": "aes-generated",
                "providerId": "aes-generated",
                "subComponents": {},
                "config": {
                    "priority": [
                        "100"
                    ]
                }
            },
            {
                "id": "5208907e-04f6-43a9-b10f-77042a355be5",
                "name": "rsa-generated",
                "providerId": "rsa-generated",
                "subComponents": {},
                "config": {
                    "priority": [
                        "100"
                    ]
                }
            }
        ]
    },
    "internationalizationEnabled": false,
    "supportedLocales": [],
    "authenticationFlows": [
        {
            "id": "5e435b45-5046-410c-86b1-4d0a2593600d",
            "alias": "Account verification options",
            "description": "Method with which to verity the existing account",
            "providerId": "basic-flow",
            "topLevel": false,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "idp-email-verification",
                    "requirement": "ALTERNATIVE",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "requirement": "ALTERNATIVE",
                    "priority": 20,
                    "flowAlias": "Verify Existing Account by Re-authentication",
                    "userSetupAllowed": false,
                    "autheticatorFlow": true
                }
            ]
        },
        {
            "id": "a1aa24b3-544a-4d04-83ca-ad091df14325",
            "alias": "Authentication Options",
            "description": "Authentication options.",
            "providerId": "basic-flow",
            "topLevel": false,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "basic-auth",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "basic-auth-otp",
                    "requirement": "DISABLED",
                    "priority": 20,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "auth-spnego",
                    "requirement": "DISABLED",
                    "priority": 30,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                }
            ]
        },
        {
            "id": "8a496ed5-2356-4716-a195-fff21090ffc1",
            "alias": "Browser - Conditional OTP",
            "description": "Flow to determine if the OTP is required for the authentication",
            "providerId": "basic-flow",
            "topLevel": false,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "conditional-user-configured",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "auth-otp-form",
                    "requirement": "REQUIRED",
                    "priority": 20,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                }
            ]
        },
        {
            "id": "13383e81-1407-4405-a752-b995c06feea2",
            "alias": "Copy of browser",
            "description": "browser based authentication not cool bro",
            "providerId": "basic-flow",
            "topLevel": true,
            "builtIn": false,
            "authenticationExecutions": [
                {
                    "authenticator": "auth-cookie",
                    "requirement": "ALTERNATIVE",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "auth-spnego",
                    "requirement": "DISABLED",
                    "priority": 20,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "identity-provider-redirector",
                    "requirement": "ALTERNATIVE",
                    "priority": 25,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "requirement": "ALTERNATIVE",
                    "priority": 30,
                    "flowAlias": "Copy of browser forms",
                    "userSetupAllowed": false,
                    "autheticatorFlow": true
                }
            ]
        },
        {
            "id": "4df02036-7ead-4411-95c6-57b637be611e",
            "alias": "Copy of browser Browser - Conditional OTP",
            "description": "Flow to determine if the OTP is required for the authentication",
            "providerId": "basic-flow",
            "topLevel": false,
            "builtIn": false,
            "authenticationExecutions": [
                {
                    "authenticator": "conditional-user-configured",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "auth-otp-form",
                    "requirement": "REQUIRED",
                    "priority": 20,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                }
            ]
        },
        {
            "id": "91d600e4-527b-4c10-ac47-f55a5bbddc7c",
            "alias": "Copy of browser forms",
            "description": "Username, password, otp and other auth forms.",
            "providerId": "basic-flow",
            "topLevel": false,
            "builtIn": false,
            "authenticationExecutions": [
                {
                    "authenticator": "auth-username-password-form",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "requirement": "CONDITIONAL",
                    "priority": 20,
                    "flowAlias": "Copy of browser Browser - Conditional OTP",
                    "userSetupAllowed": false,
                    "autheticatorFlow": true
                }
            ]
        },
        {
            "id": "eeb72b2b-3568-4508-8c02-3de699518177",
            "alias": "Direct Grant - Conditional OTP",
            "description": "Flow to determine if the OTP is required for the authentication",
            "providerId": "basic-flow",
            "topLevel": false,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "conditional-user-configured",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "direct-grant-validate-otp",
                    "requirement": "REQUIRED",
                    "priority": 20,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                }
            ]
        },
        {
            "id": "4f09238b-c044-48f8-8def-febfabd7abb0",
            "alias": "First broker login - Conditional OTP",
            "description": "Flow to determine if the OTP is required for the authentication",
            "providerId": "basic-flow",
            "topLevel": false,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "conditional-user-configured",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "auth-otp-form",
                    "requirement": "REQUIRED",
                    "priority": 20,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                }
            ]
        },
        {
            "id": "a525d44c-6261-4b5f-8187-7991357d46b5",
            "alias": "Handle Existing Account",
            "description": "Handle what to do if there is existing account with same email/username like authenticated identity provider",
            "providerId": "basic-flow",
            "topLevel": false,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "idp-confirm-link",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "requirement": "REQUIRED",
                    "priority": 20,
                    "flowAlias": "Account verification options",
                    "userSetupAllowed": false,
                    "autheticatorFlow": true
                }
            ]
        },
        {
            "id": "f1e669d0-1b44-44b5-8992-b60ae1958b4c",
            "alias": "Reset - Conditional OTP",
            "description": "Flow to determine if the OTP should be reset or not. Set to REQUIRED to force.",
            "providerId": "basic-flow",
            "topLevel": false,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "conditional-user-configured",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "reset-otp",
                    "requirement": "REQUIRED",
                    "priority": 20,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                }
            ]
        },
        {
            "id": "f2566db0-e455-4a77-8627-08429f754095",
            "alias": "User creation or linking",
            "description": "Flow for the existing/non-existing user alternatives",
            "providerId": "basic-flow",
            "topLevel": false,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticatorConfig": "create unique user config",
                    "authenticator": "idp-create-user-if-unique",
                    "requirement": "ALTERNATIVE",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "requirement": "ALTERNATIVE",
                    "priority": 20,
                    "flowAlias": "Handle Existing Account",
                    "userSetupAllowed": false,
                    "autheticatorFlow": true
                }
            ]
        },
        {
            "id": "777163da-9d74-471b-9125-aceef09f3c67",
            "alias": "Verify Existing Account by Re-authentication",
            "description": "Reauthentication of existing account",
            "providerId": "basic-flow",
            "topLevel": false,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "idp-username-password-form",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "requirement": "CONDITIONAL",
                    "priority": 20,
                    "flowAlias": "First broker login - Conditional OTP",
                    "userSetupAllowed": false,
                    "autheticatorFlow": true
                }
            ]
        },
        {
            "id": "edc242a1-822e-4945-8d62-70b826fa8d88",
            "alias": "bff",
            "description": "new flow bff",
            "providerId": "generic",
            "topLevel": false,
            "builtIn": false,
            "authenticationExecutions": []
        },
        {
            "id": "bf2ffb04-39eb-4de9-b302-29f8d2735cbb",
            "alias": "browser",
            "description": "browser based authentication not cool bro",
            "providerId": "basic-flow",
            "topLevel": true,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "auth-cookie",
                    "requirement": "ALTERNATIVE",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "auth-spnego",
                    "requirement": "DISABLED",
                    "priority": 20,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "identity-provider-redirector",
                    "requirement": "ALTERNATIVE",
                    "priority": 25,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "requirement": "ALTERNATIVE",
                    "priority": 30,
                    "flowAlias": "forms",
                    "userSetupAllowed": false,
                    "autheticatorFlow": true
                }
            ]
        },
        {
            "id": "76ec235d-ea17-47a1-8497-51b561630630",
            "alias": "browser-for-fun",
            "description": "browser based authentication",
            "providerId": "basic-flow",
            "topLevel": true,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "reset-password",
                    "requirement": "DISABLED",
                    "priority": 0,
                    "flowAlias": "bff",
                    "userSetupAllowed": false,
                    "autheticatorFlow": true
                }
            ]
        },
        {
            "id": "6ad9fe31-5e18-45c2-8d8e-ec64cde57c2a",
            "alias": "clients",
            "description": "Base authentication for clients",
            "providerId": "client-flow",
            "topLevel": true,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "client-secret",
                    "requirement": "ALTERNATIVE",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "client-jwt",
                    "requirement": "ALTERNATIVE",
                    "priority": 20,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "client-secret-jwt",
                    "requirement": "ALTERNATIVE",
                    "priority": 30,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "client-x509",
                    "requirement": "ALTERNATIVE",
                    "priority": 40,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                }
            ]
        },
        {
            "id": "66831086-47c5-4b7b-bd47-a90f1bf20723",
            "alias": "direct grant",
            "description": "OpenID Connect Resource Owner Grant",
            "providerId": "basic-flow",
            "topLevel": true,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "direct-grant-validate-username",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "direct-grant-validate-password",
                    "requirement": "REQUIRED",
                    "priority": 20,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "requirement": "CONDITIONAL",
                    "priority": 30,
                    "flowAlias": "Direct Grant - Conditional OTP",
                    "userSetupAllowed": false,
                    "autheticatorFlow": true
                }
            ]
        },
        {
            "id": "97e96691-c3a9-49da-a532-d18b033455c6",
            "alias": "docker auth",
            "description": "Used by Docker clients to authenticate against the IDP",
            "providerId": "basic-flow",
            "topLevel": true,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "docker-http-basic-authenticator",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                }
            ]
        },
        {
            "id": "b18008dd-b315-4caa-8992-c0154ce7787c",
            "alias": "first broker login",
            "description": "Actions taken after first broker login with identity provider account, which is not yet linked to any Keycloak account",
            "providerId": "basic-flow",
            "topLevel": true,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "idp-review-profile",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "requirement": "REQUIRED",
                    "priority": 20,
                    "flowAlias": "User creation or linking",
                    "userSetupAllowed": false,
                    "autheticatorFlow": true
                }
            ]
        },
        {
            "id": "bd4d3510-2799-4012-8882-027f7695cb4b",
            "alias": "forms",
            "description": "Username, password, otp and other auth forms.",
            "providerId": "basic-flow",
            "topLevel": false,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "auth-username-password-form",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "requirement": "CONDITIONAL",
                    "priority": 20,
                    "flowAlias": "Browser - Conditional OTP",
                    "userSetupAllowed": false,
                    "autheticatorFlow": true
                }
            ]
        },
        {
            "id": "d91e3c14-54e1-419f-b1f1-43339a580141",
            "alias": "http challenge",
            "description": "An authentication flow based on challenge-response HTTP Authentication Schemes",
            "providerId": "basic-flow",
            "topLevel": true,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "no-cookie-redirect",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "requirement": "REQUIRED",
                    "priority": 20,
                    "flowAlias": "Authentication Options",
                    "userSetupAllowed": false,
                    "autheticatorFlow": true
                }
            ]
        },
        {
            "id": "2b16b0c5-0560-4925-a117-7cbe6fa4f47f",
            "alias": "registration",
            "description": "registration flow",
            "providerId": "basic-flow",
            "topLevel": true,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "registration-page-form",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "flowAlias": "registration form",
                    "userSetupAllowed": false,
                    "autheticatorFlow": true
                }
            ]
        },
        {
            "id": "c8dbf2d2-889a-492c-81c1-d041dd38d605",
            "alias": "registration form",
            "description": "registration form",
            "providerId": "form-flow",
            "topLevel": false,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "registration-user-creation",
                    "requirement": "REQUIRED",
                    "priority": 20,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "registration-profile-action",
                    "requirement": "REQUIRED",
                    "priority": 40,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "registration-password-action",
                    "requirement": "REQUIRED",
                    "priority": 50,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "registration-recaptcha-action",
                    "requirement": "DISABLED",
                    "priority": 60,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                }
            ]
        },
        {
            "id": "b3c01cad-1f6b-4132-9a5c-80cc54b27ebb",
            "alias": "reset credentials",
            "description": "Reset credentials for a user if they forgot their password or something",
            "providerId": "basic-flow",
            "topLevel": true,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "reset-credentials-choose-user",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "reset-credential-email",
                    "requirement": "REQUIRED",
                    "priority": 20,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "authenticator": "reset-password",
                    "requirement": "REQUIRED",
                    "priority": 30,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                },
                {
                    "requirement": "CONDITIONAL",
                    "priority": 40,
                    "flowAlias": "Reset - Conditional OTP",
                    "userSetupAllowed": false,
                    "autheticatorFlow": true
                }
            ]
        },
        {
            "id": "ce62a973-c672-478e-8756-09d8d27a6761",
            "alias": "saml ecp",
            "description": "SAML ECP Profile Authentication Flow",
            "providerId": "basic-flow",
            "topLevel": true,
            "builtIn": true,
            "authenticationExecutions": [
                {
                    "authenticator": "http-basic-authenticator",
                    "requirement": "REQUIRED",
                    "priority": 10,
                    "userSetupAllowed": false,
                    "autheticatorFlow": false
                }
            ]
        }
    ],
    "authenticatorConfig": [
        {
            "id": "eb03d05e-0dcb-4533-9391-3e45a20fba4c",
            "config": {
                "update.profile.on.first.login": "missing"
            }
        },
        {
            "id": "fe4adbd1-838e-4655-b157-9421353fa7c9",
            "alias": "create unique user config",
            "config": {
                "require.password.update.after.registration": "false"
            }
        }
    ],
    "requiredActions": [
        {
            "alias": "CONFIGURE_TOTP",
            "name": "Configure OTP",
            "providerId": "CONFIGURE_TOTP",
            "enabled": true,
            "defaultAction": false,
            "priority": 10,
            "config": {}
        },
        {
            "alias": "terms_and_conditions",
            "name": "Terms and Conditions",
            "providerId": "terms_and_conditions",
            "enabled": false,
            "defaultAction": false,
            "priority": 20,
            "config": {}
        },
        {
            "alias": "UPDATE_PROFILE",
            "name": "Update Profile",
            "providerId": "UPDATE_PROFILE",
            "enabled": true,
            "defaultAction": false,
            "priority": 40,
            "config": {}
        },
        {
            "name": "Update Profile +",
            "providerId": "UPDATE_PASSWORD",
            "enabled": true,
            "defaultAction": false,
            "priority": 40,
            "config": {}
        },
        {
            "alias": "VERIFY_EMAIL",
            "name": "Verify Email",
            "providerId": "VERIFY_EMAIL",
            "enabled": true,
            "defaultAction": false,
            "priority": 50,
            "config": {}
        },
        {
            "alias": "update_user_locale",
            "name": "Update User Locale",
            "providerId": "update_user_locale",
            "enabled": true,
            "defaultAction": false,
            "priority": 1000,
            "config": {}
        },
        {
            "alias": "reset-password",
            "name": "new-reset-password",
            "providerId": "reset-password",
            "enabled": true,
            "defaultAction": false,
            "priority": 1001,
            "config": {}
        }
    ],
    "browserFlow": "browser",
    "registrationFlow": "registration",
    "directGrantFlow": "direct grant",
    "resetCredentialsFlow": "reset credentials",
    "clientAuthenticationFlow": "clients",
    "dockerAuthenticationFlow": "docker auth",
    "attributes": {},
    "keycloakVersion": "10.0.0",
    "userManagedAccessAllowed": false
}
```


### POST Push the realmâ€™s revocation policy [SAT] <a name="18383acc-d840-4000-8b89-7939d0eba600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/push-revocation`

Push the realmâ€™s revocation policy to any client that has an admin url associated with it.




**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Remove a specific user session [SAT] <a name="18383acc-d850-4000-8787-3e6445851e00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/sessions/{{sessionId}}`

Any client that has an admin url will also be told to invalidate this particular session.




**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Test LDAP connection [SAT] <a name="18383acc-d850-4000-8369-d31ecf248b00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/testLDAPConnection`

Test LDAP connection




**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"config": {}
}
```


### POST Test SMTP connection [SAT] <a name="18383acc-d850-4000-8218-b2edecbbc100"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/testSMTPConnection`

Test SMTP connection




**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"settings": {}
}
```


### GET Get users-management-permissions [SAT] <a name="18383acc-d860-4000-8a2f-8e76bdde7b00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users-management-permissions`

Get users-management-permissions



**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update users-management-permissions [SAT] <a name="18383acc-d860-4000-8816-f700439f0400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users-management-permissions`

Update users-management-permissions



**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"enabled": false
}
```


## Role Mapper <a name="18383acc-d860-4000-8131-7c2610089c00"></a>



### GET Get role mappings [SAT] <a name="18383acc-d860-4000-8c81-868b4c127d00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}/role-mappings`

Get role mappings



**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Update role mappings [SAT] <a name="18383acc-d860-4000-862c-f45738104200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}/role-mappings/realm`

Update role mappings



**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
[{
	"attributes": {},
	"clientRole": false,
	"composite": false,
	"description": "added role mapping from rest api",
	"name": "Investigator",
	"containerId": "heroes"
}]
```


### GET Get realm-level role mappings  [SAT] <a name="18383acc-d870-4000-8d34-f2cf330a8800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}/role-mappings/realm`

Get realm-level role mappings



**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get available realm-level role mappings  [SAT] <a name="18383acc-d870-4000-861b-8dfa071dda00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}/role-mappings/realm/available`

Get available realm-level role mappings



**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Delete realm-level role mappings  [SAT] <a name="18383acc-d870-4000-8067-cc76916dab00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}/role-mappings/realm`

Delete realm-level role mappings



**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"attributes": {},
	"clientRole": false,
	"composite": false,
	"description": "added role mapping from rest api",
	"name": "investigator"
}
```


### GET Get effective realm-level role mappings  [SAT] <a name="18383acc-d880-4000-81f6-43af14023b00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/groups/{{groupId}}/role-mappings/realm/composite`

Get effective realm-level role mappings This will recurse all composite roles to get the result.


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get role mappings [SAT] <a name="18383acc-d880-4000-8003-80e3241fe400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/role-mappings`

Get role mappings


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get realm-level role mappings [SAT] <a name="18383acc-d880-4000-895b-18f15db68f00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/role-mappings/realm`

Get realm-level role mappings

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Add realm-level role mappings to the user [SAT] <a name="18383acc-d880-4000-8e90-0c0f91216700"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/role-mappings/realm`

Add realm-level role mappings to the user

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
[{
        "name": "offline_access_2",
        "description": "${role_offline-access}",
        "composite": false,
        "clientRole": false,
        "containerId": "heroes"
}]
```


### DELETE Delete realm-level role mappings to the user [SAT] <a name="18383acc-d890-4000-8d1e-db55ab989a00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/role-mappings/realm`

Delete realm-level role mappings to the user

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
[{
        "name": "offline_access_2",
        "description": "${role_offline-access}",
        "composite": false,
        "clientRole": false,
        "containerId": "heroes"
}]
```


### GET Get realm-level roles that can be mapped [SAT] <a name="18383acc-d890-4000-844b-028f8ba82300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/role-mappings/realm/available`

Get realm-level roles that can be mapped

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get effective realm-level roles that can be mapped [SAT] <a name="18383acc-d890-4000-8ca0-e90bea68f400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/role-mappings/realm/composite`

Get effective realm-level role mappings This will recurse all composite roles to get the result

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

## Roles <a name="18383acc-d890-4000-831f-d617e873ca00"></a>



### GET Get all roles for the realm or client [SAT] <a name="18383acc-d890-4000-8bec-b348a7171700"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/roles`

Get all roles for the realm or client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Create a new role for the realm or client [SAT] <a name="18383acc-d8a0-4000-89b4-48228e520d00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/roles`

Create a new role for the realm or client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
        "name": "Strong",
        "composite": false,
        "clientRole": true,
        "containerId": "5725d549-faac-4a30-bab3-7b8370c19ce3"
    }
```


### GET Get a role by name [SAT] <a name="18383acc-d8a0-4000-83f8-0cc341ed0e00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/roles/Sneaky`

Get a role by name

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update a role by name [SAT] <a name="18383acc-d8a0-4000-8722-0e1adc9fbb00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/roles/Sneaky`

Update a role by name

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "647ba3cc-5d4d-4a5a-a67f-ed594f43a5b6",
    "name": "Sneaky",
    "composite": false,
    "clientRole": true,
    "containerId": "5725d549-faac-4a30-bab3-7b8370c19ce3",
    "attributes": {}
}
```


### DELETE Delete a role by name [SAT] <a name="18383acc-d8a0-4000-8832-c179d1839900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/roles/Sneaky`

Delete a role by name

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get a role by name composite [SAT] <a name="18383acc-d8b0-4000-8820-d08e6030ce00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/roles/Sneaky/composites`

Get a role by name

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Update a role by name composite [SAT] <a name="18383acc-d8b0-4000-8543-696aa2f12c00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/roles/Sneaky/composites`

Update a role by name

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
[{
    "name": "Sneaky-sub",
    "composite": false,
    "clientRole": true,
    "containerId": "647ba3cc-5d4d-4a5a-a67f-ed594f43a5b6",
    "attributes": {},
    "description": "sub comp"
}]
```


### DELETE Delete a role by name composite [SAT] <a name="18383acc-d8b0-4000-80d2-4b9b63e99e00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/roles/Sneaky/composites`

Remove roles from the roleâ€™s composite

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
[{
    "name": "Sneaky-sub",
    "composite": false,
    "clientRole": true,
    "containerId": "647ba3cc-5d4d-4a5a-a67f-ed594f43a5b6",
    "attributes": {},
    "description": "sub comp"
}]
```


### GET Get an app-level roles for specified app role's composite [SAT] <a name="18383acc-d8b0-4000-80b9-e34a5186e600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/roles/Sneaky/composites/clients/{{clientId}}`

An app-level roles for the specified app for the roleâ€™s composite

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get realm-level roles of the roleâ€™s composite [SAT] <a name="18383acc-d8c0-4000-81ab-1e03816dce00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/roles/Sneaky/composites/realm`

Get realm-level roles of the roleâ€™s composite

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Return List of Groups that have the specified role name [SAT] <a name="18383acc-d8c0-4000-83ef-9ba5faccca00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/roles/Sneaky/groups`

Return List of Groups that have the specified role name

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Return initialized auth permissions [SAT] <a name="18383acc-d8c0-4000-8301-1e428b358c00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/roles/Sneaky/management/permissions`

Return object stating whether role Authoirzation permissions have been initialized or not and a reference

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update initialized auth permissions [SAT] <a name="18383acc-d8d0-4000-836a-c2c7088eaf00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/roles/Sneaky/management/permissions`



**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"enabled": false
}
```


### GET Return List of Users that have the specified role name [SAT] <a name="18383acc-d8d0-4000-8a73-e154307bc900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/roles/Sneaky/users`

Return List of Users that have the specified role name

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get all roles for the realm or client [SAT] <a name="18383acc-d8d0-4000-8d8f-fec92db3a800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles`

Get all roles for the realm or client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Create a new role for the realm or client [SAT] <a name="18383acc-d8e0-4000-8d18-b795c957eb00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles`

Create a new role for the realm or client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
        "name": "Fighter",
        "composite": false,
        "clientRole": false,
        "containerId": "heroes"
    }
```


### GET Get a role by name[SAT] <a name="18383acc-d8e0-4000-83d1-38c68ce3a500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles/{{roleName}}`

Get a role by name

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Delete a role by name[SAT] <a name="18383acc-d8e0-4000-843e-74d5eff9c500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles/{{roleName}}`

Delete a role by name

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update a role by name[SAT] <a name="18383acc-d8e0-4000-8932-e13dbb5db000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles/{{roleName}}`

Update a role by name

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "ea522e2b-1e8f-42f6-9cc6-981fd5dd2114",
    "name": "Investigator",
    "composite": false,
    "clientRole": false,
    "containerId": "heroes",
    "attributes": {}
}
```


### POST Add a composite to the role [SAT] <a name="18383acc-d8e0-4000-8fbf-aa6566721200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles/{{roleName}}/composites`

Add a composite to the role


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
[
   {
    "name": "Sub-Investigator",
    "composite": false,
    "clientRole": false,
    "containerId": "Investigator",
    "description": "desc"
	}
]
```


### DELETE Delete a composite to the role [SAT] <a name="18383acc-d8f0-4000-846a-cde5cf0bf000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles/{{roleName}}/composites`

Delete a composite to the role


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "name": "Sub-Investigator",
    "composite": false,
    "clientRole": false,
    "containerId": "Investigator",
    "attributes": {}
}
```


### GET Get a composite to the role [SAT] <a name="18383acc-d8f0-4000-88e0-01e66ac71a00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles/{{roleName}}/composites`

Get a composite to the role


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get an app-level roles for the specified app [SAT] <a name="18383acc-d8f0-4000-8515-31333ff6ef00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles/{{roleName}}/composites/clients/{{clientId}}`

An app-level roles for the specified app for the roleâ€™s composite

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get realm-level roles of the roleâ€™s composite [SAT] <a name="18383acc-d8f0-4000-85b9-b350990afc00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles/{{roleName}}/composites/realm`

Get realm-level roles of the roleâ€™s composite

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Return List of Groups that have the specified role name [SAT] <a name="18383acc-d900-4000-8a3a-3b752d728300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles/{{roleName}}/groups`

Return List of Groups that have the specified role name

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get Authoirzation permissions have been initialized [SAT] <a name="18383acc-d900-4000-8bd4-2d08af45dc00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles/{{roleName}}/management/permissions`

Return object stating whether role Authoirzation permissions have been initialized or not and a reference

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update Authoirzation permissions have been initialized [SAT] <a name="18383acc-d900-4000-8d2e-869981202300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles/{{roleName}}/management/permissions`

Return object stating whether role Authoirzation permissions have been initialized or not and a reference

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"enabled": false
}
```


### GET Return List of Users that have the specified role name [SAT] <a name="18383acc-d900-4000-811b-950fc27bc100"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles/{{roleName}}/users`

Return List of Users that have the specified role name


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

## Roles (by ID) <a name="18383acc-d910-4000-83e6-d9ffa798e600"></a>



### GET Get a specific roleâ€™s representation [SAT] <a name="18383acc-d910-4000-84a5-a0acb1da4500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles-by-id/{{roleId}}`

Get a specific roleâ€™s representation

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update a specific roleâ€™s representation [SAT]  Copy <a name="18383acc-d910-4000-8cd2-f35723134900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles-by-id/{{roleId}}`

Update a specific roleâ€™s representation

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "ea522e2b-1e8f-42f6-9cc6-981fd5dd2114",
    "name": "Investigator",
    "composite": false,
    "clientRole": false,
    "containerId": "heroes",
    "attributes": {}
}
```


### DELETE Update a specific roleâ€™s representation [SAT]  Copy Copy <a name="18383acc-d910-4000-8e24-21eca6ec5f00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles-by-id/{{roleId}}`

Update a specific roleâ€™s representation

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Make the role a composite role by associating some child roles [SAT] <a name="18383acc-d910-4000-84a9-f0acbe46df00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles-by-id/{{roleId}}/composites`

Make the role a composite role by associating some child roles

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "ea522e2b-1e8f-42f6-9cc6-981fd5dd2114",
    "name": "Investigator",
    "composite": false,
    "clientRole": false,
    "containerId": "heroes",
    "attributes": {}
}
```


### GET Get roleâ€™s children by providing the role is a composite [SAT] <a name="18383acc-d920-4000-8888-e6a40a654700"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles-by-id/{{roleId}}/composites`

Get roleâ€™s children Returns a set of roleâ€™s children provided the role is a composite.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Delete roleâ€™s children by providing the role is a composite [SAT] <a name="18383acc-d920-4000-8ea8-ab8513773e00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles-by-id/{{roleId}}/composites`

Delete roleâ€™s children Returns a set of roleâ€™s children provided the role is a composite.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "ea522e2b-1e8f-42f6-9cc6-981fd5dd2114",
    "name": "Investigator",
    "composite": false,
    "clientRole": false,
    "containerId": "heroes",
    "attributes": {}
}
```


### GET Get client-level roles for the client that are in the roleâ€™s composite [SAT] <a name="18383acc-d920-4000-8bd0-badbe1e9d200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles-by-id/{{roleId}}/composites/clients/{{clientId}}`

Get client-level roles for the client that are in the roleâ€™s composite

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get realm-level roles that are in the roleâ€™s composite [SAT] <a name="18383acc-d930-4000-8215-f3cedbc05d00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles-by-id/{{roleId}}/composites/realm`

Get realm-level roles that are in the roleâ€™s composite

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get role Authoirzation permissions  [SAT] <a name="18383acc-d930-4000-8069-76bd190c5f00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles-by-id/{{roleId}}/management/permissions`

Return object stating whether role Authoirzation permissions have been initialized or not and a reference

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Get role Authoirzation permissions  [SAT] Copy <a name="18383acc-d930-4000-8269-d90294972d00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/roles-by-id/{{roleId}}/management/permissions`

Return object stating whether role Authoirzation permissions have been initialized or not and a reference

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "enabled": false
}
```


## Scope Mappings <a name="18383acc-d930-4000-8919-87f632529200"></a>



### GET Get all scope mappings for the client [SAT] <a name="18383acc-d930-4000-851e-5edcdc0b2400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{realmClientScopeId}}/scope-mappings`

Get all scope mappings for the client

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Add client-level roles to the clientâ€™s scope [SAT] <a name="18383acc-d940-4000-8093-823928ba2200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{realmClientScopeId}}/scope-mappings/clients/{{clientId}}`

Add client-level roles to the clientâ€™s scope

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "ea522e2b-1e8f-42f6-9cc6-981fd5dd2114",
    "name": "Investigator",
    "composite": false,
    "clientRole": false,
    "containerId": "heroes",
    "attributes": {}
}
```


### GET Get the roles associated with a clientâ€™s scope Returns roles for the client  [SAT] <a name="18383acc-d940-4000-81d7-0228b5b81700"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{realmClientScopeId}}/scope-mappings/clients/{{clientId}}`

Get the roles associated with a clientâ€™s scope Returns roles for the client.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Get the roles associated with a clientâ€™s scope Returns roles for the client  [SAT] <a name="18383acc-d940-4000-827a-f5067ceb6b00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{realmClientScopeId}}/scope-mappings/clients/{{clientId}}`

Get the roles associated with a clientâ€™s scope Returns roles for the client.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "ea522e2b-1e8f-42f6-9cc6-981fd5dd2114",
    "name": "Investigator",
    "composite": false,
    "clientRole": false,
    "containerId": "heroes",
    "attributes": {}
}
```


### GET Get the roles of the client  [SAT] <a name="18383acc-d940-4000-8521-7bcd191a6b00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{realmClientScopeId}}/scope-mappings/clients/{{clientId}}/available`

The available client-level roles Returns the roles for the client that can be associated with the clientâ€™s scope

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get the  effective client roles  [SAT] <a name="18383acc-d950-4000-852c-ef64eec40600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{realmClientScopeId}}/scope-mappings/clients/{{clientId}}/composite`

Get effective client roles Returns the roles for the client that are associated with the clientâ€™s scope.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Add a set of realm-level roles to the clientâ€™s scope [SAT] <a name="18383acc-d950-4000-84f6-59e9f79a8f00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{realmClientScopeId}}/scope-mappings/realm`

Add a set of realm-level roles to the clientâ€™s scope

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "ea522e2b-1e8f-42f6-9cc6-981fd5dd2114",
    "name": "Investigator",
    "composite": false,
    "clientRole": false,
    "containerId": "heroes",
    "attributes": {}
}
```


### GET Get realm-level roles associated with the clientâ€™s scope [SAT] <a name="18383acc-d950-4000-8247-42473be84c00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{realmClientScopeId}}/scope-mappings/realm`

Get realm-level roles associated with the clientâ€™s scope

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Get realm-level roles associated with the clientâ€™s scope [SAT] <a name="18383acc-d950-4000-8373-f06b85d13a00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{realmClientScopeId}}/scope-mappings/realm`

Get realm-level roles associated with the clientâ€™s scope

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "ea522e2b-1e8f-42f6-9cc6-981fd5dd2114",
    "name": "Investigator",
    "composite": false,
    "clientRole": false,
    "containerId": "heroes",
    "attributes": {}
}
```


### GET Get realm-level roles that are available to attach to this clientâ€™s scope [SAT] <a name="18383acc-d960-4000-866a-e18ebca67100"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{realmClientScopeId}}/scope-mappings/realm/available`

Get realm-level roles that are available to attach to this clientâ€™s scope

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get  a comprehensive total view of realm-level roles associated with the client [SAT] <a name="18383acc-d960-4000-8e41-1af6b0133d00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/client-scopes/{{realmClientScopeId}}/scope-mappings/realm/composite`

Get effective realm-level roles associated with the clientâ€™s scope What this does is recurse any composite roles associated with the clientâ€™s scope and adds the roles to this lists.

The method is really to show a comprehensive total view of realm-level roles associated with the client.



**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get all scope mappings for the client  [SAT] <a name="18383acc-d960-4000-8f17-6d0e7924c000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/scope-mappings`

Get all scope mappings for the client



**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Add client-level roles to the clientâ€™s scope  [SAT] <a name="18383acc-d960-4000-8002-d502a944a500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/scope-mappings/clients/{{clientId}}`

Add client-level roles to the clientâ€™s scope



**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "ea522e2b-1e8f-42f6-9cc6-981fd5dd2114",
    "name": "Investigator",
    "composite": false,
    "clientRole": false,
    "containerId": "heroes",
    "attributes": {}
}
```


### DELETE Delete client-level roles to the clientâ€™s scope  [SAT] <a name="18383acc-d970-4000-8498-54971bd62200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/scope-mappings/clients/{{clientId}}`

Delete client-level roles to the clientâ€™s scope



**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "ea522e2b-1e8f-42f6-9cc6-981fd5dd2114",
    "name": "Investigator",
    "composite": false,
    "clientRole": false,
    "containerId": "heroes",
    "attributes": {}
}
```


### GET Get client-level roles to the clientâ€™s scope  [SAT] <a name="18383acc-d970-4000-8a69-827de6034800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/scope-mappings/clients/{{clientId}}`

Get the roles associated with a clientâ€™s scope Returns roles for the client.


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get available client-level roles to the clientâ€™s scope  [SAT] <a name="18383acc-d970-4000-8a14-6f49cb7db200"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/scope-mappings/clients/{{clientId}}/available`

The available client-level roles Returns the roles for the client that can be associated with the clientâ€™s scope

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get effective client-level roles to the clientâ€™s scope  [SAT] <a name="18383acc-d970-4000-85a9-bd8ba8a10700"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/scope-mappings/clients/{{clientId}}/composite`

Get effective client roles Returns the roles for the client that are associated with the clientâ€™s scope.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Add a set of realm-level roles to the clientâ€™s scope  [SAT] <a name="18383acc-d980-4000-88c8-478eeb252600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/scope-mappings/realm`

Add a set of realm-level roles to the clientâ€™s scope


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "ea522e2b-1e8f-42f6-9cc6-981fd5dd2114",
    "name": "Investigator2",
    "composite": false,
    "clientRole": false,
    "containerId": "heroes",
    "attributes": {}
}
```


### DELETE Delete a set of realm-level roles to the clientâ€™s scope  [SAT] <a name="18383acc-d980-4000-87ce-47b55f760500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/scope-mappings/realm`

Delete a set of realm-level roles to the clientâ€™s scope


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "ea522e2b-1e8f-42f6-9cc6-981fd5dd2114",
    "name": "Investigator2",
    "composite": false,
    "clientRole": false,
    "containerId": "heroes",
    "attributes": {}
}
```


### GET Get realm-level roles associated with the clientâ€™s scope  [SAT] <a name="18383acc-d980-4000-889e-608f30ce6c00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/scope-mappings/realm`

Get realm-level roles associated with the clientâ€™s scope

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get realm-level roles that are available to attach to this clientâ€™s scope  [SAT] <a name="18383acc-d980-4000-8ed0-20a300006600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/scope-mappings/realm/available`

Get realm-level roles that are available to attach to this clientâ€™s scope


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get effective realm-level roles that are available to attach to this clientâ€™s scope  [SAT] <a name="18383acc-d990-4000-8e12-f230b9627000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/clients/{{clientId}}/scope-mappings/realm/composite`

Get effective realm-level roles associated with the clientâ€™s scope What this does is recurse any composite roles associated with the clientâ€™s scope and adds the roles to this lists.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

## User Storage Provider <a name="18383acc-d990-4000-8455-f5e92e4e3000"></a>



### GET Display simple name of usage provider  [SAT] <a name="18383acc-d990-4000-8902-80a68b04bb00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/user-storage/{{userStorageId}}/name`

Need this for admin console to display simple name of provider when displaying user detail

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Remove imported users  [SAT] <a name="18383acc-d990-4000-8d6b-9f2079d98c00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/user-storage/{{userStorageId}}/remove-imported-users`

Remove imported users

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Trigger sync  [SAT] <a name="18383acc-d990-4000-87f7-48873caa6c00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/user-storage/{{userStorageId}}/sync`

Trigger sync of users Action can be "triggerFullSync" or "triggerChangedUsersSync"

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Unlink imported users from a storage provider  [SAT] <a name="18383acc-d9a0-4000-84a2-803c7ca5a900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/user-storage/{{userStorageId}}/unlink-users`

Unlink imported users from a storage provider

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Trigger sync to ldap mapper  [SAT] <a name="18383acc-d9a0-4000-880b-7ed6bd6f8c00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/user-storage/{{ldapParentId}}/mappers/{{ldapMapperId}}/sync`

Trigger sync of mapper data related to ldap mapper (roles, groups, â€¦â€‹) direction is "fedToKeycloak" or "keycloakToFed"

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

## Users <a name="18383acc-d9a0-4000-817a-e57ba63b8f00"></a>



### GET Get users  [SAT] <a name="18383acc-d9a0-4000-8596-20d9cf7f9800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users`

Get users Returns a list of users, filtered according to query parameters

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

**Example**  *Get users  [SAT]* <a name="18383acc-d9a0-4000-8596-20d9cf7f9800_example_0"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users`


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

**Example Response**


```json
[
    {
        "id": "5d2e6c0b-924e-4496-b619-d8b8947e38a4",
        "createdTimestamp": 1588880797165,
        "username": "batman",
        "enabled": true,
        "totp": false,
        "emailVerified": true,
        "firstName": "Bruce",
        "lastName": "Wayne",
        "email": "batman@bat.com",
        "disableableCredentialTypes": [],
        "requiredActions": [],
        "notBefore": 0,
        "access": {
            "manageGroupMembership": true,
            "view": true,
            "mapRoles": true,
            "impersonate": true,
            "manage": true
        }
    },
    {
        "id": "51ec35b0-909d-421e-a5a4-6ad230d341c3",
        "createdTimestamp": 1588881104954,
        "username": "spiderman",
        "enabled": true,
        "totp": false,
        "emailVerified": true,
        "firstName": "Peter",
        "lastName": "Parker",
        "email": "spidy@sense.com",
        "disableableCredentialTypes": [],
        "requiredActions": [],
        "notBefore": 0,
        "access": {
            "manageGroupMembership": true,
            "view": true,
            "mapRoles": true,
            "impersonate": true,
            "manage": true
        }
    },
    {
        "id": "56f6c53f-5150-4b42-9757-4c3dd4e7d947",
        "createdTimestamp": 1588881160516,
        "username": "superman",
        "enabled": true,
        "totp": false,
        "emailVerified": true,
        "firstName": "Clark",
        "lastName": "Kent",
        "email": "superman@kael.com",
        "disableableCredentialTypes": [],
        "requiredActions": [],
        "notBefore": 0,
        "access": {
            "manageGroupMembership": true,
            "view": true,
            "mapRoles": true,
            "impersonate": true,
            "manage": true
        }
    },
    {
        "id": "1c4f1960-8817-4108-8672-7b36ebd3372d",
        "createdTimestamp": 1588880747548,
        "username": "thor",
        "enabled": true,
        "totp": false,
        "emailVerified": true,
        "firstName": "Thor",
        "lastName": "Thunder",
        "email": "thor@god.com",
        "disableableCredentialTypes": [],
        "requiredActions": [],
        "notBefore": 0,
        "access": {
            "manageGroupMembership": true,
            "view": true,
            "mapRoles": true,
            "impersonate": true,
            "manage": true
        }
    }
]
```


### POST Create user [SAT] <a name="18383acc-d9b0-4000-8bcd-449e43069600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users`

Create a new user Username must be unique.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
        "createdTimestamp": 1588880747548,
        "username": "Strange",
        "enabled": true,
        "totp": false,
        "emailVerified": true,
        "firstName": "Stephen",
        "lastName": "Strange",
        "email": "drstranger@marvel.com",
        "disableableCredentialTypes": [],
        "requiredActions": [],
        "notBefore": 0,
        "access": {
            "manageGroupMembership": true,
            "view": true,
            "mapRoles": true,
            "impersonate": true,
            "manage": true
        },
        "realmRoles": [	"mb-user" ]
    }
```


### GET Returns the number of users that match the given criteria [SAT] <a name="18383acc-d9b0-4000-89bf-094fc8d44e00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/count`

It can be called in three different ways. 1. Donâ€™t specify any criteria and pass {@code null}. The number of all users within that realm will be returned. <p> 2. If {@code search} is specified other criteria such as {@code last} will be ignored even though you set them. The {@code search} string will be matched against the first and last name, the username and the email of a user. </p><p> 3. If {@code search} is unspecified but any of {@code last}, {@code first}, {@code email} or {@code username} those criteria are matched against their respective fields on a user entity. Combined with a logical and.</p>

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get representation of the user [SAT] <a name="18383acc-d9c0-4000-8db6-7a1f886dea00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}`

Get representation of the user

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

**Example**  *Get user [SAT]* <a name="18383acc-d9c0-4000-8db6-7a1f886dea00_example_0"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}`


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

**Example Response**


```json
{
    "id": "56f6c53f-5150-4b42-9757-4c3dd4e7d947",
    "createdTimestamp": 1588881160516,
    "username": "superman",
    "enabled": true,
    "totp": false,
    "emailVerified": true,
    "firstName": "Clark",
    "lastName": "Kent",
    "email": "superman@kael.com",
    "disableableCredentialTypes": [],
    "requiredActions": [],
    "federatedIdentities": [],
    "notBefore": 0,
    "access": {
        "manageGroupMembership": true,
        "view": true,
        "mapRoles": true,
        "impersonate": true,
        "manage": true
    }
}
```


### PUT Update the user [SAT] <a name="18383acc-d9c0-4000-85ac-8f234bfce900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}`

Update the user

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
    "id": "56f6c53f-5150-4b42-9757-4c3dd4e7d947",
    "createdTimestamp": 1588881160516,
    "username": "Superman",
    "enabled": true,
    "totp": false,
    "emailVerified": true,
    "firstName": "Clark",
    "lastName": "Kent",
    "email": "superman@kael.com",
    "disableableCredentialTypes": [],
    "requiredActions": [],
    "federatedIdentities": [],
    "notBefore": 0,
    "access": {
        "manageGroupMembership": true,
        "view": true,
        "mapRoles": true,
        "impersonate": true,
        "manage": true
    }
}
```


### DELETE Delete the user [SAT] <a name="18383acc-d9d0-4000-8889-30612782a300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}`

Delete the user

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Return credential types  [SAT] <a name="18383acc-d9d0-4000-82b1-205f29331b00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/configured-user-storage-credential-types`

Return credential types, which are provided by the user storage where user is stored

Returned values can contain for example "password", "otp" etc. This will always return empty list for "local" users, which are not backed by any user storage

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get consents granted by the user  [SAT] <a name="18383acc-d9d0-4000-85b5-8d5f1b30fb00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/consents`

Get consents granted by the user

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Delete consents granted by the user  [SAT] <a name="18383acc-d9d0-4000-8a71-721aebb93300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/consents/{{clientId}}`

Delete consents granted by the user

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get credentials  [SAT] <a name="18383acc-d9e0-4000-8cda-9b463cc7c600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/credentials`

Get credentials 

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

**Example**  *Get credentials [SAT]* <a name="18383acc-d9e0-4000-8cda-9b463cc7c600_example_0"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/credentials`


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

**Example Response**


```json
[
    {
        "id": "f5e75065-30a9-422b-a22b-8ba1fb1a9fb4",
        "type": "password",
        "createdDate": 1588881169980,
        "credentialData": "{\"hashIterations\":27500,\"algorithm\":\"pbkdf2-sha256\"}"
    }
]
```


### DELETE Remove a credential for a user  [SAT] <a name="18383acc-d9e0-4000-883e-009d2bd52e00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/credentials/{{credentialsId}}`

Remove a credential for a user

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Move a credential to a position behind another credential  [SAT] <a name="18383acc-d9f0-4000-881d-4e19f3af6500"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/credentials/{{credentialsId}}/moveAfter/{{newPreviousCredentialId}}`

Move a credential to a position behind another credential

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Move a credential to a first position in the credentials list of the user [SAT] <a name="18383acc-da00-4000-87c0-7bafc66a7100"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/credentials/{{credentialsId}}/moveToFirst`

Move a credential to a first position in the credentials list of the user

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Update a credential label for a user [SAT] <a name="18383acc-da00-4000-871d-35f1800f5100"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/credentials/{{credentialsId}}/userLabel`

Update a credential label for a user

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|text/plain|



**Request Body** `raw`


```json
"label"
```


### PUT Disable all credentials for a user of a specific type [SAT] <a name="18383acc-da00-4000-8ba1-3656f8f0cf00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/disable-credential-types`

Disable all credentials for a user of a specific type

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
[]
```


### PUT Send an update account email to the user [SAT] <a name="18383acc-da00-4000-81d2-4a1adc9fc200"></a>


`{{keycloak_url}}/auth/admin/realms/{{realm}}/users/{{userId}}/execute-actions-email`

Send a update account email to the user An email contains a link the user can click to perform a set of required actions.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
["UPDATE_PASSWORD"]
```


### PUT Deprecated: Reset password email [SAT] <a name="18383acc-da10-4000-8fe8-76cb361f7d00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/reset-password-email?client_id=Mb-kcng-app`

Reset password email (with only client ID)

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get social logins associated with the user [SAT] <a name="18383acc-da10-4000-8b6a-f28aa1928b00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/federated-identity`

Get social logins associated with the user

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Add a social login provider to the user [SAT] <a name="18383acc-da10-4000-8152-d62ba0a05300"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/federated-identity/{{socialProvider}}`

Add a social login provider to the user

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{
	"userId": "56f6c53f-5150-4b42-9757-4c3dd4e7d947",
	"userName": "superman"
}
```


### DELETE Remove a social login provider from user [SAT] <a name="18383acc-da10-4000-888a-85456549f000"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/federated-identity/{{socialProvider}}`

Remove a social login provider from user


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get groups [SAT] <a name="18383acc-da10-4000-8cbe-17cacc809400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/groups`

Get groups


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

**Example**  *Get groups [SAT] * <a name="18383acc-da10-4000-8cbe-17cacc809400_example_0"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/groups`


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

**Example Response**


```json
[
    {
        "id": "2043c1bb-cf4b-47e3-9e07-49384d7d857a",
        "name": "dc",
        "path": "/dc"
    }
]
```


### GET Get groups count [SAT] <a name="18383acc-da20-4000-832f-ab6e3677f100"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/groups/count`

Get groups count


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Add group [SAT] <a name="18383acc-da20-4000-8bed-ce88f8ebc800"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/groups/{{groupId}}`

Add group


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### DELETE Delete group [SAT] <a name="18383acc-da30-4000-8c1c-c309bd451900"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/groups/{{groupId}}`

Delete group


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### POST Impersonate the user [SAT] <a name="18383acc-da30-4000-86ea-73c236fb7100"></a>


`{{keycloak_url}}/auth/admin/realms/{{realm}}/users/{{userId}}/impersonation`

Impersonate the user


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

**Example**  *Impersonate the user [SAT] * <a name="18383acc-da30-4000-86ea-73c236fb7100_example_0"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/impersonation`


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

**Example Response**


```json
{
    "redirect": "http://127.0.0.1:8080/auth/realms/heroes/account/applications",
    "sameRealm": true
}
```


### POST Logout user [SAT] <a name="18383acc-da30-4000-893a-f8a7989a2d00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/logout`

Remove all user sessions associated with the user Also send notification to all clients that have an admin URL to invalidate the sessions for the particular user.


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get offline sessions associated with the user and client [SAT] <a name="18383acc-da30-4000-81a9-40dcf398a600"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/offline-sessions/{{clientId}}`

Get offline sessions associated with the user and client


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### PUT Set up a new password for the user [SAT] <a name="18383acc-da40-4000-8509-69db35abd300"></a>


`{{keycloak_url}}/auth/admin/realms/{{realm}}/users/{{userId}}/reset-password`

Set up a new password for the user.


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body** `raw`


```json
{"type":"password","value":"test","temporary":false}
```


### PUT Send an email-verification email  [SAT] <a name="18383acc-da40-4000-8d3c-2a7338024b00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/send-verify-email`

Send an email-verification email to the user An email contains a link the user can click to verify their email address.

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

### GET Get sessions associated with the user  [SAT] <a name="18383acc-da40-4000-8df8-964b9ba3f400"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/sessions`

Get sessions associated with the user

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

**Example**  *Get sessions associated with the user  [SAT]* <a name="18383acc-da40-4000-8df8-964b9ba3f400_example_0"></a>


`{{keycloak_url}}/admin/realms/{{realm}}/users/{{userId}}/sessions`


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

**Example Response**


```json
[
    {
        "id": "f935a8cf-6960-487f-abd2-679ff9d74e0f",
        "username": "superman",
        "userId": "56f6c53f-5150-4b42-9757-4c3dd4e7d947",
        "ipAddress": "172.17.0.1",
        "start": 1589141601000,
        "lastAccess": 1589141601000,
        "clients": {}
    }
]
```


## Root <a name="18383acc-da50-4000-8720-402fc9f8ec00"></a>



### GET Get all  [SAT] <a name="18383acc-da50-4000-84bc-10fcc987ea00"></a>


`{{keycloak_url}}/admin/realms/{{realm}}`

Get themes, social providers, auth providers, and event listeners available on this server

**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

**Example**  *Get sessions associated with the user  [SAT] Copy* <a name="18383acc-da50-4000-84bc-10fcc987ea00_example_0"></a>


`{{keycloak_url}}/admin/realms/{{realm}}`


**Request Headers**


|Key|Value|
| --- | --- |
|Content-Type|application/json|



**Request Body**

N/A

**Example Response**


```json
{
    "id": "heroes",
    "realm": "heroes",
    "notBefore": 1589105644,
    "revokeRefreshToken": false,
    "refreshTokenMaxReuse": 0,
    "accessTokenLifespan": 300,
    "accessTokenLifespanForImplicitFlow": 900,
    "ssoSessionIdleTimeout": 1800,
    "ssoSessionMaxLifespan": 36000,
    "ssoSessionIdleTimeoutRememberMe": 0,
    "ssoSessionMaxLifespanRememberMe": 0,
    "offlineSessionIdleTimeout": 2592000,
    "offlineSessionMaxLifespanEnabled": false,
    "offlineSessionMaxLifespan": 5184000,
    "clientSessionIdleTimeout": 0,
    "clientSessionMaxLifespan": 0,
    "accessCodeLifespan": 60,
    "accessCodeLifespanUserAction": 300,
    "accessCodeLifespanLogin": 1800,
    "actionTokenGeneratedByAdminLifespan": 43200,
    "actionTokenGeneratedByUserLifespan": 300,
    "enabled": true,
    "sslRequired": "external",
    "registrationAllowed": false,
    "registrationEmailAsUsername": false,
    "rememberMe": false,
    "verifyEmail": false,
    "loginWithEmailAllowed": true,
    "duplicateEmailsAllowed": false,
    "resetPasswordAllowed": false,
    "editUsernameAllowed": false,
    "bruteForceProtected": false,
    "permanentLockout": false,
    "maxFailureWaitSeconds": 900,
    "minimumQuickLoginWaitSeconds": 60,
    "waitIncrementSeconds": 60,
    "quickLoginCheckMilliSeconds": 1000,
    "maxDeltaTimeSeconds": 43200,
    "failureFactor": 30,
    "defaultRoles": [
        "offline_access",
        "uma_authorization"
    ],
    "requiredCredentials": [
        "password"
    ],
    "otpPolicyType": "totp",
    "otpPolicyAlgorithm": "HmacSHA1",
    "otpPolicyInitialCounter": 0,
    "otpPolicyDigits": 6,
    "otpPolicyLookAheadWindow": 1,
    "otpPolicyPeriod": 30,
    "otpSupportedApplications": [
        "FreeOTP",
        "Google Authenticator"
    ],
    "webAuthnPolicyRpEntityName": "keycloak",
    "webAuthnPolicySignatureAlgorithms": [
        "ES256"
    ],
    "webAuthnPolicyRpId": "",
    "webAuthnPolicyAttestationConveyancePreference": "not specified",
    "webAuthnPolicyAuthenticatorAttachment": "not specified",
    "webAuthnPolicyRequireResidentKey": "not specified",
    "webAuthnPolicyUserVerificationRequirement": "not specified",
    "webAuthnPolicyCreateTimeout": 0,
    "webAuthnPolicyAvoidSameAuthenticatorRegister": false,
    "webAuthnPolicyAcceptableAaguids": [],
    "webAuthnPolicyPasswordlessRpEntityName": "keycloak",
    "webAuthnPolicyPasswordlessSignatureAlgorithms": [
        "ES256"
    ],
    "webAuthnPolicyPasswordlessRpId": "",
    "webAuthnPolicyPasswordlessAttestationConveyancePreference": "not specified",
    "webAuthnPolicyPasswordlessAuthenticatorAttachment": "not specified",
    "webAuthnPolicyPasswordlessRequireResidentKey": "not specified",
    "webAuthnPolicyPasswordlessUserVerificationRequirement": "not specified",
    "webAuthnPolicyPasswordlessCreateTimeout": 0,
    "webAuthnPolicyPasswordlessAvoidSameAuthenticatorRegister": false,
    "webAuthnPolicyPasswordlessAcceptableAaguids": [],
    "browserSecurityHeaders": {
        "contentSecurityPolicyReportOnly": "",
        "xContentTypeOptions": "nosniff",
        "xRobotsTag": "none",
        "xFrameOptions": "SAMEORIGIN",
        "contentSecurityPolicy": "frame-src 'self'; frame-ancestors 'self'; object-src 'none';",
        "xXSSProtection": "1; mode=block",
        "strictTransportSecurity": "max-age=31536000; includeSubDomains"
    },
    "smtpServer": {},
    "eventsEnabled": false,
    "eventsListeners": [
        "jboss-logging"
    ],
    "enabledEventTypes": [],
    "adminEventsEnabled": false,
    "adminEventsDetailsEnabled": false,
    "identityProviders": [
        {
            "alias": "keycloak-oidc",
            "internalId": "d79d0d65-8ee1-47f0-8611-f9e6eea71f20",
            "providerId": "keycloak-oidc",
            "enabled": true,
            "updateProfileFirstLoginMode": "on",
            "trustEmail": false,
            "storeToken": false,
            "addReadTokenRoleOnCreate": false,
            "authenticateByDefault": false,
            "linkOnly": false,
            "firstBrokerLoginFlowAlias": "first broker login",
            "config": {
                "clientId": "ssss",
                "tokenUrl": "http://localhost",
                "authorizationUrl": "http://localhost",
                "clientAuthMethod": "client_secret_basic",
                "syncMode": "IMPORT",
                "clientSecret": "assaasa",
                "useJwksUrl": "true"
            }
        },
        {
            "alias": "keycloak-oidc-2",
            "internalId": "7cf3fd74-8d3a-4c8d-b651-fcc885df8a31",
            "providerId": "keycloak-oidc",
            "enabled": true,
            "updateProfileFirstLoginMode": "on",
            "trustEmail": false,
            "storeToken": false,
            "addReadTokenRoleOnCreate": false,
            "authenticateByDefault": false,
            "linkOnly": false,
            "firstBrokerLoginFlowAlias": "first broker login",
            "config": {}
        }
    ],
    "identityProviderMappers": [
        {
            "id": "42c7b62d-4383-42c9-a8a0-65519e2c2543",
            "name": "test-mapper",
            "identityProviderAlias": "keycloak-oidc2",
            "identityProviderMapper": "keycloak-oidc",
            "config": {}
        },
        {
            "id": "ea65c956-24c7-4587-8fe7-c07222e3485d",
            "name": "test",
            "identityProviderAlias": "keycloak-oidc-2",
            "identityProviderMapper": "hardcoded-user-session-attribute-idp-mapper",
            "config": {
                "syncMode": "INHERIT"
            }
        }
    ],
    "internationalizationEnabled": false,
    "supportedLocales": [],
    "browserFlow": "browser",
    "registrationFlow": "registration",
    "directGrantFlow": "direct grant",
    "resetCredentialsFlow": "reset credentials",
    "clientAuthenticationFlow": "clients",
    "dockerAuthenticationFlow": "docker auth",
    "attributes": {},
    "userManagedAccessAllowed": false
}
```

