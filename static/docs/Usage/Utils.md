# Utils

**Altron** **exports** some utility functions that come in handy when trying to extract, update, or get information about the component state. Here is a description of each one:

- **getData**: This function returns the data-blocks that are stored at a given moment.It can also return the data for a block specific id.
- **setData**: This function allows you to update the data-blocks directly.
- **getEditorId:** This function returns to editor id.
- **getWorkingBlock**: This function allows you to get the working block id and its state. It can return null if none of the blocks are focused or edited (view state).

### Functions type

| Function | Type |
| ---- | ---- |
| getData | (id?:string)=> dataBlock[]\|dataBlock |
| setData | (newData: dataBlock[] \| ((prev: dataBlock[]) => dataBlock[]))=> void |
| getWorkingBlock | ()=>{state: "focused" \| "editing";  id: string; }  |
| getEditorId | ()=>string |

### Way to call

These functions are exported from the **Altron** component, which means in order to use them, you have to bind a variable to the component reference.

``` Typescript
<script lang="ts">
import Altron from '@altron/altron/altron.svelte';
import { onMount } from 'svelte';
let editor: Altron = null; 
// we are creating a variable to hold a reference to the AltronRichText component
onMount(() => {
    editor.setData([{ id: '12', name: 'header', data: { text: 'hello friend!', 
             level: 1 } }]); // initialize the editor with a header
    const intervalId = setInterval(() => {
        const data = editor.getData()
        const workingBlock = editor.getWorkingBlock()
        console.log(data, workingBlock)        
    }, 2000)
    // here we have created a setInterval that prints the component data and 
    //working block each two seconds
    return () => {
        clearInterval(intervalId)
    }
});
</script>  
   <div>
     <Altron bind:this={editor} />
   </div>
```