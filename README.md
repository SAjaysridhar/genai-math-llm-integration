## Integration of a Mathematical Calulations with a Chat Completion System using LLM Function-Calling

### AIM:
To design and implement a Python function for calculating the volume of a cylinder, integrate it with a chat completion system utilizing the function-calling feature of a large language model (LLM).

### PROBLEM STATEMENT:

### DESIGN STEPS:

#### STEP 1:
Load environment variables and set up the OpenAI API key for authentication.
#### STEP 2:
 Implement cal_cylinder_vol(radius, height), which computes and returns the volume in JSON format.
#### STEP 3:
 Send a user’s request to the OpenAI chat model (ChatCompletion.create) along with function metadata.
### PROGRAM:
```
import json
import math

# Function to calculate cylinder volume
def calculate_cylinder_volume(radius: float, height: float) -> dict:
    volume = math.pi * (radius ** 2) * height
    return {"radius": radius, "height": height, "volume": volume}

# Simulated "LLM function call" response
user_message = "What is the volume of a cylinder with radius 5 cm and height 10 cm?"

# Pretend the LLM decided to call our function
function_call = {
    "name": "calculate_cylinder_volume",
    "arguments": json.dumps({"radius": 20, "height": 40})
}

# Extract arguments and call Python function
arguments = json.loads(function_call["arguments"])
result = calculate_cylinder_volume(**arguments)

# Simulated AI natural language reply
print("AI Response: The volume of the cylinder is approximately {:.2f} cubic units.".format(result["volume"]))
```
### OUTPUT:

<img width="1343" height="721" alt="Screenshot 2025-09-26 101811" src="https://github.com/user-attachments/assets/f7c21ef2-9a1c-45d1-a9f9-6641017a8ccb" />


### RESULT:
:The code successfully enables LLM-driven cylinder volume calculation via function calling.
