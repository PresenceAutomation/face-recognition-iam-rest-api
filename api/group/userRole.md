## /group/userRole

Change the role of the user in the group to either "user" or "groupAdmin"

* **URL** : `/group/userRole`
  
* **Method:** `POST`

* **Header**
	
	- content-type : 'application/json'
	- tenantid 
	- tenantkey
	- token
	
* **Request Body**

	- groupId
	- userId
	- groupRole
	  
* **Success Response:**

  * **Code:** 200 <br />
  * Schema : 
		
		```	
		{
		  "status": "success",
		  "statusCode": "200"
		}
		```
	

* **Sample Call:**

   	
    	curl --request POST \
  			  --url 'https://in.secure.hyperverge.co/iam/v1/group/userRole' \
            --header 'content-type: application/json' \
            --header 'tenantid: {{tenantid}}' \
            --header 'tenantkey: {{tenantkey}}' \
            --header 'token: {{token}}' \
            --data '{"groupId":"0CwUv4L","userId":"+910123456789","groupRole":"user"}'
    	
    	
