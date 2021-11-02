# Simple React Todo App with Storybook
> <details>
>  <summary>Contents</summary>
>
>> | [About]() | [Links]() |
>> | -- | -- |
>> | [Steps]() | |
>>
>
> </details>
>
> ## About
>> <details>
>>  <summary>This Todo App is built following the "<a href="https://towardsdatascience.com/build-a-simple-todo-app-using-react-a492adc9c8a4">Build a Simple Todo App using React</a>" by <a href="https://shubhamstudent5.medium.com/?source=post_page-----a492adc9c8a4--------------------------------">Kumar Shubham</a>, and the <a href="https://storybook.js.org/docs/react/get-started/introduction">Storybook.js</a> tutorial.</summary>
>> 
>>> This App follows and is adapted from the tutorials "[Build a Simple Todo App using React](https://towardsdatascience.com/build-a-simple-todo-app-using-react-a492adc9c8a4)" and the basic [`storybook.js` tutorial](https://storybook.js.org/docs/react/get-started/introduction). The main ambition of this repo/app is to outline a todo template for myself while familiarizing myself with `storybook.js` for future projects.
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
>>
>> </details>