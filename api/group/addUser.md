## /group/addUser

Add an existing user to an existing group.

* **URL** : `/group/addUser`
  
* **Method:** `POST`

* **Header**
	
	- content-type : 'application/json'
	- tenantid 
	- tenantkey
	- token
	
* **Request Body**

	- groupId
	- userId
	  
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
  			  --url 'http://iam.hyperverge.co/v1/user/getOTP' \
            --header 'content-type: application/json' \
            --header 'tenantid: {{tenantid}}' \
            --header 'tenantkey: {{tenantkey}}' \
            --header 'token: {{token}}' \
            --data '{"groupId":"facetestaccess","userId":"+910001231314"}'
    	
    	
