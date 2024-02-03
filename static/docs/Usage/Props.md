# Props

The **Altron** entry accommodates several optional props.

### `ComponentMap`

- **Description:** This prop, as previously discussed, links the component name with its class reference. **Altron** sets it as context.
- **Type:** Map<string, ComponentType<SvelteComponent\>\>
- **Default value:** An empty map.

### `initialData` 

- **Description:** Used to initialize the editor with data. The initial data must adhere to the **datablock** type, and the provided data undergoes validation to ensure unique IDs.
- **Type:** dataBlock[]
- **Default value:** An empty list.

### `viewMode` 

- **Description:** Specifies whether **Altron** is used for editing or just viewing.
- **Type:** boolean
- **Default value:** false

### `iframeSettings` 

- **Description:** This prop is an object that specifies the settings for the iframe used in the **embed block**. **Altron** sets it as context.
- **Type:** [iframeSettingsType](/docs/Usage/Types/#IframeSettings)
- **Default value:** An empty object.

### `attachmentTypes` 

- **Description:** Restricts the accepted attachments by the **attachment block** to the chosen [mime type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types).
- **Type:** string
- **Default value:** "\*"

### `acceptedEmbedSrcs` 

- **Description:** Provides a description of the accepted sources by the embed block and a list of regex rules to match these accepted sources.
- **Type:** { rules: string[], description: string}
- **Default value:** { 
    description: 'You should enter a valid URL for an embed; any source is accepted',
    rules: [] }

### `processEmbedSrcs`

- **Description:** A method that processes the accepted source before setting it to the block value.
- **Type:** (src:string)=>string
- **Default value:** (src)=>src

### `codeBlockLanguages`  

- **Description:** The list of languages that end-users can choose inside the code block.
- **Type:** string[]
- **Default value:** ['javascript', 'java','c','css','plaintext','typescript','python','csharp']

### `Font families`

- **Description:** **Altron** expects two font families: one for body-level elements (span, code, li, label, p) and one for headers.
- **Type:** Both string
- **Default value:** Body font defaults to **Helvetica, sans-serif**, and headers font defaults to **Verdana, sans-serif**.

### `Colors` 

- **Description:** **Altron** utilizes five colors: **primaryColor** for the focus state, **secondaryColor** for the editing state, **bgColor** used in the dialog's backdrop, **errorColor** for errors, and  **textColor**.
- **Type:** All string
- **Default value:** Primary takes a shade of green **#3366FF**, secondary a shade of blue **#1eeb36**, bgColor takes white, error will default to **#ff3333**, and text color defaults to **#121212**.

### `Spacing`

- **Description:** You can set the **width** of the editor, the **gap** between blocks, and the four different margins.
- **Type:** All string
- **Default value:** Width defaults to **95%**, four margins to **10px**, and the gap also defaults to **10px**.

### `Heading Sizes` 

- **Description:** Six font size levels can be set: **h1, h2, h3, h4, body,** and **small**. 
- **Type:** All string
- **Default value:** A clamp function is used for default values, ranging from 0.875 rem up to 2.1 rem, making the fonts responsive.

### `Margins` 

- **Description:** You can set five line height levels: **lh1, lh2, lh3, lh4,** and **lbody**. 
- **Type:** All string
- **Default value:** They start with 1.3, with **lh1** increasing by 0.5 up to 1.6 **lbody**.