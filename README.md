# javascript-modules-n-a-minute

A **module** is just a file which exports some JavaScript code.

First, a file exports (package) something useful…

awesome-pacakge.js
```export default '🧁';```

Second, a different file uses this code by importing it.

my-app.js
```import cupcake from '../path/to/awesome-package.js';```

Pretty simple! But there's more you should know.

### Default Exports

A module can specify at most 1 default export.

```export default '🧁';```

This allows the consumer to name the module whatever it prefers when importing.

```
// wait, that's not pizza...
import pizza from '../path/to/awesome-package';
```

This is ideal for modules which export a single class or function.

## Named Exports

Some modules might offer a collection of independent helper functions, like RxJS or Lodash. A better option for such packages is named **exports**.

```
export const cupcake = '🧁';
export const pizza = '🍕';
```
If the consumer only wants pizza, they can import it by name - this is called treeshaking or dead code elimination.

```import { pizza } from '../path/to/awesome-package'; ```

### How to change the name of an import?

If you don’t like the exported name, you can change it with the ```as``` keyword.

```
import { pizza as awesomePizza } from '../path/to/awesome-package';

console.log(awesomePizza);
```
### How to export a list of variables?

A module may have many variables to export and this can get messy. Use an export list to make your code more succinct and organized.

```
const cupcake = '🧁';
const pizza = '🍕';

export { 
    cupcake,
    pizza
}
```



