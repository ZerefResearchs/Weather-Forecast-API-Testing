# Weather-Forecast-API-Testing

**Project Name:** Weather Forecast API Testing  
**API Under Test:** OpenWeather Current Weather Data API  
**Base URL:** `https://api.openweathermap.org/data/2.5/weather`  
**Tester:** Abhishek Singh Negi  
**Date:** October 2025  

---

### 1. Objective

To verify that the OpenWeather “Current Weather Data” API functions correctly, handles invalid requests gracefully, and returns accurate and complete weather information for different input parameters.

---

### 2. Scope

**In Scope:**

* `/weather` endpoint
* Query parameters: `q`, `lat`, `lon`, `appid`, `units`
* Functional and negative testing

**Out of Scope:**

* Other APIs (forecast, air pollution, historical data)
* Advanced performance or security testing

---

### 3. Tools Used

* Postman – Manual API testing
* Python (requests + pytest) – Automation
* Excel / Google Sheets – Test case management
* Notepad / Word – Documentation

---

### 4. Types of Testing

* Functional Testing
* Negative Testing
* Boundary Testing
* Schema Validation

---

### 5. Test Environment

* Live OpenWeather API endpoint
* Valid API Key from OpenWeather account

---

### 6. Entry Criteria

* API key generated and functional
* Internet access available

**Exit Criteria**

* All critical test cases executed and passed
* Known bugs logged and tracked

---

### 7. Deliverables

* Test Case Sheet
* Bug Report
* Automation Script (pytest)

---

### 8. Test Cases

| Test Case ID | Test Scenario                | Test                  | Expected Result                                                        | Type        | Priority |
| ------------ | ---------------------------- | --------------------- | ---------------------------------------------------------------------- | ----------- | -------- |
| TC-001  | Verify API response for valid city name  | Send GET request to `/data/2.5/weather?q=London&appid=API_KEY`  | Response Code = 200; JSON contains "London" in `name` field and valid weather data  | Functional  | High  |
| TC-002  | Verify API response for valid city with country code  | Send GET request to `/data/2.5/weather?q=Paris,FR&appid=API_KEY`  | Response Code = 200; Country = "FR"  | Functional  | Medium  |
| TC-003  | Verify API response for invalid city name  | Send GET request to `/data/2.5/weather?q=InvalidCity123&appid=API_KEY`  | Response Code = 404; Message = "city not found"  |  Negative  | High  |
| TC-004  | Verify response when API key is missing  | Send GET request without `appid`  | Response Code = 401; Message indicates invalid key  | Negative  | Critical  |
| TC-005  | Verify response for invalid API key  | Send GET request with wrong `appid`  | Response Code = 401; Message = "Invalid API key"  | Negative  | Critical  |
| TC-006  | Verify response when city name is empty  | Send GET request with `q=`  | Response Code = 400 or 404; Message indicating missing or invalid city  | Negative  | Medium  |
| TC-007  | Verify response using coordinates (lat/lon)  | Send GET request with `lat=35&lon=139`  | Response Code = 200; City returned matches expected region (Tokyo area)  | Functional  | Medium  |
| TC-008  | Verify response contains all main fields  | Send GET request for any valid city  | JSON contains keys: `coord`, `weather`, `main`, `wind`, `sys`, `name`  | Functional  | High  |
| TC-009  | Verify temperature unit conversion  | Send GET request with `units=metric` and `units=imperial`  | Both responses return different temperature values  | Functional  | Medium  |
| TC-010  | Verify API response time  | Measure response time for valid request  | Response time < 2 seconds  | Performance  | Low  |

---

### 9. Risks

* API downtime or rate limits during testing
* Invalid key usage

---

### 10. References

* OpenWeather API Docs: [https://openweathermap.org/api](https://openweathermap.org/api)

---

👨‍💻 **Author:** Abhishek Singh Negi  
📧 **Mail:** [abhisheknegi117@gmail.com](abhisheknegi117@gmail.com)  
🔗 **Socials:** [LinkedIn](https://www.linkedin.com/in/abhishek-singh-negi-07826717a/?profileId=ACoAACpljZwBBhgeIMtvXCQxs2UKWL_Fxb4T9NQ)
