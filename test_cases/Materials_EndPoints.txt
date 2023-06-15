Materials API Endpoint Test Cases:

1. GET /api/material
   
   a. Test Case : Retrieve All Materials
      - Description: Verify that the API returns all materials from the database.
      - Steps:
        - Send a GET request to the "/api/material" endpoint.
        - Check the response status code.
        - Verify that the response body contains an array of materials.

2. GET /api/material/:id
   
   a. Test Case : Retrieve Specific Material
      - Description: Verify that the API returns a specific material from the database.
      - Steps:
        - Send a GET request to the "/api/material/:id" endpoint, replacing ":id" with a valid material ID.
        - Check the response status code.
        - Verify that the response body contains the correct material information.
  

   b. Test Case : Retrieve Non-existent Material
      - Description: Verify that the API handles the case when the requested material ID does not exist or  or any negative value.
      - Steps:
        - Send a GET request to the "/api/material/:id" endpoint, replacing ":id" with a non-existent material ID.
        - Check the response status code.
        - Verify that the response body indicates that the material was not found.


3. PUT /api/material/:id
   
   a. Test Case : Update Material Power Level and Quantity
      - Description: Verify that the API updates the power level and quantity of a material and recalculates the power level of affected weapons.
      - Steps:
        - Send a PUT request to the "/api/material/:id" endpoint, replacing ":id" with a valid material ID.
        - Include the payload with the updated power level and quantity.
        - Check the response status code.
        - Verify that the response body contains the updated materials and affected weapons.


   b. Test Case : Update Non-existent Material
      - Description: Verify that the API handles the case when the requested material ID for update does not exist  or any negative value.
      - Steps:
        - Send a PUT request to the "/api/material/:id" endpoint, replacing ":id" with a non-existent material ID.
        - Include the payload with the updated power level and quantity.
        - Check the response status code.
        - Verify that the response body indicates that the material was not found.


  c. Test Case: Update Material with Negative Power Level and Quantity
  - Description: Verify that the API handles the case when attempting to update a material with negative power level and quantity.
      - Steps:
        - Send a PUT request to the "/api/material/{{material_id}}" endpoint, replacing "{{material_id}}" with a valid material ID.
        - Include the payload with the power level and quantity set to negative values (-100 and -70, respectively).
        - Check the response status code.
        - Verify that the response body contains the expected error message: "Power level and quantity must be positive."

4. DELETE /api/material/:id
  
   a. Test Case : Delete Material and Update Affected Weapons
      - Description: Verify that the API sets the deleted_at field of a specific material and its parent materials, and sets the status of affected weapons as broken.
      - Steps:
        - Send a DELETE request to the "/api/material/:id" endpoint, replacing ":id" with a valid material ID.
        - Check the response status code.
        - Verify that the response body contains the deleted materials and affected weapons.
  

   b. Test Case : Delete Non-existent Material
      - Description: Verify that the API handles the case when the requested material ID for deletion does not exist or any negative value.
      - Steps:
        - Send a DELETE request to the "/api/material/:id" endpoint, replacing ":id" with a non-existent material ID.
        - Check the response status code.
        - Verify that the response body indicates that the material was not found.
