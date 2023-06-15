Test Cases for maxBuildQuantity

1. Retrieve Maximum Build Quantity
   - Description: Verify that the API returns the maximum build quantity for a specific weapon.
   - Steps:
     - Send a GET request to the "/api/weapon/:id/maxBuildQuantity" endpoint, replacing ":id" with a valid weapon ID.
     - Check the response status code.
     - Verify that the response body contains the correct maximum build quantity value.


2. Invalid Weapon ID
   - Description: Verify that the API handles requests with an invalid weapon ID or  or any negative value.
   - Steps:
     - Send a GET request to the "/api/weapon/:id/maxBuildQuantity" endpoint, replacing ":id" with an invalid or non-existent weapon ID.
     - Check the response status code.
     - Verify that the response body contains an appropriate error message or indication that the weapon ID is invalid.


We can further expand the test cases based on the specific requirements, including additional boundary tests, edge cases, and any validation or business rules applicable to the endpoint.


