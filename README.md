# react-router-classname-wrapper
generate classname wrapper from pathname

##### Example:


``` javascript

import React from 'react';
import ReactDOM from 'react-dom';
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';

import Home from './home';
import Example from './example';
import Foo from './example/foo';
import Bar from './example/bar';
import ClassNameWrapper from './components/classnamewrapper';

ReactDOM.render(
  <Router>
    <ClassNameWrapper pathname={this.props.location.pathname}>
      <Switch>
        <Route exact path="/" component={ Home } />
        <Route exact path="/example" component={ Example } />
        <Route exact path="/example/foo" component={ Foo } />
        <Route exact path="/example/bar" component={ Bar } />
      </Switch>
    </ClassNameWrapper>
  </Router>,
  document.querySelector('#root')
);
```

output:

When router is '/example'
``` html
<div className="example">
  <Example/>
</div>
```

When router is '/example/foo'
``` html
<div className="example">
  <div className="foo">
    <Foo/>
  </div>
</div>
```

When router is '/example/bar'
``` html
<div className="example">
  <div className="bar">
    <Bar/>
  </div>
</div>
```



