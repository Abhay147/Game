This handler helps you to handle multiple promises effortlessly. This library will handle processes and its sub processes and its sub process and so on... 

## Simplest Code
```js
    var processQueue = new ProcessQueue;
    var process1 = new Process(function(){/* promise invoker function */});
    processQueue.push(process1);
    var process2...
    var process3 ...
```

## Developers
**Build dist**
Just a simple node program run on build.js file.
* Make sure you have npm and node installed. If not [click here](https://nodejs.org/en/download/)
* On terminal do the following
```sh
git clone https://github.com/abhayjatindoshi/process-handler.git
cd process-manager/
npm install
node build.js
```

## Dependencies
* [UIkit](https://github.com/uikit/uikit) → Used for rendering the process UI

## API
## Process 

**Syntax**

```js
    new Process(invokingFunction);
    new Process(promise);
```
- invokingFunction → function that should be invoked inside the [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
- promise → or [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) object itself

**Methods**

```js
    then(resolve,reject);
```
- resolve, reject → functions that we pass to a [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

```js
    catch(reject);
```
- reject → function that we pass to a [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

```js
    getStatus()
```
- gets the current status of this process


## ProcessQueue

**Syntax**

```js
    new ProccessQueue();
```

**Methods**

```js
    push(Process);
    push(ProcessQueue);
```
- any `Process` or `ProcessQueue` type of object can be pushed into the queue

```js
    then(resolve,reject);
```
- resolve, reject → functions that we pass to a [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

```js
    catch(reject);
```
- reject → function that we pass to a [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

```js
    getStatus()
```
- gets the current status of this queue

## DecoratedProcess

**Syntax**

```js
    new DecoratedProcess(invokingFunction[,title]);
    new DecoratedProcess(promise[,title]);
```

- invokingFunction → function that should be invoked inside the [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
- promise → or [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) object itself
- title → initial title to display on [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)

**Methods**

All the methods from [Process](#Process) and the ones below.

```js
    appendToElement(DOMElement);
```
- DOMElement → to attach the DecoratedProcess UI to a [DOMElement](https://developer.mozilla.org/en-US/docs/Web/API/Element)

```js
    updateTitle(title);
```
- updates the title in the [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)


## DecoratedProcessQueue

**Syntax**

```js
    new DecoratedProcessQueue([title]);
```
- title → initial title to display on [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)

**Methods**

All the methods from [ProcessQueue](#ProcessQueue) and the ones below.

```js
    appendToElement(DOMElement);
```
- DOMElement → to attach the DecoratedProcessQueue to a [DOMElement](https://developer.mozilla.org/en-US/docs/Web/API/Element)

```js
    updateTitle(title);
```
- updates the title in the [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)
