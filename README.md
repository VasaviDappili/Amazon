# Amazon
# Code
```
import time
from selenium import webdriver
from selenium.webdriver.chrome.options import Options
chrome_options = Options()
chrome_options.add_experimental_option("detach", True)
chrome_options.add_argument("--disable-blink-features=AutomationControlled")
driver = webdriver.Chrome(options=chrome_options)
driver.maximize_window()
product_asin = "B071Z8M4KX"
product_url = f"https://www.amazon.in/dp/{product_asin}"
print("Step 1: Opening Product Page...")
driver.get(product_url)
tab_product = driver.current_window_handle
time.sleep(3)
print("✓ Product page opened")
print("\nStep 2: Opening Cart tab...")
driver.switch_to.new_window("tab")
tab_cart = driver.current_window_handle
add_to_cart_url = (
    f"https://www.amazon.in/gp/aws/cart/add.html?"
    f"ASIN.1={product_asin}&Quantity.1=1"
)

driver.get(add_to_cart_url)

time.sleep(3)

print("✓ Product added to Cart")

print("Step 3: Opening Cart page...")

driver.get(
    "https://www.amazon.in/gp/cart/view.html"
)

time.sleep(3)

print("✓ Cart page opened")

print("\nStep 4: Opening Wishlist tab...")

driver.switch_to.new_window("tab")

tab_wishlist = driver.current_window_handle

driver.get(
    "https://www.amazon.in/hz/wishlist/intro"
)

time.sleep(3)

print("✓ Wishlist page opened")
print("\n=======================================================")
print("AUTOMATION COMPLETED")
print("=======================================================")

print("✓ Tab 1 → Product Page")
print("✓ Tab 2 → Cart Page")
print("✓ Product added to Cart")
print("✓ Tab 3 → Wishlist Page")

print("=======================================================")

input(
    "\nPress ENTER here in the terminal when you want to close Chrome..."
)

driver.quit()

print("Chrome closed.")

```
# Output
<img width="1600" height="852" alt="image" src="https://github.com/user-attachments/assets/14eb60f9-0c6a-4483-9099-d1c7beccb6e8" />
<img width="1600" height="851" alt="image" src="https://github.com/user-attachments/assets/2a434f9d-2561-4df7-8d1f-b597a8509783" />
<img width="1600" height="861" alt="image" src="https://github.com/user-attachments/assets/e5663297-e808-4219-aa03-d8c7bd0c3bb9" />


