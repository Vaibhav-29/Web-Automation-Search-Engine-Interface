# Web-Automation-Search-Engine-Interface
This project demonstrates basic web automation techniques using Selenium WebDriver and Python. You can extend this project by adding more complex scenarios, error handling, or integrating with other tools/frameworks for enhanced automation capabilities.
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
import time

# Define the URL of the website
url = "https://example.com"

# Define login credentials
username = "your_username"
password = "your_password"

# Define search query
search_query = "example query"

# Initialize the WebDriver (Chrome)
driver = webdriver.Chrome()

# Open the website
driver.get(url)

# Locate the login form elements
username_field = driver.find_element_by_id("username")
password_field = driver.find_element_by_id("password")
login_button = driver.find_element_by_id("login_button")

# Enter login credentials and submit
username_field.send_keys(username)
password_field.send_keys(password)
login_button.click()

# Wait for page to load
time.sleep(2)

# Locate the search bar
search_bar = driver.find_element_by_id("search_bar")

# Enter search query and submit
search_bar.send_keys(search_query)
search_bar.send_keys(Keys.RETURN)

# Wait for search results to load
time.sleep(2)

# Extract search results
search_results = driver.find_elements_by_class_name("search_result")

# Print search results
for result in search_results:
    print(result.text)

# Close the browser
driver.quit()
