---
layout: bidder
title: SpotIM
description: Prebid SpotIM Bidder Adapter
multiformat_supported: will-bid-on-any
pbjs: true
biddercode: spotIM
media_types: banner, video
schain_supported: true
gdpr_supported: true
usp_supported: true
floors_supported: true
userIds: all
gvl_id: 280
---

### Note

To use this adapter and for additional information, please contact: 

This adapter requires setup and approval before being used. 

### Bid Parameters

#### Banner, Video

{: .table .table-bordered .table-striped }
| Name | Scope | Type | Description | Example
| ---- | ----- | ---- | ----------- | -------
| `org` | required | String |  The org ID, as provided by your representative  | "YOUR-ORG-ID"
| `floorPrice` | optional | Number |  Minimum price in USD. <br/><br/> ATTENTION:<br/> Misuse of this parameter can impact revenue | 1.30
| `placementId` | optional | String |  A unique placement identifier  | "112233"
| `testMode` | optional | Boolean |  Parameter to activate test mode  | false

## Example
```javascript
var adUnits = [{
  code: 'banner-div',
  mediaTypes: {
    banner: {
      sizes: [
        [160, 600],
        [120, 600]
      ]
    }
  },
  bids: [{
    bidder: 'spotIM',
    params: {
      org: 'YOUR-ORG-ID', // Required
      floorPrice: 1.3, // Optional
      placementId: '112233', // Optional
      testMode: true // Optional
    }
  }]
},
  {
    code: 'dfp-video-div',
    sizes: [
      [640, 480]
    ],
    mediaTypes: {
      video: {
        playerSize: [
          [640, 480]
        ],
        context: 'instream'
      }
    },
    bids: [{
      bidder: 'spotIM',
      params: {
        org: 'YOUR-ORG-ID', // Required
        floorPrice: 2.5, // Optional
        placementId: '112233', // Optional
        testMode: true // Optional
      }
    }]
  }
];
```

### Configuration
SpotIM recommends setting UserSync by iframe for monetization.