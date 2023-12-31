![altronBg](/images/altronBg.png)

**Altron** is a robust and versatile rich text editor designed for Svelte applications. It empowers users to effortlessly create, edit, and manage structured text content by seamlessly incorporating various blocks with associated data. This component is meticulously crafted to offer high customizability, responsiveness on mobile devices, and support for both editing and viewing modes.

## Data structure

Instead of using a global contenteditable element in where you can add different HTML elements. Altron workspace consist of separate blocks : paragraphs, headings, images, lists, quotes, etc . Each one of them is an independent contenteditable element (or more complex structure).

## Clean data store

The interesting part is that altron returns clean data instead of Html markup. For example if you have used medium before your blog will be stored like this :
Html

```Html
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

```Typescript
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
id is a random generated string using nanoid .
name representing the block's name.
data which holds the block information.

## More info

You can check altron's documentation website for more information [altronDocs](https://altron.vercel.app/).
