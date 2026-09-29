# CLASS webElement

Selenium Webdriver represents all the HTML elements as WebElements. This
class provides a mechanism to represent them as objects & perform
various actions on the related elements. Typically, the findElement
method in
[`remoteDriver`](https://docs.ropensci.org/RSelenium/reference/remoteDriver-class.md)
returns an object of class webElement.

## Details

webElement is a generator object. To define a new webElement class
method \`new\` is called. When a webElement class is created an
elementId should be given. Each webElement inherits from a remoteDriver.
webElement is not usually called by the end-user.

## Fields

- `elementId`:

  Object of class `"character"`, giving a character representation of
  the element id.

## Methods

- `clearElement()`:

  Clear a TEXTAREA or text INPUT element's value.

- `clickElement()`:

  Click the element.

- `compareElements(otherElem)`:

  Test if the current webElement and an other web element refer to the
  same DOM element.

- `describeElement()`:

  Describe the identified element.

- `findChildElement( using = c("xpath", "css selector", "id", "name", "tag name", "class name", "link text", "partial link text"), value )`:

  Search for an element on the page, starting from the node defined by
  the parent webElement. The located element will be returned as an
  object of webElement class. The inputs are:

  `using`:

  :   Locator scheme to use to search the element, available schemes:
      `{"class name", "css selector", "id", "name", "link text", "partial link text", "tag name", "xpath" }`.
      Defaults to 'xpath'. Partial string matching is accepted.

  `value`:

  :   The search target. See examples.

- `findChildElements( using = c("xpath", "css selector", "id", "name", "tag name", "class name", "link text", "partial link text"), value )`:

  Search for multiple elements on the page, starting from the node
  defined by the parent webElement. The located elements will be
  returned as an list of objects of class WebElement. The inputs are:

  `using`:

  :   Locator scheme to use to search the element, available schemes:
      `{"class name", "css selector", "id", "name", "link text", "partial link text", "tag name", "xpath" }`.
      Defaults to 'xpath'. Partial string matching is accepted.

  `value`:

  :   The search target. See examples.

- `getElementAttribute(attrName)`:

  Get the value of an element's attribute. See examples.

- `getElementLocation()`:

  Determine an element's location on the page. The point (0, 0) refers
  to the upper-left corner of the page.

- `getElementLocationInView()`:

  Determine an element's location on the screen once it has been
  scrolled into view. Note: This is considered an internal command and
  should only be used to determine an element's location for correctly
  generating native events.

- `getElementSize()`:

  Determine an element's size in pixels. The size will be returned with
  width and height properties.

- `getElementTagName()`:

  Query for an element's tag name.

- `getElementText()`:

  Get the innerText of the element.

- `getElementValueOfCssProperty(propName)`:

  Query the value of an element's computed CSS property. The CSS
  property to query should be specified using the CSS property name, not
  the JavaScript property name (e.g. background-color instead of
  backgroundColor).

- `highlightElement(wait = 75/1000)`:

  Utility function to highlight current Element. Wait denotes the time
  in seconds between style changes on element.

- `isElementDisplayed()`:

  Determine if an element is currently displayed.

- `isElementEnabled()`:

  Determine if an element is currently enabled. Obviously to enable an
  element just preform a click on it.

- `isElementSelected()`:

  Determine if an OPTION element, or an INPUT element of type checkbox
  or radiobutton is currently selected.

- `selectTag()`:

  Utility function to return options from a select DOM node. The option
  nodes are returned as webElements. The option text and the value of
  the option attribute 'value' and whether the option is selected are
  returned also. If this method is called on a webElement that is not a
  select DOM node an error will result.

- `sendKeysToElement(sendKeys)`:

  Send a sequence of key strokes to an element. The key strokes are sent
  as a list. Plain text is enter as an unnamed element of the list.
  Keyboard entries are defined in \`selKeys\` and should be listed with
  name \`key\`. See the examples.

- `setElementAttribute(attributeName, value)`:

  Utility function to set an elements attributes.

- `submitElement()`:

  Submit a FORM element. The submit command may also be applied to any
  element that is a descendant of a FORM element.
