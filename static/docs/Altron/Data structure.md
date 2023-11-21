
# Data structure

Instead of using a global `contenteditable` element in where you can add different HTML elements. **Altron** workspace consist of separate blocks : paragraphs, headings, images, lists, quotes, etc . Each one of them is an independent `contenteditable` element (or more complex structure).

### Clean data store

The interesting part is that **altron** returns clean data instead of Html markup. For example if you have used medium before your blog will be stored like this :

``` Html
<section name="0ed1" class="section section--body section--first">  
   <div class="section-content">
      <h3 name="c2ad" class="graf graf--h3 "> header here </h3> 
      <p name="83d3" class="graf graf--p graf-after--h3">paragraph here</p>
   </div>
</section>
<section name="d1d2" class="section section--body">
  ...
</section>
```

compared to 

``` Typescript
const datablocks=[
 {
   id:"136251",
   name:"header",
   data:{
     text:"header here",
     level:3
   }
 },
 {
   id:"115621",
   name:"paragraph",
   data:{
     text:"paragraph here",
   }
 }
]
```

As you can see this data is clean where it can be rendered in your web , mobile , desktop apps.furthermore can easily stored in sql databases as tables or non sql once as json.

Each block is just an object with these properties:

- **id** is a random generated string using [nanoid](https://www.npmjs.com/package/nanoid).
- **name** representing the block's name.
- **data** which holds the block information.

### Data of each block 

| Name               | Data type                                                                 |
| ------------------ | --------------------------------------------------------------------------------- |
| paragraph              | { text: string }                       |
| header   | { text: string; level: 1 \| 2 \| 3 \| 4 }          |
| quote        | { text: string; owner: string } |
| image         | { base64: string; name: string; caption: string }                              |
| code         | { text: string; lang: languages }    |
| list       | { items: string[]; type: 'ordered' \| 'unordered' }                       |
| checklist    |{ items: { value: string; checked: boolean }[] }                     |
| attachment        | { file: File; title: string }                             |
| embed    | { src: string }   |
| space         | { size: number } 

### Blocks UI states

Each block in the editor's data list will be rendered as block level element where it can be in one of these three different states:

1. **View State:** In this state, the block displays its information based on its type and associated data.
2. **Focus State:** Upon clicking/touching a block, it transitions to the focus state. Here, the block is enveloped with options for deleting the block, moving it up and down (default options of the **menu**).
3. **Edit State:** Upon another click/touch, the block enters the edit state, allowing users to modify the block's information.
