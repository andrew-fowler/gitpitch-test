# Webdriverio
# Cucumber
# Typescript

---

# Step definitions
 
```typescript
import TheInternet from '../model/pages/theinternet.page';

var module: any;
module.exports = function theinternet() {

    this.Given(
        /^I load the internet/,
        function () {
            TheInternet.open();
        } );

    this.Then(
        /^the internet is loaded/,
        function () {
            TheInternet.welcomeMessage.waitForVisible();
        } );
};
```
---

# Page object model

```typescript
class theinternet {

    public get welcomeMessage()  { return browser.element("//h1[contains(.,'Welcome to the Internet')]") }

    public open(): void {
        browser.url('/')
    }
}
const TheInternet = new theinternet();
export default TheInternet
```