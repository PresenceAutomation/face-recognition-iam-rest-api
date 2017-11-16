## /group/list

List all groups in the tenantId

* **URL** : `/group/list`
  
* **Method:** `POST`

* **Header**
	
	- content-type : 'application/json'
	- tenantid 
	- tenantkey
	- token
	
* **Request Body**
	Empty	  
* **Success Response:**

  * **Code:** 200 <br />
  * Schema : 
		
		```	
		{
		  "status": "success",
		  "statusCode": "200",
		  "result" : {
		  	"groups" : []
		  }
		}
		```
	

* **Sample Call:**

   	
    	curl --request POST \
  			  --url 'http://iam.hyperverge.co/v1/group/list' \
            --header 'content-type: application/json' \
            --header 'tenantid: {{tenantid}}' \
            --header 'tenantkey: {{tenantkey}}' \
            --header 'token: {{token}}' \
            --data '{"groupId":"0CwUv4L","userId":"+910123456789","groupRole":"user"}'
    	
    	
