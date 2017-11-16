#WORK IN PROGRESS

# HyperVerge Secure - Face Recognition IAM API Documentation

## Overview

This documentation describes Face Recognition IAM API v1. If you have any queries please contact support.

1. General
2. Entities
1. Parameters
1. Root Endpoint
1. Authentication and Authorization
1. Media Types
3. Supported Endpoints
3. Supported kyc_types 
2. Optional Parameters
<!-- 3. API wrappers and sample code snippets (Beta) -->

## General 
We recommend using HTTPS for all API access. All responses will be in JSON format, and all image uploads are to be performed as form-data (POST request). APIs without image uploads use application/json. Each individual API is explained in detail in the following section.


## Entities
There are 3 types of entities in this system. 

1. User
2. Group
3. Tenant 

##### 1. User
When an organization registers, an `admin user` is generated and credentials are provided to the organization's PoC, along with the `tenantId`. Using this more users can be registered into the system. Any person registered into a tenant is by default a `user`. Further, the user can be made an `admin` or `groupAdmin`(discussed in 2.); these `roles` are assigned to the `user` to allow different levels of access to the system. `admin` and `groupAdmin` are allowed to create and register users. Similarly, the `admin` can re-register a user at a later time and also give the `user` the ability to re-add more of his/her faces at a later stage.

##### 2. Group
A `group` can represent a team or site or location or building or any other collection of people. While the `user` is used to authenticate a person, `group` is used for authorization and access. For instance, only `users` added to group `lab` would be allowed into a 'lab', in which case a person is authenticated as a user and then checked if he should be provided access to the 'lab' based on whether he/she is present in the group `lab`. The `groupAdmin` are the gate keepers to the group. They have the ability to provide access to any `user` or revoke as well. `groups` and `groupAdmin` are created by `admin`.

##### 3. Tenant
All groups and users come under a single tenant. The tenant refers to the organization that is being registered on the platform. The tenant is created by the support team at HyperVerge or one of its partners. The `admin` are the gatekeepers to the organization. On creation, an `tenantId` is generated and would be shared.
<br>

---

#### User Privileges
There are 3 types of user roles in the system: `admin`, `groupAdmin` and a normal `user`. The privileges that each type of user can exercise are mentioned below:
 
##### Admin
Apart from everything that a Group Admin can do, an Admin user of the system can:<br>

* Create or delete a group
* Make a user an admin for the organization
* Delete a user
 
##### Group Admin
Apart from everything that a normal user can do, a Group Admin user of the system can:<br>

* Create and register a user
* Add a user to the group or remove user from group
* Make a user a group admin to the group

##### Normal User
A normal user of the system can:<br>

* Edit his/her details
* Add or remove his/her faces
<br>



## Authentication
All API calls need an `tenantId` and `tenantKey` to be sent with the header for authentication. The `tenantId` is used for billing. 
<br>


## Authorization
All API calls requiring authorization need a `token` to be sent with the header. The `token` would be generated by the system as a response to valid credentials or face verfication. The `token` can be obtained by authenticating with the username and OTP. All API calls made by an organization additionally need the `tenantId`
<br>

## Parameters
All optional and compulsory parameters are passed as part of the request body.

## Root Endpoint
A `GET` request can be issued to the root endpoint to check for successful connection : 

	 curl https://iam.hyperverge.co/v1 

The `plain/text` reponse of `"AoK!"` should be received.

## Supported APIs
- user
 	- [/user/enroll](api/user/enroll.md)
 	- [/user/create](api/user/create.md)
 	- [/user/auth](api/user/auth.md)
 	- [/user/faceauth](api/user/faceauth.md)
 	- [/user/remove](api/user/remove.md)
 	- [/user/get](api/user/get.md)
 	- [/user/edit](api/user/edit.md)
 	- [/user/addFace](api/user/addFace.md)
 	- [/user/removeFace](api/user/removeFace.md)
	- [/user/role](api/user/role.md)
 	- [/user/getOTP](api/user/getOTP.md)
- group
 - [/group/create](api/group/create.md)
 - [/group/addUser](api/group/addUser.md)
 - [/group/get](api/group/get.md)
 - [/group/remove](api/group/remove.md)
 - [/group/edit](api/group/edit.md)
 - [/group/userRole](api/group/userRole.md)
 - [/group/list](api/group/list.md)
 - [/group/listUsers](api/group/listUsers.md)
 - [/group/removeUser](api/group/removeUser.md)
- image
 - [image/recognize](api/image/recognize.md)
 - [image/verify](api/image/verify.md)

