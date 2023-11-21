# Props

Here are all **Altron** props and their **Default** values:

#### processEmbedSrcs

**Type**: (src: string) => string  
**Default**: (src: string) => {return src;};

#### excludedBlocks

**Type**: blocks[]  
**Default**: []

#### attachmentTypes

**Type**: string  
**Default**: "\*"

#### acceptedEmbedSrcs

**Type**: string[]  
**Default**: []

#### iframeSettings

**Type**: IframeSettings  
**Default**: {}

#### viewMode

**Type**: boolean  
**Default**: false

#### headerFont

**Type**: string  
**Default**: 'Verdana, sans-serif'

#### bodyFont

**Type**: string  
**Default**: 'Helvetica, sans-serif'

#### primaryColor

**Type**: string  
**Default**: '#3366FF'

#### secondaryColor

**Type**: string  
**Default**: '#1eeb36'

#### textColor

**Type**: string  
**Default**: '#121212'

#### bgColor

**Type**: string  
**Default**: '#ffffff'

#### blocksGap

**Type**: string  
**Default**: "10px"

#### marginLeft

**Type**: string  
**Default**: "10px"

#### marginRight

**Type**: string  
**Default**: "10px"

#### marginTop

**Type**: string  
**Default**: "10px"

#### marginBottom

**Type**: string  
**Default**: "10px"

#### width

**Type**: string  
**Default**: "95%"

#### h1

**Type**: string  
**Default**: 'clamp(1.8rem, calc(1.8rem + ((1vw - 0.48rem) * 0.9722)), 2.1rem)'

#### h2

**Type**: string  
**Default**: 'clamp(1.5rem, calc(1.5rem + ((1vw - 0.48rem) * 0.9722)), 1.8rem)'

#### h3

**Type**: string  
**Default**: 'clamp(1.2rem, calc(1.2rem + ((1vw - 0.48rem) * 0.9722)), 1.5rem)'

#### h4

**Type**: string  
**Default**: 'clamp(1.125rem, calc(1.15rem + ((1vw - 0.48rem) * 0.3472)), 1.2rem)'

#### body

**Type**: string  
**Default**: 'clamp(1rem, calc(1rem + ((1vw - 0.48rem) * 0.1736)), 1.125rem)'

#### small

**Type**: string  
**Default**: 'clamp(0.875rem, calc(0.875rem + ((1vw - 0.48rem) * 0.1736)), 1rem)'

#### lh1

**Type**: string  
**Default**: '1.3'

#### lh2

**Type**: string  
**Default**: '1.35'

#### lh3

**Type**: string  
**Default**: '1.4'

#### lh4

**Type**: string  
**Default**: '1.5'

#### lbody

**Type**: string  
**Default**: '1.6'

#### codeBlockLanguages

**Type**: languages[]  
**Default**: ['javascript', 'java', 'c', 'css', 'plaintext', '**Type**script', 'python', 'csharp']


#### Custom components

|Component|Props|
|---|---|
|customEmbed|Accepts a **src** prop of **Type** **string** for the embedded view.|
|customAttachment|Accepts a **file** prop of **Type** **File** and a **title** prop of **Type** **string**.|
|customImage|Accepts **base64** (string), **name** (string), and **caption** (string) props.|
|customCode|Accepts **text** (string) and **lang** (languages) props.|
|customList|Accepts **items** (array of strings) and ****Type**** ('ordered' or 'unordered') props.|
|customHeader|Accepts **text** (string) and **level** (1, 2, 3, or 4) props.|
|customParagraph|Accepts a **text** prop of **Type** **string** for the paragraph view.|
|customQuote|Accepts **text** (string) and **owner** (string) props.|
|customCheckList|Accepts an array of objects with **value** (string) and **checked** (boolean) props.|
|customMenu|Accepts a **close** prop which is function to close the menu. Set to **null**.|