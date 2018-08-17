# Python selenium

A simple driver util function

```python
def setup_driver():
    """Setup the driver"""
    profile = webdriver.FirefoxProfile()
    profile.set_preference("browser.download.folderList", 2)
    profile.set_preference("browser.download.manager.showWhenStarting", False)
    profile.set_preference("browser.download.dir", os.getcwd())
    profile.set_preference("browser.helperApps.neverAsk.saveToDisk",
                           "application/csv")

    options = webdriver.FirefoxOptions()
    options.add_argument('-headless')
    driver = webdriver.Firefox(firefox_profile=profile, options=options)
    driver.implicitly_wait(30)
    return driver
```
