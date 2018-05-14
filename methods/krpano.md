---
description: 'Default has "auto rotation", "change animation", "cubemap"'
---

# Krpano \(recommend\)

## generateKrpano {#.generateaframe()}

#### Arguments

This function doesn't return anything.  `el` and `panoramas` should be previously passed to `init` .

\(Object\): The configuration settings for KRPano.  
`autoRotateSettings (Object)`:   
Default: `{ active: true, revert: false, rotateDuration: 200000, restartTime: 20000 }` .

| Name | Description | Default value |
| --- | --- | --- | --- | --- |
| active | Start auto rotate or not, it will auto disabled in VR mode or Gyroscope is on | true |
| revert | Revert rotate destination | false |
| rotateDuration | How many mini-second when auto rotate a circle | 200000 |
| restartTime | When auto rotate stopped, how long will it auto restart? \(ms\) | 20000 |

`gyroSettings` : Default: `{ active: false }`.

Name

| Name | Description | Default value |
| --- | --- |
| active | Can mobile use gyroscope? | false |

`krpanoSettings`: Default: `{ mwheel: true, focus: false }`. 

Description

| Name | Description | Default value |
| --- | --- | --- |
| mwheel | User use mouse wheel to zoom in or out | true |
| focus | Auto focus on the generated div if krpano is ready | false |

`tripodSettings` : Default: `{ image: '', size: 60 }`. 

| Name | Description | Default value |
| --- | --- | --- |
| image | Image url for tripod | '' |
| size | Tripod size | 100 |

#### Example {#example}

```javascript
const panoramas = [{ objectId: '1' }, { objectId: '2' }]​

krpanoViewer.init({
  el: document.querySelector('#vrmaker-krpano'),
  panoramas
})

krpanoViewer.generateKrpano({
  autoRotateSettings: {
    active: true,
    revert: false,
    rotateDuration: 200000,
    restartTime: 20000
  },
  gyroSettings: {
    active: false
  },
  krpanoSettings: {
    mwheel: true,
    focus: false
  },
  tripodSettings: {
    image: 'http://i.imgur.com/xNNfJiP.jpg',
    size: 100
  }
})
```

## destroy

To remove current generated krpano viewer.

#### Example {#example}

```javascript
krpanoViewer.destroy()
```

## changePanorama

#### Arguments

\(String\): The ID of the panorama to be changed.

#### Example {#example}

```javascript
const panoramas = [{ objectId: '1' }, { objectId: '2' }]

krpanoViewer.changePanorama('1')
```

## toggleGyro

#### Arguments

\(Boolean\): The value to enable or disable the viewer's gyro.

#### Example {#example}

```javascript
krpanoViewer.toggleGyro(true)
```

## toggleVRMode

#### Arguments

\(Boolean\): The value to enable or disable the viewer's gyro.

#### Example {#example}

```javascript
krpanoViewer.toggleVRMode(true)
```

