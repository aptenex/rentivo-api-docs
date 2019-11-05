# Authentication

The Rentivo Lycan API implements a JWT based authentication. Any requests which require authentication will need either a Bearer token or a ResourceKey token.   



## Bearer Token

You will use a `Bearer` JWT token if you have an account on Lycan, are an application owner, or manage your own collection. Typical use-cases for such API access would be to curate your properties, handle distribution to third party marketing sites and process reservation payments through a connected payment gateway.

### How do get a Bearer Token
1. Acquire a Bearer Token by exchanging  your user credentials against the auth endpoint
2. Use token in any requests  

### Who uses Bearer Tokens?

- Companies with their own Lycan Installation and would like to create their own website powered by Lycan
- Agencies who manage their own collection/inventory
- External Property Management Softwares
- Individual homeowners/agencies




## ResourceKey Token

You will use ` ResourceKey` if you are a third party who wishes to be supplied with inventory from a Lycan user. For example, if you are a meta-marketplace, or a cleaning-app, or a logistics management company, or a review company, your product may depend on getting access to specific resources from a Lycan user. For example, you may need access to a user's properties, or a user's booking information. In this scenario, you will use a resource key which grants you access limited to the specific resource collection. 

### How to get a ResourceKey Token
1. Receive your token from Rentivo support or via a partner that has supplied in the token directly
2. Use the ResourceKey in requests you send

### Who might use ResourceKey Tokens?

- Meta-marketplaces
- Third-party applications who wish to get property/reservation/booking information.
- Web agencies building websites for individual managers

<aside class='info'>
You can see which endpoints support `Bearer` and `ResourceKey` tokens on each endpoint.
</aside>
 

### How do I get my respective token?

If you are going use JWT `Bearer` authentication, you get your key by requesting a token from the authorization endpoint. See the "Get Authentication JWT (Bearer) section below. In order to get our token, you pass your username and password for Lycan. 

If you are going to use a `ResourceKey` based autentication, you will get your key from the company supplying you connectivity to their resources. For example, if you are wanting to receive inventory/booking information from an agent, they will supply you with the appropriate `ResourceKey`. 

Once you have either token, authentication against Lycan uses the same process. Whenever you send a request to Lycan, you must include your token in the `Authorization` prefixed with the type of token. For example:

## Bearer Token Auth

When sending a request which required authorization to Lycan, you must always send your corresponding token.

```shell
--header 'Authorization: Bearer {{token}}'
```

## ResourceKey Token Auth

You can see here we have a ResourceKey and as such use the Authorization: ResourceKey header attribute=>value pairing to authenticate.

```shell
--header 'Authorization: ResourceKey {{token}}'
```


## Authenticate Request


##### URL arguments


<div class="opwrapper">
    <div class="opblock opblock-post" >
        <div class="opblock-summary opblock-summary-post">
            <span class="opblock-summary-method">POST</span>
            <span class="opblock-summary-path">
                <a class="nostyle">
                    <span>/auth/token</span>
                </a>
            </span>
            <div class="opblock-summary-description">
                Get Authentication JWT (Bearer)
            </div>            
        </div>
    </div>
</div>


```shell
$ http --form POST http://symfony.test/app_dev.php/api/auth/token \
  "Accept:application/json" \
  "Content-Type:application/x-www-form-urlencoded" \  
  "cache-control:no-cache" \
  "_username=$username" \
  "_password=$password" \
  "application_hash=$application_hash"
```



> Example 200 Response (Trimmed for brevity)

```json
{
    "token": "ey23V9BRE1JTl9MWUNBTl9QUk9WSURFUl9"
}
```

> Example 401 Failed Authentication

```json
{"code":401,"message":"Bad credentials"} 
```

<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`_username`<br><span class="label notice">Required</span>|Your username
`_password`<br><span class="label notice">Required</span>|Your password
`application_hash`<br><span class="label notice">Required</span>|Your application hash

