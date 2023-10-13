# React - Componentes, Props y Eventos

## Componentes

Los componentes permiten separar la interfaz de usuario en piezas independientes y reutilizables. Existen dos tipos:

### Componentes Funcionales

Son simples funciones de JS que reciben props y retornan elementos de React:

```jsx
const MiComponente = (props) => {
  return <h1>Hola {props.name}</h1>
}
```

### Componentes de Clase

Son clases de JS que extienden de React.Component. Manejan estado y tienen métodos complejos: 

```jsx
class MiComponente extends React.Component {

  state = {
    // estado inicial
  }

  render() {
    return <h1>Hola {this.props.name}</h1>
  }

}
```

Se prefieren los funcionales por su simplicidad.

## Props

Las props son inputs que se pasan de un componente padre a uno hijo. Permiten personalizar y reutilizar componentes:

```jsx
<MiComponente name="Juan"/>
```

Se accede a las props via `props` dentro del componente. Se recomienda nombrarlas de forma clara y autodocumentada.

## Eventos 

El manejo de eventos se realiza con props como `onClick`, `onChange`, etc:

```jsx
function miFuncionClick() {
  // código manejo click 
}

<button onClick={miFuncionClick}>Botón</button>
```

En componentes de clase se debe bindear al `this`.

## Renderizado

El método `ReactDOM.render()` se utiliza para renderizar componentes en el DOM:

```jsx
ReactDOM.render(<MiComponente />, document.getElementById('root'))  
```

Permite incrustar componentes de React en elementos HTML existentes.

