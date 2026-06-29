
# ItemOut

Catalog item metadata returned by `/v1/items`.

## Properties

Name | Type
------------ | -------------
`itemId` | number
`marketHashName` | string
`phase` | string
`itemType` | string
`itemSubtype` | string
`weaponType` | string
`baseName` | string
`skinName` | string
`wearName` | string
`defIndex` | string
`paintIndex` | number
`collection` | string
`collectionImage` | string
`crates` | Array&lt;string&gt;
`cratesImages` | Array&lt;string&gt;
`releaseDate` | Date
`rarityName` | string
`rarityColor` | string
`styleName` | string
`isStattrak` | boolean
`isSouvenir` | boolean
`minFloat` | number
`maxFloat` | number
`imageUrl` | string
`supply` | number

## Example

```typescript
import type { ItemOut } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "itemId": null,
  "marketHashName": null,
  "phase": null,
  "itemType": null,
  "itemSubtype": null,
  "weaponType": null,
  "baseName": null,
  "skinName": null,
  "wearName": null,
  "defIndex": null,
  "paintIndex": null,
  "collection": null,
  "collectionImage": null,
  "crates": null,
  "cratesImages": null,
  "releaseDate": null,
  "rarityName": null,
  "rarityColor": null,
  "styleName": null,
  "isStattrak": null,
  "isSouvenir": null,
  "minFloat": null,
  "maxFloat": null,
  "imageUrl": null,
  "supply": null,
} satisfies ItemOut

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ItemOut
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


