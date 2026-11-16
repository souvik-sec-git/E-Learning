# Security-Testing-Playbook

API enable software systems and applications to communicate and share data.

API endpoints: These are locations where an API receives requests about a specific resource on its server.

1. Detect API endpoints

   a.
	   ex:   
   
	   GET /api/books HTTP/1.1  
   
	   Host: example.com  
   
	   here API is:  /api/books

   b. Lookout for javaScript files too - JS Link Finder BApp
   

3. how to interact with them
   
 	a. The input data the API processes.

	b. The types of requests the API accepts.(HTTP, media type)

	c. Rate limits and authentication mechanisms.



5. API are written in two types of format
   
	a. Human Readable(For devs in detailed explanations, ex, usage scenarios)

	b. Machine Readable(JSON or XML for automation)


7. Discovering API
	a. By browsing the applications
	b. By crawling the applications using burp scanner or manually by burps browser



9. If API resource endpoint is found, still we need to investigate the following paths.
   

11. To test documented API endpoints: a. Postman B. SoapUI
    

13. To Parse OpenAPI documentation using - OpenAPI Parser BApp
    

15. Supported HTTP Methods:
    
	a. GET

	b. POST

	c. DELETE

	d. PATCH

	e. OPTIONS (Retrieves information on the types of request methods that can be used on a resource.)


** also HTTP verb list can be used to cycle through range of methods  


9. supported content types: changing content types may make it vulnerable. ex - JSON to XML
    
	a. Content-Type (changing directly)

	b. Content type converter BApp

** lookout for:   

	a. errors  
   
	b. bypass flawed defenses  
   
	c. vulnerable to SQLi, due to change in content type as there is difference in processing the logic.  
   

10. Using intruder to find hidden endpoints

	for ex:

	PUT/api/user/update

** we can replace update with "add", "delete" etc based on intital recon


 

    
