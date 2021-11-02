# Simple React Todo App with Storybook
> <details>
>  <summary>Contents</summary>
>
>> | [About](https://github.com/mmmoore1313/React-toDo/tree/main#about) | [Links](https://github.com/mmmoore1313/React-toDo/tree/main#links) |
>> | -- | -- |
>> | [Steps](https://github.com/mmmoore1313/React-toDo/tree/main#steps) | |
>>
>
> </details>
>
> ## About
>> <details>
>>  <summary>This Todo App is built following the "<a href="https://towardsdatascience.com/build-a-simple-todo-app-using-react-a492adc9c8a4">Build a Simple Todo App using React</a>" by <a href="https://shubhamstudent5.medium.com/?source=post_page-----a492adc9c8a4--------------------------------">Kumar Shubham</a>, and the <a href="https://storybook.js.org/docs/react/get-started/introduction">Storybook.js</a> tutorial.</summary>
>> 
>>> This App follows and is adapted from the tutorials "[Build a Simple Todo App using React](https://towardsdatascience.com/build-a-simple-todo-app-using-react-a492adc9c8a4)" and the basic [`storybook.js` tutorial](https://storybook.js.org/docs/react/get-started/introduction). The main ambition of this repo/app is to outline a todo template for myself while familiarizing myself with `storybook.js` for future projects.
>>> ###### [Return to Top](https://github.com/mmmoore1313/React-toDo/tree/main#simple-react-todo-app-with-storybook)
>> </details>
> ## Steps
>> <details>
>>  <summary>1. Create the app</summary>
>>
>>> <details>
>>>  <summary> 1.1- <a href="https://reactjs.org/docs/create-a-new-react-app.html">Create React App</a></summary>
>>>
>>>> `npx create-react-app todo`
>>> </details>
>>> <details>
>>>  <summary>1.2- Switch into the <code>todo</code> directory</summary>
>>>
>>>> `cd todo`
>>> </details>
>> </details>
>> <details>
>>  <summary>2. Setup <code><a href="https://storybook.js.org/docs/react/get-started/introduction">storybook.js</a></code></summary>
>>
>>> <details>
>>>  <summary>2.1- Install <code><a href="https://storybook.js.org/docs/react/get-started/introduction">storybook.js</a></code></summary>
>>>
>>>> `npx sb init`
>>> </details>
>>> <details>
>>>  <summary>2.2- Run <code><a href="https://storybook.js.org/docs/react/get-started/introduction">storybook.js</a></code></summary>
>>>
>>>> `yarn storybook`  
>>>> -or if you prefer npm-  
>>>> `npm run storybook`  
>>>> <details>
>>>>  <summary>Troubleshooting</summary>
>>>>
>>>>> <details>
>>>>>  <summary><code>babel-loader</code> error</summary>
>>>>>
>>>>>> In `todo/package.json`, add  
>>>>>> ```
>>>>>> "resolutions": {
>>>>>>   "babel-loader": "8.1.0"
>>>>>>  }
>>>>>> ```  
>>>>>> to the bottom
>>>>> </details>
>>>> </details>
>>> </details>
>> </details>
>> <details>
>>  <summary>3. Make it do something</summary>
>>
>>> <details>
>>>  <summary>3.1- Imports</summary>
>>>
>>>> Add to the top:
>>>> ```
>>>>  import { Button, Card, Form } from 'react-bootstrap'
>>>>  import 'bootstrap/dist/css/bootstrap.min.css'
>>>> ```
>>> </details>
>>> <details>
>>>  <summary>3.2- Functions</summary>
>>>
>>>> <details>
>>>>  <summary>3.2.1- <code>Todo()</code></summary>
>>>>
>>>>> ```
>>>>> function Todo({ todo, index, markTodo, removeTodo }) {
>>>>>   return (
>>>>>     <div className="todo">
>>>>>       <span style={{ textDecoration: todo.isDone ? "line-through" : "" }}>
>>>>>         {todo.text}
>>>>>       </span>
>>>>>       <div>
>>>>>         <Button variant="outline-success" onClick={() => markTodo(index)}>
>>>>>           ✓
>>>>>         </Button>
>>>>>         {' '}
>>>>>         <Button variant="outline-danger" onClick={() => removeTodo(index)}>
>>>>>           ✕
>>>>>         </Button>
>>>>>       </div>
>>>>>     </div>
>>>>>   )
>>>>> }
>>>>> ```
>>>> </details>
>>>> <details>
>>>>  <summary>3.2.2- <code>FormTodo()</code></summary>
>>>>
>>>>> <details>
>>>>>  <summary>3.2.2.1- <code>useState()</code></summary>
>>>>>
>>>>>> `const [value, setValue] = React.useState("")`
>>>>> </details>
>>>>> <details>
>>>>>  <summary>3.2.2.2- <code>handleSubmit()</code></summary>
>>>>>
>>>>>> ``` 
>>>>>> const handleSubmit = e => {
>>>>>>   e.preventDefault()
>>>>>>   if (!value) return
>>>>>>   addTodo(value)
>>>>>>   setValue("")
>>>>>> }
>>>>>> ``` 
>>>>> </details>
>>>>> <details>
>>>>> <summary>3.2.2.3- <code>return()</code></summary>
>>>>>
>>>>>> ``` 
>>>>>> return (
>>>>>>   <Form onSubmit={handleSubmit}>
>>>>>>     <Form.Group>
>>>>>>       <Form.Label>
>>>>>>         <b>Add Todo</b>
>>>>>>       </Form.Label>
>>>>>>       <Form.Control
>>>>>>         type="text"
>>>>>>         className="input"
>>>>>>         value={value}
>>>>>>         onChange={e => setValue(e.target.value)}
>>>>>>         placeholder="Add new todo"
>>>>>>       />
>>>>>>       <Button variant="primary mb-3" type="submit">
>>>>>>         Submit
>>>>>>       </Button>
>>>>>>     </Form.Group>
>>>>>>   </Form>
>>>>>> )
>>>>>> ``` 
>>>>> </details> 
>>>> </details>
>>>> <details>
>>>>  <summary>3.2.3- <code>App()</code></summary>
>>>>
>>>>> <details>
>>>>>  <summary>3.2.3.1- <code>useState()</code></summary>
>>>>>
>>>>>> ``` 
>>>>>> const [todos, setTodos] = React.useState([
>>>>>>   {
>>>>>>     text: "This is a sample todo",
>>>>>>     isDone: false
>>>>>>   }
>>>>>> ])
>>>>>> ```  
>>>>> </details>
>>>>> <details>
>>>>>  <summary>3.2.3.2- <code>addTodo()</code></summary>
>>>>>
>>>>>> ``` 
>>>>>> const addTodo = text => {
>>>>>>   const newTodos = [...todos, { text }]
>>>>>>   setTodos(newTodos)
>>>>>> }
>>>>>> ```  
>>>>> </details>
>>>>> <details>
>>>>>  <summary>3.2.3.3- <code>markTodo()</code></summary>
>>>>>
>>>>>> ``` 
>>>>>> const markTodo = index => {
>>>>>>   const newTodos = [...todos]
>>>>>>   newTodos[index].isDone = true
>>>>>>   setTodos(newTodos)
>>>>>> }
>>>>>> ```  
>>>>> </details>
>>>>> <details>
>>>>>  <summary>3.2.3.4- <code>removeTodo()</code></summary>
>>>>>
>>>>>> ``` 
>>>>>> const removeTodo = index => {
>>>>>>   const newTodos = [...todos]
>>>>>>   newTodos.splice(index, 1)
>>>>>>   setTodos(newTodos)
>>>>>> }
>>>>>> ``` 
>>>>> </details>
>>>>> <details>
>>>>>  <summary>3.2.3.5- <code>return()</code></summary>
>>>>>
>>>>>> ``` 
>>>>>> return (
>>>>>>   <div className="app">
>>>>>>     <div className="container">
>>>>>>       <h1 className="text-center mb-4">
>>>>>>         Todo List
>>>>>>       </h1>
>>>>>>       <FormTodo addTodo={addTodo} />
>>>>>>       <div>
>>>>>>         {todos.map((todo, index) => (
>>>>>>           <Card>
>>>>>>             <Card.Body>
>>>>>>               <Todo
>>>>>>                 key={index}
>>>>>>                 index={index}
>>>>>>                 todo={todo}
>>>>>>                 markTodo={markTodo}
>>>>>>                 removeTodo={removeTodo}
>>>>>>               />
>>>>>>             </Card.Body>
>>>>>>           </Card>
>>>>>>         ))}
>>>>>>       </div>
>>>>>>     </div>
>>>>>>   </div>
>>>>>> )
>>>>>> ``` 
>>>>> </details>
>>>> </details>
>>> </details>
>>> <details>
>>>  <summary>3.3- Complete <code>App.js</code></summary>
>>>
>>>> ``` 
>>>>  import React from "react"
>>>>  import './App.css';
>>>>  import { Button, Card, Form } from 'react-bootstrap'
>>>>  import 'bootstrap/dist/css/bootstrap.min.css'
>>>>  
>>>>  function Todo({ todo, index, markTodo, removeTodo }) {
>>>>    return (
>>>>      <div className="todo">
>>>>        <span style={{ textDecoration: todo.isDone ? "line-through" : "" }}>
>>>>          {todo.text}
>>>>        </span>
>>>>        <div>
>>>>          <Button variant="outline-success" onClick={() => markTodo(index)}>
>>>>            ✓
>>>>          </Button>
>>>>          {' '}
>>>>          <Button variant="outline-danger" onClick={() => removeTodo(index)}>
>>>>            ✕
>>>>          </Button>
>>>>        </div>
>>>>      </div>
>>>>    )
>>>>  }
>>>>  
>>>>  function FormTodo({ addTodo }) {
>>>>    const [value, setValue] = React.useState("")
>>>>    
>>>>    const handleSubmit = e => {
>>>>      e.preventDefault()
>>>>      if (!value) return
>>>>      addTodo(value)
>>>>      setValue("")
>>>>    }
>>>>    
>>>>    return (
>>>>      <Form onSubmit={handleSubmit}>
>>>>        <Form.Group>
>>>>          <Form.Label>
>>>>            <b>Add Todo</b>
>>>>          </Form.Label>
>>>>          <Form.Control
>>>>            type="text"
>>>>            className="input"
>>>>            value={value}
>>>>            onChange={e => setValue(e.target.value)}
>>>>            placeholder="Add new todo"
>>>>          />
>>>>          <Button variant="primary mb-3" type="submit">
>>>>            Submit
>>>>          </Button>
>>>>        </Form.Group>
>>>>      </Form>
>>>>    )
>>>>  }
>>>>  
>>>>  function App() {
>>>>    const [todos, setTodos] = React.useState([
>>>>      {
>>>>        text: "This is a sample todo",
>>>>        isDone: false
>>>>      }
>>>>    ])
>>>>    
>>>>    const addTodo = text => {
>>>>      const newTodos = [...todos, { text }]
>>>>      setTodos(newTodos)
>>>>    }
>>>>    
>>>>    const markTodo = index => {
>>>>      const newTodos = [...todos]
>>>>      newTodos[index].isDone = true
>>>>      setTodos(newTodos)
>>>>    }
>>>>    
>>>>    const removeTodo = index => {
>>>>      const newTodos = [...todos]
>>>>      newTodos.splice(index, 1)
>>>>      setTodos(newTodos)
>>>>    }
>>>>    
>>>>    return (
>>>>      <div className="app">
>>>>        <div className="container">
>>>>          <h1 className="text-center mb-4">
>>>>            Todo List
>>>>          </h1>
>>>>          <FormTodo addTodo={addTodo} />
>>>>          <div>
>>>>            {todos.map((todo, index) => (
>>>>              <Card>
>>>>                <Card.Body>
>>>>                  <Todo
>>>>                    key={index}
>>>>                    index={index}
>>>>                    todo={todo}
>>>>                    markTodo={markTodo}
>>>>                    removeTodo={removeTodo}
>>>>                  />
>>>>                </Card.Body>
>>>>              </Card>
>>>>            ))}
>>>>          </div>
>>>>        </div>
>>>>      </div>
>>>>    )
>>>>  }
>>>>  
>>>>  export default App;
>>>> ```  
>>> </details>
>> </details>
>> ###### [Return to Top](https://github.com/mmmoore1313/React-toDo/tree/main#simple-react-todo-app-with-storybook)
> </details>
>
> ## Links
>> <details>
>>  <summary>Relevant Links</summary>
>>
>>> 
>> </details>
