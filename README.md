# ES6 Tracking Helper

A tracking helper built in ES6 with Google Analytics and Google Tag Manager Support built in.

## Usage

```js
import TrackingHelper, {Tracker} from 'es6-tracking-helper'

const trackingHelper = new TrackingHelper({
  availableTracker: {'gtm': Tracker.GoogleTagManager}
})
```

Use the built in click listener

```html
<a data-tracking-type="event" data-tracking-name="click-event">Track</a>
```

Or trigger the tracking via JS

```js
trackingHelper.track({type: 'event', name: 'js-triggered-event'})
```

## API

#### constructor

| Parameter | Type | Description |
|---|---|---|
| options | ``Object`` | Options object |
| options.debug | ``Boolean (false)`` | Enables debugging in the console |
| options.init | ``Boolean (true)`` | Initiate click event listener |
| options.context | ``Node (document)``  | Context for event listener |
| options.availableTracker | ``Object`` | Tracker Classes |
| options.pageName | ``String`` \| ``Boolean (false)`` | Will be prepended to event/pageview names in built in tracker |
| options.category | ``String (Global)`` | Global Category |
| options.action | ``String (Global)`` | Global Action |
| options.dataset | ``Object`` | Data attributes for event listener |
| options.dataset.type | ``String (trackingType)`` | Data attribute for type |
| options.dataset.category | ``String (trackingCategory)`` |  Data attribute for category |
| options.dataset.action | ``String (trackingAction)`` |  Data attribute for action |
| options.dataset.name | ``String (trackingName)`` |  Data attribute for name |
| options.dataset.nonInteraction | ``String (trackingNonInteraction)`` |  Data attribute for non interaction flag |

#### startTracking ⇨ ``TrackingHelper``

Start listening for clicks on nodes with tracking data attributes

*Returns*: ``TrackingHelper`` - This tracking helper instance

#### stopTracking ⇨ ``TrackingHelper``

Stop listening for clicks on nodes with tracking data attributes

*Returns*: ``TrackingHelper`` - This tracking helper instance

#### onClick

Click handler for nodes with tracking data attributes

#### add(type, method) ⇨ ``TrackingHelper``

Adds a tracking type

| Parameter | Type | Description |
|---|---|---|
| type | ``String`` | Name used to identify type in data attributes |
| method | ``String`` | Method in Tracker(s) |

*Returns*: ``TrackingHelper`` - This tracking helper instance

#### remove(type) ⇨ ``TrackingHelper``

Removes a tracking type

| Parameter | Type | Description |
|---|---|---|
| type | ``String`` | Name used to identify type in data attributes |

*Returns*: ``TrackingHelper`` - This tracking helper instance

#### track ⇨ ``TrackingHelper``

Iterates over all trackers and tries to invoke the designated tracking type

*Returns*: ``TrackingHelper`` - This tracking helper instance

## License

MIT