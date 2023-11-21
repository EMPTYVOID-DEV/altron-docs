# Events

**Altron** component fires several events when used in edit-mode ([viewMode](/docs/Usage/View mode) set to false). Let's go through them:

#### blockAdded

Fired when a new block has been added with the **Block id** and **name**.

#### blockDeleted

Fired when a block has been deleted with **Block ID**, **name**, and **data**.

#### blockMoved 

Fired when a block is moved with **Block ID** and **up** attribute (boolean) indicating whether it moved up or down.

#### focusing

Fired when a block gains focus with **Block ID**.
#### editing
Fired when a block is being edited with **Block ID**.

#### losingFocus
Fired when a block loses focus with null detail object.

