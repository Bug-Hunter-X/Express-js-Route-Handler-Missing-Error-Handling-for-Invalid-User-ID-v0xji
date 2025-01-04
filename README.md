# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, the `/users/:id` route fails to handle cases where `:id` is not a valid number.

The `bug.js` file shows the erroneous code.  The `bugSolution.js` file provides a corrected version that includes robust error handling.

## Problem
The original code attempts to parse the `userId` from the request parameters as an integer using `parseInt()`. If the `userId` is not a number (e.g., a string or null), `parseInt()` will return `NaN`. This causes the `users.find()` method to fail silently, potentially leading to unhandled exceptions or unexpected behavior, including server crashes.

## Solution
The corrected code adds explicit checks to validate the `userId` before attempting to parse it and use it in the database query.  If the `userId` is invalid, an appropriate error response is sent to the client.  This prevents server crashes and provides better feedback to the user.