
## 路由变量

刚才展示的是常规的路由，路由中的规则是给定的，现在我们尝试使用路由变量，在组件中获取这个路由的变量，并做相应的组件展示。

```JavaScript
import React, { Component } from 'react';
import { Router, Route, hashHistory, Link, IndexRoute } from 'react-router';

import './App.css';

const Message = (props) =>
  <div>
    <h1>{props.params.message || 'Hello'}</h1>
    <Links />
  </div>

const Links = () =>
  <nav>
    <Link to="/">Hello</Link>
    <Link to="/yong">Yong</Link>
    <Link to="/feng">Feng</Link>
  </nav>

class App extends Component {
  render() {
    return (
      <Router history={hashHistory}>
        <Route path="/(:message)" component={Message} />
      </Router>
    );
  }
}

export default App;

```
