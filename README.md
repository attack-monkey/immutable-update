# immutable-update object (iu-object)
Immutably and easily update deep nested objects


 This immutable object updater leaves the original object in tact and produces a new object.

 It targets a specific node and creates a new object with the particular node updated to the new value
 
 If the node doesn't already exist, it will be created.
 If the node is updated to undefined / null / [] / {}, this will delete the node and any parent nodes that no longer have a child.

The first param is `state` - AKA the object to update

The second param is an array representing which node to target.

eg. `['lvl1', 'lvl2', 'val']` represents `state.lvl1.lvl2.val`

Note: the second parameter can also be a string delimted by '/'
eg. `'lvl1/lvl2/val'`

The third param is the value to update the node to

## Example

```javascript

import {iu} from iu-object;

obj = {
    hi: {
        im: {
            deeply: 'nested'
        }
    }
};

const newObj = iu(
    obj, 
    'hi/im/deeply',
    { immutably : 'updated' }
);

```