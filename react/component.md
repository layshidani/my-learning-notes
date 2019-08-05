# Exemplo de componente

## Componente botão com css 
```js
import React from 'react';
import { transform } from '@babel/core';

function Button(props) {
    const { onClick, text } = props;

    const buttonStyle = {
      textAlign:'center',
      fontSize: '0.7em',
      padding: '10px 20px',
      backgroundColor: '#0071A3',
      color: '#F1F1F1',
      border: 'none',
      borderRadius: '10px',
      textTransform:'uppercase',
      marginTop: '10px'
    };

    const disabledStyle = { ...buttonStyle, backgroundColor: '#ccc' }

    return (
        <button type='button' style={buttonStyle} onClick={onClick}>{text}</button>
    )
  }

  export default Button;
```

Para chamar este botão na page:

```js
<Button text='entrar' onClick={this.signIn} />
```

## Componente botão com css a parte e com fontawesome
```js
import React from 'react';
import './Button.css';
import { FontAwesomeIcon } from "@fortawesome/react-fontawesome";

function Button(props) {
  return (
    <button className={props.className} onClick={props.onClick} id={props.id}>
      <FontAwesomeIcon icon={props.iconName} /> {props.text} {props.price}
    </button>
  );
}

export default Button;
```

Para chamar este botão na page:

```js
<Button text='Entrar' className='btn' iconName={faSignInAlt} onClick={this.signIn} />
```