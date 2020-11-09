
The browser has an embedded engine sometimes called a “JavaScript virtual machine”. This engine converts the script to machine language. 

JavaScript is a “safe” programming language. It does not provide low-level access to memory or CPU.
It has no direct access to OS functions. limited to few things like working with files, webcam on user permission.

'Same origin policy'
    Different tabs/windows generally do not know about each other.

'use strict'
    When it is located at the top of a script, the whole script works the “modern” way.


Property getters and setters
    Data Properties
    Accessor Properties - get() and set()




------------    Async programming    ----------

  Callback function ++++++++
      To notify the calling instance that an asynchronous function has completed it's execution.

      const getTodo = callback => {
        setTimeout (() => {
          callback({ "value": 2000 })
        }, 3000)
      }

      getToDo(toDo => {
        console.log(todo.value)
      })

  Promises +++++++++++++++
      Makes handling async code easier and convenient.
      Constructor of Promise class is expecting a function which has async code as parameter. Function has two parameters reject and resolve.
      Resolve handle success and reject handle failure.
      If promise is resolved, we are now able to call a chain of then. If it is rejected, we will call a chain of then.

      Promise.all() - kind of like transaction i.e., all promises should excute 


  Async/Wait +++++++++++
      async keyword to indicate that function is executing async code based on a promise. It implies promise will be returned.
        It helps us to write promise based code as if it is syncronous, but w/o blocking execution thread.

      await means we have to for the promise to be resolved or rejected. It only makes async block wait. Can be only be used in async functions.
      Execution is sequential in async/await


Closures +++++++++++ ??????
  Closures give u access to an outer funtion's scope from an inner function.
  To use a closure, define a function inside another function and expose it. To expose a function, return it or pass it to another function.
  The inner function will have access to the variables in the outer function scope, even after the outer function has returned.


Data - binding

Vuejs:

Mutations - 
    store.commit("inc")
    mutations must be syncronous

Action - 
    dispatch actions in components with dispatch or {mapActions}
    store.dispatch("inc")
    actions can be asynchronous
    Make use of async / await
    