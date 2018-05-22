---
description: 'Default has "auto rotation", "change animation", "cubemap"'
---

# VR Viewer

#### Arguments

init vrviewer sdk like this code:

```javascript
import 'vrviewer'

VRViewer.init({
  el: '#vrviewer-sdk',
  lang: 'zh-cn',
  panoCollection: fakePanoCollection,
  panoramas: fakePanoramas,
  setting: {
    autoRotateSetting: {
      active: true,
      revert: false,
      rotateDuration: 200000,
      restartTime: 20000
    },
    gyroSetting: {
      active: false
    },
    krpanoSetting: {
      mwheel: true,
      focus: false
    },
    tripodSetting: {
      image: 'https://www.istaging.com/sdk/logo-tripod.png',
      size: 60
    },
    hideUISetting: {
      hideCollectionInfo: false,
      hidePanoramaList: false,
      hideFloorplan: false,
      hideFullscreen: false,
      hideLoading: true,
      hideMarkerInfo: false
    },
    shareSetting: {
      shareUrl: 'https://www.istaging.com/'
    }
  }
})
```

This function doesn't return anything.  `el` and `panoramas` should be previously passed to `init` .

\(Object\): The configuration settings for krpano.
`autoRotateSetting (Object)`:
Default: `{ active: true, revert: false, rotateDuration: 200000, restartTime: 20000 }` .

| Name | Description | Default value |
| --- | --- | --- |
| active | Start auto rotate or not, it will auto disabled in VR mode or Gyroscope is on | true |
| revert | Revert rotate destination | false |
| rotateDuration | How many mini-second when auto rotate a circle | 200000 |
| restartTime | When auto rotate stopped, how long will it auto restart? \(ms\) | 20000 |

`gyroSetting` : Default: `{ active: false }`.

Name

| Name | Description | Default value |
| --- | --- | --- |
| active | Can mobile use gyroscope? | false |

`krpanoSetting`: Default: `{ mwheel: true, focus: false }`.

Description

| Name | Description | Default value |
| --- | --- | --- |
| mwheel | User use mouse wheel to zoom in or out | true |
| focus | Auto focus on the generated div if krpano is ready | false |

`tripodSetting` : Default: `{ image: '', size: 60 }`.

| Name | Description | Default value |
| --- | --- | --- |
| image | Image url for tripod | '' |
| size | Tripod size | 100 |

`hideUISetting` : Default: `{ hideCollectionInfo: false, hidePanoramaList: false, hideFloorplan: false, hideFullscreen: false, hideLoading: true, hideMarkerInfo: false }`.
You can hide it and do yourself UI with some VRViewer sdk methods (methods is still in developing)

| Name | Description | Default value |
| --- | --- | --- |
| hideCollectionInfo | Hide collection info UI | false |
| hidePanoramaList | Hide panorama list UI | false |
| hideFloorplan | Hide floorplan UI | false |
| hideFullscreen | Hide fullscreen UI | false |
| hideLoading | Hide loading UI | false |
| hideMarkerInfo | Hide marker info UI | false |

`shareSetting` : Default: `shareUrl: 'https://www.istaging.com/'`.

| Name | Description | Default value |
| --- | --- | --- |
| shareUrl | Genera QR Code in viewer | 'https://www.istaging.com/' |

#### Example {#example}

```javascript
const panoramas = [{ panoramaId: '1' }, { panoramaId: '2' }]​

VRViewer.init({
  el: '#vrmaker-krpano',
  panoramas,
  setting: {
    autoRotateSetting: {
      active: true,
      revert: false,
      rotateDuration: 200000,
      restartTime: 20000
    },
    gyroSetting: {
      active: false
    },
    krpanoSetting: {
      mwheel: true,
      focus: false
    },
    tripodSetting: {
      image: 'https://www.istaging.com/sdk/logo-tripod.png',
      size: 60
    },
    hideUISetting: {
      hideCollectionInfo: false,
      hidePanoramaList: false,
      hideFloorplan: false,
      hideFullscreen: false,
      hideLoading: false,
      hideMarkerInfo: false
    },
    shareSetting: {
      shareUrl: 'https://www.istaging.com/'
    }
  }
})
```

## destroy

To remove current generated VR Viewer.

#### Example {#example}

```javascript
VRViewer.destroy()
```

## onTogglePanoramasList

Toggle show/hide panoramas list in UI

#### Example {#example}

```javascript
VRViewer.onTogglePanoramasList()
```
