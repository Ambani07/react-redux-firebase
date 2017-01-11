<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

# isLoaded

Detect whether items are loaded yet or not

**Parameters**

-   `item` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Item to check loaded status of. A comma seperated list is also acceptable.

**Examples**

```javascript
import React, { Component, PropTypes } from 'react'
import { connect } from 'react-redux'
import { firebaseConnect, helpers } from 'react-redux-firebase'
const { isLoaded, dataToJS } = helpers
```

Returns **[Boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** Whether or not item is loaded

# isEmpty

Detect whether items are empty or not

**Parameters**

-   `item` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Item to check loaded status of. A comma seperated list is also acceptable.
-   `data`  

**Examples**

```javascript
import React, { Component, PropTypes } from 'react'
import { connect } from 'react-redux'
import { firebaseConnect, helpers } from 'react-redux-firebase'
const { isEmpty, dataToJS } = helpers
```

Returns **[Boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** Whether or not item is empty

# toJS

Convert Immutable Map to a Javascript object

**Parameters**

-   `data` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Immutable Map to be converted to JS object (state.firebase)

Returns **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** data - Javascript version of Immutable Map

Returns **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Data located at path within Immutable Map

# pathToJS

Convert parameter from Immutable Map to a Javascript object

**Parameters**

-   `firebase` **[Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)** Immutable Map to be converted to JS object (state.firebase)
-   `path` **[String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Path from state.firebase to convert to JS object
-   `notSetValue` **([Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) \| [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) \| [Boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean))** Value to use if data is not available
-   `data`  

**Examples**

_Basic_

```javascript
import { connect } from 'react-redux'
import { firebaseConnect, helpers } from 'react-redux-firebase'
const { pathToJS } = helpers
const fbWrapped = firebaseConnect()(App)
export default connect(({ firebase }) => ({
  profile: pathToJS(firebase, 'profile'),
  auth: pathToJS(firebase, 'auth')
}))(fbWrapped)
```

Returns **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Data located at path within Immutable Map

# dataToJS

Convert parameter under "data" path of Immutable Map to a Javascript object

**Parameters**

-   `firebase` **[Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)** Immutable Map to be converted to JS object (state.firebase)
-   `path` **[String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Path of parameter to load
-   `notSetValue` **([Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) \| [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) \| [Boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean))** Value to return if value is not found
-   `data`  

**Examples**

_Basic_

```javascript
import { connect } from 'react-redux'
import { firebaseConnect, helpers } from 'react-redux-firebase'
const { dataToJS } = helpers

const fbWrapped = firebaseConnect(['/todos'])(App)

export default connect(({ firebase }) => ({
  // this.props.todos loaded from state.firebase.data.todos
  todos: dataToJS(firebase, 'todos')
}))(fbWrapped)
```

Returns **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Data located at path within Immutable Map

# customToJS

Load custom object from within store

**Parameters**

-   `firebase` **[Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)** Immutable Map to be converted to JS object (state.firebase)
-   `path` **[String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Path of parameter to load
-   `customPath` **[String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Part of store from which to load
-   `notSetValue` **([Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) \| [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) \| [Boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean))** Value to return if value is not found
-   `data`  
-   `custom`  

**Examples**

_Basic_

```javascript
import { connect } from 'react-redux'
import { firebaseConnect, helpers } from 'react-redux-firebase'
const { customToJS } = helpers

const fbWrapped = firebaseConnect(['/todos'])(App)

export default connect(({ firebase }) => ({
  // this.props.todos loaded from state.firebase.data.todos
  requesting: customToJS(firebase, 'todos', 'requesting')
}))(fbWrapped)
```

Returns **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Data located at path within state