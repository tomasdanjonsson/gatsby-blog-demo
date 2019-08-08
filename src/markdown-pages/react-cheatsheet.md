---
title: "React Cheatsheet"
date: "2019-08-09"
---

### Components

```
import React from 'react'
import ReactDOM from 'react-dom'
class Hello extends React.Component {
  render () {
    return <div className='message-box'>
      Hello {this.props.name}
    </div>
  }
}
const el = document.body
ReactDOM.render(<Hello name='John' />, el)i
```

### Functional components

```
function MyComponent ({ name }) {
  return <div className='message-box'>
    Hello {name}
  </div>
}
```

### Import multiple exports

```
import React, {Component} from 'react'
import ReactDOM from 'react-dom'
class Hello extends Component {
  ...
}
```

### Constructor

```
constructor(props) {
  super(props);
  this.state = {
    list: props.initialList
  };
}

// where props aren't used in constructor

constructor() {
  super();
  this.state = {
    list: []
  };
}
```

### Context

```
// requires 'prop-types' library

import { string } from "prop-types";

class Cowboy extends React.Component {
  childContextTypes: {
    salutation: string
  }

  getChildContext() {
    return { salutation: "Howdy" };
  }

  render() {
    return React.Children.only(this.props.children);
  }
}

const Greeting = (props, context) =>
  <div>{this.context.salutation} {this.props.name}.</div>

Greeting.contextTypes = {
  salutation: PropTypes.string
}

// <Greeting name="Michael" />
// => Michael.

// <Cowboy><Greeting name="Michael" /></Cowboy>
// => Howdy Michael.
```

_source: https://devhints.io/react & https://reactcheatsheet.com/_
