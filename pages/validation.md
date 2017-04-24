Methods that take input will validate all parameters. Any parameter that fails validation will trigger an error response with status `HTTP 422`. The response body will be a JSON object that includes a message as well as a list of fields that failed validation.

**Example Validation Body:**

    {
      "message": "Validation error",
      "errors": [
        {
            "message": "Must be one of: candidate, prospect",
            "field": "type"
        }
      ]
    }
