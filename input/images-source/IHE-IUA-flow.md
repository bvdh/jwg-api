@startuml

  participant AuthorizationClient as "Authorization Client"
  participant ResourceServer as "Resource Server"
  participant AuthorizationServer as "Authorization Server"

  AuthorizationClient -> AuthorizationServer: Get Authorization Metadata [ITI-103]

  group ITI-103 Get Authorization Metadata
    AuthorizationClient -> AuthorizationServer: Authorization Server Metadata Request
    AuthorizationClient <-- AuthorizationServer: Authorization Server Metadata Response
  end group

  group ITI-71 Get Access Token
    alt 
    else Client Credential
      AuthorizationClient -> AuthorizationServer: Get Access Token Request (<client-credentials>)
      AuthorizationClient <-- AuthorizationServer: Get Access Token Response (<access-token>)
    else Authorization Code 
      AuthorizationClient -> AuthorizationServer: REDIRECT(requested scopes, clientId)
      note over AuthorizationServer: login if needed
      AuthorizationServer -> AuthorizationClient: REDIRECT (<authorization-token>)
      AuthorizationClient -> AuthorizationServer: Get Access Token Request (<client credentials> + <authorization-code>)
      AuthorizationClient <-- AuthorizationServer: Get Access Token Respons (<access-token>) 
    end
  end group
  group ITI-72 Incorporate Access Token [ITI-72]
    AuthorizationClient -> ResourceServer: Resource Request(<access-token>)
    alt
    else validate token
    note over ResourceServer: validate token
    else introspect token
      group ITI-10 Introspection
        ResourceServer -> AuthorizationServer: introspect token (<access-token>)
        ResourceServer <-- AuthorizationServer: <token-claims>
      end group
    end
    AuthorizationClient <-- ResourceServer: Resource Response(<content>)
  end group
@enduml