# react-native-multiSelect-flatList
> A simple RN component that can search, open edit block with abilities to select all item, remove selected with animations

![Demo](https://github.com/purumvisum/react-native-multiSelect-flatList/blob/master/ice_video_20171005-112420.gif)


# Instalation
`npm install https://github.com/purumvisum/react-native-multiSelect-flatList`

## Usage
```javascript
import EditableFlatList from 'react-native-multiselect-flatlist';
   
<EditableFlatList
    itemsList={this.props.sessions}
    keyExtractor={(item, index) => item.Id}
    searchBy={(item) => item.Description}
    orderBy={(item) => item.Description}
    renderRow={this._renderRow.bind(this)}
    clickOnRow = {this._selectSession.bind(this)}
    removeRow={this._exitOrRemoveSession.bind(this)}
    onRefresh={this.props.updateSessions}
    preventSelectingActions = {!isOwner} 
    emptyListText = {'You have no items...'}
    iconWidth = {40}
    iconStyles = {{
         marginLeft: 0
     }}
     
 />
```

## Attributes
### `itemsList` `required`  
A list of items to dispalay (equivalent for [FlatList data attr](https://facebook.github.io/react-native/docs/flatlist.html))
### `keyExtractor` `required` 
keyExtractor tells the list to use the ids for the react keys.(equivalent for [FlatList keyExtractor attr](https://facebook.github.io/react-native/docs/flatlist.html))
### `searchBy`
Set item sorting field
### `orderBy`
Set item oreder field
### `renderRow`
Allow to use your styles and set content of items in row. 
> Do not use TouchableOpacity, TouchableWithoutFeedback and TouchableHighlight. renderItem method of FlatList already rewrited by module and using touchable elemnts can cancel modle events. To make from EditableFlatList simple FlatList wrap your items to TouchableOpacity, TouchableWithoutFeedback and TouchableHighlight (it will canceled all events).   
### `clickOnRow`
Allow to add your custom event on row press. It will be canceled whet editing mode is on.
### `removeRow`
Allow to add remove action for list items. 
### `onRefresh`
Allow to add refresh action for list items. 
### `preventSelectingActions`
Do not apply selecting view for this list. For example whent it is nessessary to check writes for editing
### `iconWidth`
Size of icon (when select item). 
### `iconStyles`
Extra styles for icon. 
### `emptyListText`
Add custom text when your list is empty (default : `No items`)
