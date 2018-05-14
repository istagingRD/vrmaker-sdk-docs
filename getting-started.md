# Getting started

## Instructions

### Installation

Choose [Krpano ](https://krpano.com/)or [A-frame](https://aframe.io/) as your panorama viewer and include its script \(it should be placed before `vrmaker-sdk.js`\).

{% hint style="info" %}
If you want to use Krpano as your viewer, you can use the free version with watermark to demo. Otherwise, you need to purchase a Krpano license.
{% endhint %}

```markup
// purchase a KRPano license and use the paid version of the JS file in your project
<script type=text/javascript src="krpano.min.js"></script>
// A-frame (free/open source)
<script type=text/javascript src="aframe.min.js"></script>
```

Then import vrmaker by es6 in your project. 

```text
import VRMaker from 'vrmaker'
```

Or use [VR Maker SDK cdn ](https://www.istaging.com/sdk/vrmaker.js)include it in your project:

```javascript
<script src="https://www.istaging.com/sdk/vrmaker.js"></script>
```

Finally, initialize the `VRMaker` object \(don't forget do create a `div` with an `id`\):

```javascript
<body>
  <div id="vrmaker"></div>
</body>

<script>
  // Init krpano(recommended) or aframe
  var viewer = new VRMaker.AframeViewer()
  // var viewer = new VRMaker.KrpanoViewer()
  viewer.init({
    el: document.getElementById('#vrmaker')
    panoramas: // Fetched with VR Maker API you upload
  })
</script>
```

{% hint style="info" %}
You can also hard-code the panorama Array. For example:

```text
panoramas: [{
  panoramaId: '1',
  panoramaName: 'a', 
  panoramaIndex: 0
  downloadLink: 'example.png',
  panoramaRotation: 0
}, {
  panoramaId: '2',
  // etc ...
}]
```
{% endhint %}

### Result

![](.gitbook/assets/download-3.png)

### Example

Clone [https://github.com/istagingRD/vrmaker-sdk](https://github.com/istagingRD/vrmaker-sdk) and check it in examples / dev folder.

```text
npm install

npm start

// You can also check webpack dev server
npm run dev
```

### Live example

[https://livetour.istaging.com/58217f61a22b9d0067e06d7c?ui=true](https://livetour.istaging.com/58217f61a22b9d0067e06d7c?ui=true)

