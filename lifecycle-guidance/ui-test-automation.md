# UI Test Automation - POM Framework

### What is Page Object Model Design Pattern \(POM\) ? <a id="what-is-page-object-model-design-pattern-pom"></a>

‌

Page Object Model is a Design Pattern which has become popular in Selenium Test Automation. It is widely used design pattern in Selenium for enhancing test maintenance and reducing code duplication. Page object model \(POM\) can be used in any kind of framework such as modular, data-driven, keyword driven, hybrid framework etc. A page object is an object-oriented class that serves as an interface to a page of your Application Under Test\(AUT\). The tests then use the methods of this page object class whenever they need to interact with the User Interface \(UI\) of that page. The benefit is that if the UI changes for the page, the tests themselves don’t need to change, only the code within the page object needs to change. Subsequently, all changes to support that new UI is located in one place.

​‌

### **Advantages of Page Object Model**  <a id="advantages-of-page-object-model"></a>

‌

The advantages of page object model can be listed as:‌

* **Code re-usability** – We could achieve code re-usability by writing the code once and use it in different tests.
* **Code maintainability** – There is a clean separation between test code and page specific code such as locators and layout which becomes very easy to maintain code. Code changes only on Page Object Classes when a UI change occurs. It enhances test maintenance and reduces code duplication.
* **Object Repository –** Each page will be defined as a java class. All the fields in the page will be defined in an interface as members. The class will then implement the interface.
* **Readability –** Improves readability due to clean separation between test code and page specific code

_**​**_‌

This approach is called **Page Object Model\(POM\)**. It helps make the code **more readable, maintainable**, and **reusable.**‌

​[​![Page Object Model \(POM\) &amp; Page Factory in Selenium: Complete Tutorial](https://www.guru99.com/images/AdvanceSelenium/071514_0722_PageObjectM2.png)​](https://www.guru99.com/images/AdvanceSelenium/071514_0722_PageObjectM2.png)​![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-Lm5QiXfvtgvTV6GtS-u%2F-Lo672Y92BSR5HodxDlt%2F-Lo689DNR-S_b2S48bRZ%2Fimage.png?alt=media&token=e693f07e-448f-46fe-a755-745be7c87f3b)‌

**This figure illustrates the page pattern model using Selenium:**

\*\*\*\*![](https://raw.githubusercontent.com/pluralsight/guides/master/images/2a2a896f-44af-4954-820a-ba3efc485970.png)

