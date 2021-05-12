# Custom Hooks

### Ejecicio 1. 
- Comenzar por un nuevo proyecto de React. Modificar App para que se vea asi:

```js
import React, { useState } from 'react';
import './App.css';
const App = () => {

  const [count, setCount] = useState(1)

  const handleClick = () => {
    setCount(count+1)
  }
  return (
    <div className="App">
      <button onClick={handleClick}>Contar</button>
      <p>{count}</p>
    </div>
  );
};

export default App;
```

- Queremos extraer toda la lógica del estado en App y llevarla a un custom hook. 
- Hacer un custom hook que se llame desde App y que se encargue de actualizar la variable count cada vez que se aprieta el botón. 
- App debería quedar así:

```js
import React from 'react';
import './App.css';
import useCount from './hooks/useCount';

const App = () => {
  const [count, setCount] = useCount(1);

  return (
    <div className="App">
      <button onClick={setCount}>Contar</button>
      <p>{count}</p>
    </div>
  );
};

export default App;
```

### Ejercicio 2.

- Modificar App para que se vea asi:

```js
import React, { useState } from 'react';
import './App.css';
const App = () => {
  const [count, setCount] = useState(1);

  const handleClickSuma = () => {
    setCount(count + 1);
  };

  const handleClickResta = () => {
    setCount(count - 1);
  };

  return (
    <div className="App">
      <button onClick={handleClickSuma}>Sumar</button>
      <button onClick={handleClickResta}>Restar</button>
      <p>{count}</p>
    </div>
  );
};

export default App;
```

- Sin pensar en hooks todavía, modificar el código para que tanto la suma como la resta se hagan correctamente desde una sola función llamada handleClick 
- (pista: va a ser necesario identificar a los botones, por ejemplo con un id o con un name)
- Una vez que eso funcione, extraer toda la lógica del conteo al hook useCount
- App debería quedar así:

```js
import React from 'react';
import './App.css';
import useCount from './hooks/useCount'
const App = () => {

  const [count, setCount] = useCount(1)

  return (
    <div className="App">
      <button onClick={setCount} id="suma">Sumar</button>
      <button onClick={setCount} id="resta">Restar</button>
      <p>{count}</p>
    </div>
  );
};

export default App;
```




