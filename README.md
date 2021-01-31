# snackbar

Snackbar material react component.

## Installation

```sh
npm install @marcoparrone/snackbar
```

## Usage

```js
import {Snackbar, open_snackbar} from '@marcoparrone/snackbar';
```

Read further for more information.

## Creating a snackbar

For creating a snackbar now you can use the Snackbar react component. It accepts just the "id" property:

 * id: a string containing an identifier for the snackbar;

Here is an example of a snackbar:

```js
<Snackbar id="mustBeNum">{this.state.text_snack_mustbenum}</Snackbar>
```

In the above example, this.state.text_snack_mustbenum contains the localized message to show in the snackbar.

## Showing a snackbar

The snackbars are hidden, to show them you can use the open_snackbar function.

The function accepts two parameters: a reference to some element containing the snackbar (it could be a reference to the top element of the react app), created with React.createRef(), and a string containing the id of the snackbar.

Here is an example:

```js
...
class NotesList extends React.Component {
...
  constructor(props) {
...
    this.notesListRef = React.createRef();
...
  handleSettingsChange(e) {
    let tmpint = 0;
...
      case 'textarearows':
        if (isNaN(e.target.value) || e.target.value === "") {
          open_snackbar (this.notesListRef, 'mustBeNum');
        } else {
...
  render() {
...
    <AppWithTopBar refprop={this.notesListRef} lang={this.state.language} appname={this.state.text_appname} ... >
      <Snackbar id="mustBeNum">{this.state.text_snack_mustbenum}</Snackbar>
...
```
