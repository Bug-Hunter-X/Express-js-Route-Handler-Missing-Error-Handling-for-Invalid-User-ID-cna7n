# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input. Specifically, this example shows a route that retrieves a user by ID, but lacks proper error handling if the ID is not a valid integer.

## Bug

The `bug.js` file contains the erroneous code.  The route handler attempts to parse the `userId` as an integer using `parseInt()` without checking if the result is a valid integer. If `req.params.id` is not a valid integer (e.g., a string or NaN), `parseInt()` will return `NaN`, leading to a potential error or unexpected behavior.

## Solution

The `bugSolution.js` file provides the corrected code.  The solution includes error handling to check if `parseInt(userId)` returns a valid integer.  If not, it returns a 400 Bad Request error to the client.

This improved error handling makes the application more robust and less prone to crashes due to unexpected input.