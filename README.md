# British Triathlon Open Active Data

## Endpoints
- [https://api.britishtriathlon.org/openactive/v1/events](https://api.britishtriathlon.org/openactive/v1/events) - a feed of triathlon events

## Standards
The data feed is published to conform to [OpenActive Realtime Paged Data Exchange 1.0](https://www.openactive.io/realtime-paged-data-exchange/1.0/) and [OpenActive Modelling Opportunity Data](https://www.openactive.io/modelling-opportunity-data/), using features from the [OpenActive Beta Namespace](https://www.openactive.io/ns-beta/).

**Notes**
- Our latitude/longitude values were previously saved to 2 decimal places. We have changed this to 6 decimal places now but it will take a while for all our events to be updated to the higher degree of accuracy.

## Issues, Questions and Comments
Please raise any issues, questions or comments as a [new issue in this repository](https://github.com/britishtriathlon/openactive/issues).

## Custom Data Fields 
In addition to the data fields in the [Opportunity Data Model](https://www.openactive.io/modelling-opportunity-data/), there are also some custom data fields unique to British Triathlon's implementation.

These are prefixed with "btf:" and their purpose is explained below.

| Data Field | Type | Example Value | Description |
| ---------- | ---- |-------------- | ----------- |
| btf:swimType | string | `"Open Water - Lake"` | The type of swim that is taking place. Only appears for events which have a swim stage. |
| btf:draftLegal | boolean | `true` | Whether the cycle leg of the event is draft-legal. If false, the field is not shown and so the event is draft-illegal |
| btf:componentEvent | array |  | Contains `Event` objects which are the individual stages within a race. See [github proposal](https://github.com/openactive/modelling-opportunity-data/issues/102) |
| btf:raceTypes | array | `["Super Sprint Triathlon","Sprint Distance Triathlon","Standard Distance Triathlon","Middle Distance Triathlon","Long Distance Triathlon","Duathlon","Aquathlon","Cross Triathlon","Cross Duathlon","Winter Triathlon","Childrens Triathlon","Childrens Duathlon","Childrens Aquathlon","Aquabike","GO TRI","Swim","Relay","Novice Triathlon","Mixed Team Relay"]` | Details what races are available within the event |
| btf:eventFeatures | array |`["Aid stations","Camping","Catering","Chip Timing","Distance markers","Finishers Medal","Numbered racking","Prizes","Results on website","Secure transition","Suitable for Para-tri","T-Shirt","Traffic free"]` | Specific features which are available at the event |
| btf:qualifier | boolean | `true` | Whether the event contains a Great Britain Age-Group Team qualifying race. If false, the field is not shown and so the event does not contain a qualifier |
| btf:expectedCompetitors | integer | `200` | Shows the estimated number of participants an organiser expects in their event. See [github proposal](https://github.com/openactive/modelling-opportunity-data/issues/105) |

## Changelog
| Date | Changes |
|---|---|
| 2018-12-18 | Updates to conform with the Modelling Spec V2 |
| 2018-07-03 | Initial version published |
