# Exemplo de Rota

No arquivo **App.js**:

```js
import React, { Component } from 'react';
import './App.css';
import Page1 from './pages/Page1';
import Page2 from './pages/Page2';
import SpecialPage from './pages/SpecialPage';
import {BrowserRouter as Router, Route} from 'react-router-dom';

class App extends Component {
  constructor(props) {
    super(props);
    this.state = {};
  }

  render() {
    return (
      <Router>
      <div className='App'>
        <header className='App-header'>
          <Route exact path='/' component={Page1}/>
          <Route exact path='/page2' component={Page2}/>
          <Route exact path='/special-page' component={SpecialPage}/>
        </header>
      </div>
    </Router>
    );
  }
}

export default App;
```