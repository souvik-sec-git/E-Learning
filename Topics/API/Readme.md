# Security-Testing-Playbook

API enable software systems and applications to communicate and share data.

API endpoints: These are locations where an API receives requests about a specific resource on its server.

1. Detect API endpoints:

   a.
	   ex:   
   
	   GET /api/books HTTP/1.1  
   
	   Host: example.com  
   
	   here API is:  /api/books

   b. Lookout for javaScript files too - JS Link Finder BApp
   

2. how to interact with them:
   
 	a. The input data the API processes.

	b. The types of requests the API accepts.(HTTP, media type)

	c. Rate limits and authentication mechanisms.



3. API are written in two types of format:
   
	a. Human Readable(For devs in detailed explanations, ex, usage scenarios)

	b. Machine Readable(JSON or XML for automation)


4. Discovering API:
   
	a. By browsing the applications

	b. By crawling the applications using burp scanner or manually by burps browser



** If API resource endpoint is found, still we need to investigate the following paths.
   

5. To test documented API endpoints:
   
    a. Postman
   
    B. SoapUI
    

6. To Parse OpenAPI documentation using - OpenAPI Parser BApp
    

7. Supported HTTP Methods:
    
	a. GET

	b. POST

	c. DELETE

	d. PATCH

	e. OPTIONS (Retrieves information on the types of request methods that can be used on a resource.)


** also HTTP verb list can be used to cycle through range of methods  


8. supported content types: changing content types may make it vulnerable. ex - JSON to XML
    
	a. Content-Type (changing directly)

	b. Content type converter BApp

** lookout for:   

	a. errors  
   
	b. bypass flawed defenses  
   
	c. vulnerable to SQLi, due to change in content type as there is difference in processing the logic.  
   

9. Using intruder to find hidden endpoints

	for ex:

	PUT/api/user/update

** we can replace update with "add", "delete" etc based on initial recon  

10. Mass assignment vulnerabilities/ auto-binding
    
    a. software frameworks automatically bind request parameters to fields on an internal object.
    
    b. never intended to be processed by devs.

ex request:  
a. PATCH /api/users/  

	{
	    "username": "wiener",
	    "email": "wiener@example.com",
	}  

b. GET /api/users/123  

	{
	    "id": 123,
	    "name": "John Doe",
	    "email": "john@example.com",
	    "isAdmin": "false"
	}

** here "isAdmin" is the hidden parameter, exploit it with burp  


11. Exploiting hidden parameters:
    
    a. Param miner BApp
    
    b. Content Discovery Tool

12. Preventing Vulnerabilities in API:
    
    a. Securing documentation, to be not publicly accessible.
    
    b. Ensuring documentation is kept up to date so that legitimate testers have full visibility of the API's attack surface.
    
    c. Appling an allowlist of permitted HTTP methods.
    
    d. Validating that the content type is expected for each request or response.
    
    e. Using generic error messages to avoid giving away information that may be useful for an attacker.
    
    f. Use protective measures on all versions of your API, not just the current production version.
    
	h. To prevent mass assignment vulnerabilities, allowlist the properties that can be updated by the user, and blocklist sensitive properties that shouldn't be updated by the user. 

	





 

    
