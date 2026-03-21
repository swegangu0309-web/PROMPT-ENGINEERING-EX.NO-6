# Ex.No.6 Development of Python Code Compatible with Multiple AI Tools


# Register no. 21222305020
# Aim: Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights with Multiple AI Tools

#AI Tools Required: 

ChatGPT (GPT-5 or GPT-4) – for generating and explaining Python code.

Google Gemini / Bard – for comparing code logic and alternative API uses.

GitHub Copilot – for in-editor code suggestions and real-time debugging help.

Replit / Jupyter Notebook – for executing and testing AI-generated code.

Postman / RapidAPI – to explore and test API requests and responses.

# Explanation:
Experiment the persona pattern as a programmer for any specific applications related with your interesting area. 
Generate the outoput using more than one AI tool and based on the code generation analyse and discussing that. 

# Objective:

To design effective prompts that guide AI tools (like ChatGPT) to generate Python code, compare outputs from multiple APIs, and suggest meaningful insights — improving students’ ability to communicate coding needs to AI.

# Stage 1: Generate Python Code for Interacting with Multiple APIs

# Prompt:
Write a Python program that connects to two weather APIs — OpenWeatherMap and WeatherAPI. Fetch current temperature and humidity data for a given city, and print the results neatly.

# Output:
```

import requests

def get_openweather_data(city, api_key):
    url = f"https://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}&units=metric"
    data = requests.get(url).json()
    return data["main"]["temp"], data["main"]["humidity"]

def get_weatherapi_data(city, api_key):
    url = f"http://api.weatherapi.com/v1/current.json?key={api_key}&q={city}"
    data = requests.get(url).json()
    return data["current"]["temp_c"], data["current"]["humidity"]

city = "Delhi"
open_temp, open_hum = get_openweather_data(city, "your_openweather_key")
weather_temp, weather_hum = get_weatherapi_data(city, "your_weatherapi_key")

print(f"OpenWeatherMap - Temp: {open_temp}°C, Humidity: {open_hum}%")
print(f"WeatherAPI - Temp: {weather_temp}°C, Humidity: {weather_hum}%")

```

# AI Explanation:
The AI explained that this code uses the requests module to call two APIs, extract temperature and humidity, and display them. It also mentioned the need to replace API keys with valid ones.
  
# Stage 2: Compare Outputs from Different APIs
# Prompt:
Modify the previous code so that it compares the temperature and humidity values from both APIs and highlights the differences clearly

# Output:
```

temp_diff = abs(open_temp - weather_temp)
hum_diff = abs(open_hum - weather_hum)

print(f"Temperature difference: {temp_diff:.2f}°C")
print(f"Humidity difference: {hum_diff:.2f}%")

if temp_diff > 2:
    print("⚠️ Significant temperature variation between APIs.")
else:
    print("✅ Both APIs show similar weather data.")

```

# AI Explanation:
The AI added code to calculate absolute differences and print warnings if they exceed a threshold, helping identify inconsistencies between APIs.

# Stage 3: Suggest Insights or Next Steps
# Prompt:
Based on the compared weather data, suggest how the program could automatically choose the more reliable API result and display an average value.

# Output:

```

avg_temp = (open_temp + weather_temp) / 2
avg_hum = (open_hum + weather_hum) / 2

print(f"Average Temperature: {avg_temp:.2f}°C")
print(f"Average Humidity: {avg_hum:.2f}%")

if temp_diff > 5:
    print("Consider verifying API accuracy or checking API update times.")
else:
    print("Average values are reliable for further analysis.")

```

# AI Explanation:
The AI suggested computing averages and adding conditional logic to detect inconsistencies, improving data reliability.

# Reflection Note:
At first, my prompts were too short and unclear — the AI generated generic code. When I added specific details like:

1. API names

2. What kind of data to fetch

3. Expected output format

the results became much more accurate and useful.

I learned that good AI prompts must be detailed, structured, and goal-oriented — almost like giving instructions to a human assistant. In the future, I would refine prompts by including constraints (e.g., “use exception handling” or “display results in a table format”) for better quality output.

# Conclusion:

This exercise demonstrates that effective prompt design plays a key role in maximizing the usefulness of AI tools for project development. By learning to communicate clearly with AI systems, students can:

Save time in coding and debugging.

Understand how to integrate multiple APIs efficiently.

Derive meaningful insights automatically.

Ultimately, prompt engineering helps bridge the gap between human intent and AI-assisted coding execution, making the project workflow smoother and smarter.
