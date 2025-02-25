# gx-detect
How-to for detecting GX browser in the web page

### Scenario
You would like to determine if a site is being visited through Opera GX.

That would allow e.g. to decide if a user should see some additional/exclusive content when a page is being visited using Opera GX.

### How to check if a browser is Opera GX?
The way of checking whether the browser in Opera GX is to call from page scripts:

```javascript
window.navigator.userAgentData?.toString().indexOf('[object NavigatorUAData]') === 0 && window.navigator.userAgentData?.brands?.some(item => item.brand == "Opera GX")
```

That statement returns ```true``` if the browser is Opera GX - otherwise it will return ```false```.

### Examples
Example page with Opera GX detection [GX detection example](gx_detection_example.html)

### Note
Running other browser with overridden ```--user-agent``` will change the ```user-agent``` in the headers of outcoming requests but won't change the ```window.navigator.userAgentData``` object.
