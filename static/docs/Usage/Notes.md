# Notes

There is some notes worth taking in consideration when using **Altron**.

#### Code Highlighting

**Altron** by default doesn't highlight code blocks mainly to decrease the package size, but we recommend using [svelte-highlight](https://www.npmjs.com/package/svelte-highlight). There is a **customCode** example that uses **svelte-highlight** in the suggestions sub-directory of the project repository.

#### More than one instance

The data of **Altron** component is isolated, allowing us to create more than one instance of the component for things like changes comparison.

#### Error handling

When unwanted data has been added by the user **Altron** sets the default value.

- **embed** when the input value is not a https-url or didn't follow the **acceptedEmbedSrcs** altron will set the source to empty string then handle it inside the view component.

- **attachment** if the user didnt select a file or the selection does not meet the **attachmentTypes** altron will set the file to null.

- same with **image** block base64 is empty string until a proper image get selected.