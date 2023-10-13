Aquí te muestro cómo quedaría el README.md con buenos estilos y encabezado:

# React - Componentes, Props y Eventos

## React Conceptos Básicos

Este repositorio cubre los conceptos centrales de React como componentes, props, estado y eventos. Ideal para aprender las bases de React y su funcionalidad.

### Componentes

Los componentes permiten dividir la interfaz de usuario en piezas independientes, reutilizables y pensables. Son como funciones que reciben inputs y retornan elementos de interfaz de usuario.

Existen dos tipos de componentes:

#### Componentes Funcionales

- Son funciones simples de JavaScript que reciben props como parámetros y retornan elementos de React.
- No manejan estado interno ni tienen ciclo de vida.
- Se declaran con función o constante. 
- Ejemplo:

```jsx
const MiComponente = (props) => {
  return <h1>Hola {props.name}</h1>;
}
```

#### Componentes de Clase

- Son clases de JavaScript que extienden de React.Component.
- Manejan estado interno y métodos del ciclo de vida.
- El estado se declara en el constructor.
- Se renderizan usando el método `render()`.
- Ejemplo:

```jsx
class MiComponente extends React.Component {

  constructor(props) {
    super(props);
    this.state = {
      contador: 0  
    }
  }

  render() {
    return <h1>Contador: {this.state.contador}</h1>;
  }

}
```

En general se prefieren los componentes funcionales por su sintaxis limpia, a menos que se necesite manejar estado.

### Props

Las props (propiedades) permiten pasar datos de un componente padre a uno hijo. Son como los parámetros de una función.

- Se pasan como atributos en JSX.
- Se accede a ellas dentro del componente mediante `this.props`.
- Solo lectura (inmutables).
- Se recomienda nombrarlas de forma autodocumentada.

```jsx
<MiComponente name="Juan" edad={20} />

const MiComponente = (props) => {
  console.log(props.name) // Juan
  console.log(props.edad) // 20  
}
```

### Estado

El estado permite que los componentes de clase manejen data interna que impacta en la renderización.

- Se declara en el constructor.  
- Se actualiza con `this.setState()`.
- Nunca se modifica directamente.
- Los cambios en el estado disparan una rerenderización.

```jsx
class MiComponente extends React.Component {

  constructor(props) {
    super(props);
    this.state = {
      contador: 0
    }
  }

  incrementarContador = () => {  
    this.setState({
      contador: this.state.contador + 1
    });
  }
  
  render() {
    return <div>Contador: {this.state.contador}</div>;
  }

}
```

### Eventos  

El manejo de eventos en React se realiza a través de props como `onClick`, `onChange`, etc.

- Se asignan a elementos JSX como atributos.
- Reciben funciones manejadoras de eventos. 
- La sintaxis es similar a los eventos del DOM pero en camelCase.

#### Eventos en componentes funcionales

Se pasa una referencia a la función manejadora:

```jsx
function handleClick() {
  // hacer algo
}

<button onClick={handleClick}>Botón</button> 
```

También se pueden declarar inline:

```jsx
<button onClick={() => {
  // hacer algo 
}}>Botón</button>
```

#### Eventos en componentes de clase

Hay que bindear el manejador al contexto de la clase:

```jsx
class MiComponente extends React.Component {

  handleClick = () => {
    // hacer algo
  }
  
  render() {
    return <button onClick={this.handleClick}>Botón</button>;
  }

}
```

O bindar en el constructor:

```jsx
constructor(props) {
  super(props);
  this.handleClick = this.handleClick.bind(this); 
}
```

#### Eventos y Estado

Los manejadores de eventos pueden actualizar el estado con `this.setState()`:

```jsx 
handleClick() {
  this.setState({
    count: this.state.count + 1
  }); 
}
```

Esto dispara una rerenderización del componente.

#### Argumento del Evento

El manejador recibe un argumento con el objeto del evento:

```jsx
function handleChange(event) {
  console.log(event.target.value);
}
```
## Autores ✒️

* **Rex Developer** - *Creador* - [Rex Dev](https://github.com/rexstudios-dev)
