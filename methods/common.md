# Common

## init

#### Arguments

\(HTMLElement\): The element that will be used to generate the panorama viewer.  
\(Array\): The panoramas to display in the panorama viewer.  
`panoramaId (String):` Unique ID of panorama.   
`panoramaName (String)`:   
`panoramaIndex (Number)`: The position of the panorama \(e.g. `0` is the first panorama\).  
`downloadLink`: The URL containing the image of the panorama.

#### Example

```javascript
VRMaker.init({
  el: document.getElementById('#vrmaker')
  panoramas: // Array fetched with VR Maker API or your own node server
})
```

{% hint style="info" %}
 If you want to use KRPano as your viewer, you can use the free version with watermark to demo. Otherwise, you need to purchase a KRPano license.
{% endhint %}

## initEl

#### Arguments

\(HTMLElement\): The element that will be used to generate the panorama viewer.

#### Example

```javascript
const el = document.getDocumentByID('#vrmaker')

VRMaker.initEl(el)
```

## initPanoramas

#### Arguments

\(Array\): The panoramas to be displayed in the panorama viewer.

#### Example

```javascript
const panoramas = [{ panoramaId: '1' }, { panoramaId: '2' }]

VRMaker.initPanoramas(panoramas)
```

## addPanoramas

#### Arguments

\(Array\): The panoramas to be added to the original array.

#### Example

```javascript
const panoramas = [{
  panoramaId: '1'
}, {
  panoramaId: '2'
}]

VRMaker.addPanoramas(panoramas)
```

## updatePanorama

#### Arguments

\(String\): ID of the panorama to be selected.  
\(Object\): The panoramas to be added to the original object.

#### Example

```javascript
VRMaker.updatePanorama('1', { panoramaIndex: 21 })
```

## updateCurrentPanorama

#### Arguments

\(Object\): The panoramas to be added to the original object.

#### Example

```javascript
VRMaker.updateCurrentPanorama({ panoramaIndex: 21 })
```

## removePanorama

#### Arguments

\(String\): ID of the panorama to be selected.

#### Example

```javascript
VRMaker.removePanorama('1')
```

## selectPanorama

#### Arguments

\(String\): ID of the panorama to be selected.

#### Returns

\(Object\): Found panorama. Same as the one gotten with `getCurrentPanorama`.

#### Example

```javascript
const id = '1'

VRMaker.selectPanorama(id)
// => { panoramaId: '1' } 
```

## getEl

#### Returns

\(HTMLElement\): Element set with `initEl` .

#### Example

```javascript
VRMaker.getEl()
// => <div id="vrmaker"></div>
```

## getPanoramas

#### Returns

\(Array\): Panoramas set with `initPanoramas`.

#### Example

```javascript
VRMaker.getPanoramas()
// => [{ panoramaId: '1' }, { panoramaId: '2'}]
```

## getCurrentPanorama

#### Returns

\(Object\): Panorama set with `selectPanorama()`.

#### Example

```javascript
VRMaker.getCurrentPanoramas()
// => [{ panoramaId: '1' }, { panoramaId: '2'}]
```



