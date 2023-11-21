# Customization

Various aspects of the **altron** can be customized through props. For more information about each prop, check the [Props](/docs/Usage/Props) route.

####  **Colors**

  - `primaryColor` : Used in both focus and view states.
  - `secondaryColor`: Specifically used in the edit state.
  - `textColor`: Defines the text color within the editor.
  - `bgColor`: The background color of your app, needed with `menu`.
  
#### **Fonts**
 
   - `headerFont`: Sets the font for header elements (e.g., h1, h2, h3, h4).
   - `bodyFont`: Defines the font for general text elements (e.g., p, span, label, li, a).
   
#### **Font Sizes and Line Heights**
    
   - Customize font sizes using `h1`, `h2`, `h3`, `h4`, `body`, `small`.
   - Set line heights for various text elements using `lh1`, `lh2`, `lh3`, `lh4`, and `lbody`.
#### **Custom spacing**

By default, **Altron** separates blocks with a 10px gap and have the different margins set to 10px.you can change that through these props **marginLeft** ,**marginRight**  , **marginTop** ,**marginBottom** and **blocksGap**.

#### **Custom width** 

You can also pass custom width for the editor the default is **95%**.

#### **Custom Code Block Languages** 

Define the list of languages users can use for code blocks with the `codeBlockLanguages` prop. By default, it includes JavaScript, Java, C, CSS, TypeScript, Python, and C#.

#### **Excluded Blocks**

This prop excludes a list of blocks from the blocks menu. This only restricts the end user from adding these blocks; you can still add those using the `setData` function.

#### **AttachmentTypes**
This prop specifies the mime types supported by the attachment block default to "*" meaning accept any file format/extension. For more information, check the [accept attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/accept).

#### **AcceptedEmbedSrcs** 
This prop defines an array of regexs for `embed` block accepted sources. This defaults to an empty array to accept any source.

#### **iframeSettings**
This contains iframe attributes that will be used to show the `embed` block data.

#### ProcessEmbedSrcs

This function is used in the embed block view state and takes as an argument an accepted source to modify it before passing it to the iframe. For example, here we are turning the badly formed YouTube source to an accepted one.

``` Typescript
processEmbedSrcs={(src) => {
   const a = src.split('/');
   a.splice(a.length - 1, 0, 'embed');
   return a.join('/').replace('watch?v=', '');
}}
```

#### Custom Components

You can replace the default view components for various block types with your custom components.

- `customImage`
- `customCode`
- `customList`
- `customHeader`
- `customParagraph`
- `customQuote`
- `customEmbed`
- `customCheckList`
- `customAttachment`
- `customMenu` : The default menu allows for deleting, moving up and down the **focused** block.