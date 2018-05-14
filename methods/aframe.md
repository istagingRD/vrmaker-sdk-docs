---
description: 'Use A-Frame as your viwewr, you need to customize everything by your own.'
---

# A-Frame

## generateAframe

#### Arguments

\(Object\): the configuration object.  
`disableVR (Boolean)`: Whether to hide the VR buttons. Default: `false`.  
`autoRotate (Object)`: Configuration for the camera's auto rotation. Default: `{ enabled: true, duration: 200000 }`.  
`restartTime (Number)`: How long \(in milliseconds\) should `startAutoRotate` trigger again.

{% hint style="info" %}
`el` and `panoramas` are previously set with `init()`.
{% endhint %}

#### Example

```javascript
const panoramas = [{ objectId: '1' }, { objectId: '2' }]

aframeViewer.init({
  el: document.getElementById('vrmaker'),
  panoramas
})

aframeViewer.generateAframe()
```

## changePanorama

#### Arguments

\(String\): The new image for the panorama.  
\(Callback\): Code to be ran after the image as been loaded.

{% hint style="info" %}
 The panorama to be changed is the one set with `selectPanorama`.
{% endhint %}

#### Example

```javascript
const panoramas = [{ objectId: '1' }, { objectId: '2' }]

aframeViewer.selectPanorama('1')
aframeViewer.changePanorama('http://example.com/image.png')
```

## toggleVRMode

#### Arguments

\(Object\): the configuration object.  
`(Boolean)`: Use `true` to enable VR mode and `false` to disable it. 

#### Example

```javascript
aframeViewer.toggleVRMode(true)
```

## startAutoRotate

#### Arguments

 \(Object\): the configuration object.  
`enabled (Boolean)`: If `enabled` is `false` this function won't trigger.

#### Example

```javascript
var config = {
  autoRotate: {
    enabled: true
  }
}

aframeViewer.startAutoRotate(config)
```

## stopAutoRotate

#### Arguments

 \(Object\): the configuration object.  
`restartTime (Boolean)`: How long \(in milliseconds\) should `startAutoRotate` trigger again.

#### Example

```javascript
var config = {
  autoRotate: {
    restartTime: 20000
  }
}

aframeViewer.stopAutoRotate(config)
```



