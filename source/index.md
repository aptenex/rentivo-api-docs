---
title: Rentivo API Reference

language_tabs:
  - shell

includes:
  - authentication
  - pagination
  - object_expansion
  - properties
  - properties_listings

search: true
---

# Introduction

> Examples in this documentation are written using [httpie](https://github.com/jkbrzt/httpie)

> To install `httpie` on macOS or linux with (linuxwrapper) run `brew install httpie`



Lycan API Documentation

This section contains the technical documentation for Lycan. API Authentication is managed through two different authorization strategies. We have `Bearer` tokens which are keys that grant access to any resource which owns this token (These are JWT based). The second authorization solution is `ResourceKey` based, which is where as an owner of a resource, you can grant third party access. 

## Scope of Ownership/Visbility


This might sound obvious, but for the sake of clarity, when you authenticate with a token, you will be able to access only resource which are within the scope visibility for that key. Lycan has several different types of roles.

- Root Level
- Application Administrator (Installation of your own Lycan)
- User (Read and write access)
- Agent (Read only)

An application administrator will be able to perform all actions on all resources within their application. 
A user will be able to access only resources which they own, or resources which are shared with them. For example, if you are a collection owner, and you have invited five other user's to your "Collection" you will be able to view/update specific resources which are within your own collection. You will not be able to view other user's resources. 


## Multi-tenancy of Lycan environment


Lycan is a multi-tenanted application which many environments. Each environment is entirely isolated from each other, each with their own permissions, their own users and their own properties/distribution restrictions. The owner of the installation, which we call "Application Owner" on Lycan has full control over their environment and tenants (the users). This means that when you try and connect to a Lycan based API to get your Json Web Token (`Bearer`) you must also specify the `application_hash` which you are trying to access. If you do not know your hash, or have not been provided it, please contact support for this information. 



## Warning: Updating Nested Objects

When you fetch data from the API you will see that the object includes nested objects. For example, if you fetch a reservation, the API will return all payments and order items attached to that reservation.

<aside class='warning'>
 You must not send the same response back for an update. This is because Lycan will not fetch the respective object, and instead will ignore your ID that you supply and create a new entity in it's place. This will result in you wiping existing data and replacing it with new data, potentially creating new payments. 
</aside>

<img src="https://s3-eu-west-1.amazonaws.com/lycan-general/docs/VR4_095e.png" class="img-responsive" />


