# Properties.Listings


<div class="auth-wrapper">
    <button class="btn authorize unlocked">
        <span>Bearer Token</span>
    </button>
</div>


<div class="opwrapper">
    <div class="opblock opblock-post" >
        <div class="opblock-summary opblock-summary-post">
            <span class="opblock-summary-method">POST</span>
            <span class="opblock-summary-path">
                <a class="nostyle">
                    <span>/api/property/:propertyId/listings</span>
                </a>
            </span>
            <div class="opblock-summary-description">
                Get Authentication JWT (Bearer)
            </div>            
        </div>
    </div>
</div>


<span class="hide">Parameter</span> | <span class="hide">Description</span>
------------------------------------|--------------------------------------
`expand`<br><span class="label">optional</span>|You can optionally expand response on `?expand=channel,provider`


This endpoint will list all listings which belong to the master property record. 

For more information on what the difference between a property and a listing is, please refer to the general taxonomy description of a "Property" and "Listing" in the Lycan user guide, however, a short explaination is that:

- The Property always refers to the soruce of truth. It is a replica of the property which was imported and syncronized to Lycan from a third party platform. When the property is added to a "Collection" and the collection is distributed to a Channel, this creates the "Listing"
- The Listing is what Lycan distributes, not the Property. For this reason, every channel and "Listing" record can have different information for each channel. One channel can have different description, or different pricing because the Listings are inherantly capable of storing different data per channel. 



If a property is distributed to three different channels, then it would have three different Listings and be included in three different collections.


```shell
$ http GET "{{endpoint}}/api/property/0a1d7adc-8e41-4d2c-8abd-53cefd9bc6f7/listings?expand=channel,provider" \
           "Accept:application/json" \
           "Authorization:Bearer"  
```  


> <br />
> 
> Example Response of 4 listings which belong to a single property 

```json
{
    "page": 1,
    "limit": 20,
    "pages": 1,
    "total": 4,
    "_links": {
        "self": {
            "href": "/api/property/5a615d57-ad9d-49cf-9d52-526c5cef646b/listings?page=1&count=20"
        },
        "first": {
            "href": "/api/property/5a615d57-ad9d-49cf-9d52-526c5cef646b/listings?page=1&count=20"
        },
        "last": {
            "href": "/api/property/5a615d57-ad9d-49cf-9d52-526c5cef646b/listings?page=1&count=20"
        }
    },
    "_embedded": {
        "listings": [
            {
                "id": "211a1726-5085-4a2f-afe8-155f6d21072a",
                "createdAt": "2019-04-01T13:41:22+00:00",
                "updatedAt": "2019-04-11T12:34:16+00:00",
                "descriptiveName": "Homely Property",
                "isActive": true,
                "provider": {
                    "logo": "https://lycan.rentivo.com/bundles/procuro/img/logo_square_2.png",
                    "isValidCredentials": true,
                    "createdAt": "2018-04-10T09:58:32+00:00",
                    "nickname": "Fargolondra",
                    "discr": "providerprocuroauth",
                    "providerName": "Procuro"
                },
                "providerListingId": "222",
                "providerPublicURL": null,
                "discr": "listing",
                "arePoliciesValid": true,
                "staySynchronizeWithMaster": null,
                "providerMapping": [],
                "synchronizationMode": "SYNCHRONIZATION_MODE_FULL",
                "policiesError": null,
                "listingImportId": null,
                "listingStatus": null,
                "statusNotes": null,
                "channel": null
            },
            {
                "id": "6d6e7b72-ec91-4347-af5d-7adc745f2c04",
                "createdAt": "2019-01-15T11:16:16+00:00",
                "updatedAt": "2019-04-23T13:29:13+00:00",
                "descriptiveName": "Fargo Hill Apartment",
                "isActive": true,
                "provider": {
                    "logo": "https://lycan.rentivo.com/bundles/rentivo/img/logo_square.png",
                    "isValidCredentials": true,
                    "createdAt": "2018-04-10T10:28:44+00:00",
                    "nickname": "Fargo Rentivo Website",
                    "discr": "providerrentivoauth",
                    "client": "9P7ELuVlw21MtzvvlPweocdWtDtVtbqryveCDz3ajLHPf49y",
                    "username": null
                },
                "providerListingId": null,
                "providerPublicURL": null,
                "discr": "listing",
                "arePoliciesValid": true,
                "staySynchronizeWithMaster": null,
                "providerMapping": [],
                "synchronizationMode": "SYNCHRONIZATION_MODE_FULL",
                "policiesError": null,
                "listingImportId": null,
                "listingStatus": null,
                "statusNotes": null,
                "channel": {
                    "id": "dedb16f6-a3de-4eff-82c5-fabab20781f9",
                    "descriptiveName": "Fargo",
                    "provider": {
                        "logo": "https://lycan.rentivo.com/bundles/rentivo/img/logo_square.png",
                        "isValidCredentials": true,
                        "createdAt": "2018-04-10T10:28:44+00:00",
                        "nickname": "Fargo Rentivo Website",
                        "discr": "providerrentivoauth",
                        "client": "9P7ELuVlw21MtzvvlPweocdWtDtVtbqryveCDz3ajLHPf49y",
                        "username": null
                    },
                    "defaultSettings": null,
                    "baseUrl": null,
                    "defaultPriceCalculationStrategy": null,
                    "lodgingRateGenerationStrategy": [],
                    "pricingModel": null,
                    "discr": "brand",
                    "_links": {
                        "channels:listings": {
                            "href": "/api/channels/dedb16f6-a3de-4eff-82c5-fabab20781f9/listings"
                        }
                    }
                }
            },
            {
                "id": "8ec52b96-e727-498e-9fb0-0b81004a6e9d",
                "createdAt": "2019-01-15T11:16:18+00:00",
                "updatedAt": "2019-04-23T13:29:13+00:00",
                "descriptiveName": "Fargo Hill Apartment",
                "isActive": true,
                "provider": {
                    "logo": "https://lycan.rentivo.com/bundles/rentivo/img/logo_square.png",
                    "isValidCredentials": true,
                    "createdAt": "2019-01-06T11:03:46+00:00",
                    "nickname": "Test Love",
                    "discr": "providerrentivoauth",
                    "client": "n1GJN5Yej97IZca6bgM",
                    "username": null
                },
                "providerListingId": "186450",
                "providerPublicURL": null,
                "discr": "listing",
                "arePoliciesValid": true,
                "staySynchronizeWithMaster": null,
                "providerMapping": [],
                "synchronizationMode": "SYNCHRONIZATION_MODE_FULL",
                "policiesError": null,
                "listingImportId": null,
                "listingStatus": null,
                "statusNotes": null,
                "channel": {
                    "id": "ea73ccfe-4b33-4e28-a706-257bace9eb76",
                    "descriptiveName": "Fargo TEST",
                    "provider": {
                        "logo": "https://lycan.rentivo.com/bundles/rentivo/img/logo_square.png",
                        "isValidCredentials": true,
                        "createdAt": "2019-01-06T11:03:46+00:00",
                        "nickname": "Test Love",
                        "discr": "providerrentivoauth",
                        "client": "n1GJN5Yej97IZca6bgM",
                        "username": null
                    },
                    "defaultSettings": null,
                    "baseUrl": null,
                    "defaultPriceCalculationStrategy": "HIGHEST_RATE",
                    "lodgingRateGenerationStrategy": [],
                    "pricingModel": null,
                    "discr": "brand",
                    "_links": {
                        "channels:listings": {
                            "href": "/api/channels/ea73ccfe-4b33-4e28-a706-257bace9eb76/listings"
                        }
                    }
                }
            },
            {
                "id": "c40a364f-9f47-4a5f-a895-1752731b8420",
                "createdAt": "2019-04-18T12:01:26+00:00",
                "updatedAt": "2019-04-23T09:36:41+00:00",
                "descriptiveName": "Fargo Hill Apartment",
                "isActive": true,
                "provider": {
                    "logo": "https://lycan.rentivo.com/bundles/airbnb/img/logo_square.png",
                    "isValidCredentials": true,
                    "createdAt": "2019-01-29T00:24:21+00:00",
                    "nickname": "SANDBOX",
                    "discr": "providerairbnbauth",
                    "loginLink": "/partners/airbnb/oauth/connection-start?connectionId=98d3f7a",
                    "providerName": "Airbnb",
                    "baseUrl": null,
                    "client": null,
                    "accessToken": null,
                    "refreshToken": null,
                    "expiresAt": null,
                    "scope": null,
                    "testMode": null
                },
                "providerListingId": "555555555",
                "providerPublicURL": null,
                "discr": "listing",
                "arePoliciesValid": true,
                "staySynchronizeWithMaster": null,
                "providerMapping": [],
                "synchronizationMode": "SYNCHRONIZATION_MODE_FULL",
                "policiesError": null,
                "listingImportId": null,
                "listingStatus": null,
                "statusNotes": null,
                "channel": {
                    "id": "12f38c60-4fec-42da-9bc8-1f16a8b8e9df",
                    "descriptiveName": "asdasd",
                    "provider": {
                        "logo": "https://lycan.rentivo.com/bundles/airbnb/img/logo_square.png",
                        "isValidCredentials": true,
                        "createdAt": "2019-01-29T00:24:21+00:00",
                        "nickname": "CHRIS SANDBOX",
                        "discr": "providerairbnbauth",
                        "loginLink": "/partners/airbnb/oauth/connection-start?connectionId=98d3f7a",
                        "providerName": "Airbnb",
                        "baseUrl": null,
                        "client": null,
                        "accessToken": null,
                        "refreshToken": null,
                        "expiresAt": null,
                        "scope": null,
                        "testMode": null
                    },
                    "defaultSettings": {
                        "id": "f5ce5191-c5f6-4c0b-83a5-d198b673c272",
                        "bookingSource": null,
                        "descriptiveName": "(C) Booking Commissions Settings",
                        "logo": null,
                        "brandCompanyName": null,
                        "website": null,
                        "biography": null,
                        "phone": null,
                        "emails": []
                    },
                    "baseUrl": null,
                    "defaultPriceCalculationStrategy": "HIGHEST_RATE",
                    "lodgingRateGenerationStrategy": [
                        "WEEKLY_LOS_DISCOUNT_RULESET"
                    ],
                    "pricingModel": null,
                    "discr": "brand",
                    "_links": {
                        "channels:listings": {
                            "href": "/api/channels/12f38c60-4fec-42da-9bc8-1f16a8b8e9df/listings"
                        }
                    }
                }
            }
        ]
    }
}
 ``` 