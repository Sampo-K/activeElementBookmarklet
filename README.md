# What this is?
Simple bookmarklet that helps finding the currently focused item. Useful for accessibility testing.

# Installation
Add the code in the bookmarklet.js as a new bookmark to your browser's bookmark toolbar or preferred folder (use the code as the URL).
[Active Element](javascript%3A(()%3D%3E%7Bconst%20active%3DgetActiveElement()%3Bconst%20backup%3Dactive.style.outline%3Bactive.style.transition%3D%22outline%200.6s%20linear%22%3Bactive.style.outline%3D%222px%20solid%20red%22%3Bconsole.log(active)%3BsetTimeout(()%3D%3E%7Bactive.style.outline%20%3D%20backup%3B%7D%2C3000)%3Bfunction%20getActiveElement(element%3Ddocument.activeElement)%7Bconst%20shadowRoot%3Delement.shadowRoot%3Bconst%20contentDocument%3Delement.contentDocument%3Bif(shadowRoot%26%26shadowRoot.activeElement)%7Breturn%20getActiveElement(shadowRoot.activeElement)%3B%7Dif(contentDocument%26%26contentDocument.activeElement)%7Breturn%20getActiveElement(contentDocument.activeElement)%3B%7Dreturn%20element%7D%7D)()%3B)

# Running
Go to a desired page, navigate in the page using keyboard navigation methods. When you encounter strange behavior or lose the keyboard focus, click the bookmarklet and the active element will be logged in the developer console. The active element also gets a bright red outline for couple of seconds if the the element is visible.
