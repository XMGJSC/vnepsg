# This lib for get vn projection from epsg code

## Installation
```shell
yarn add epsgvn proj4
```

## How to use
```js
import epsg from 'epsgvn';
import proj from 'proj4';

type EPSGType = keyof typeof epsg;

export const projectionConvert = ({
  from,
  to,
  latitude,
  longitude,
}: {
  from: EPSGType;
  to: EPSGType;
  latitude: number;
  longitude: number;
}) => {
  const [lon, lat] = proj(epsg[from], epsg[to], [longitude, latitude]);
  return {longitude: lon, latitude: lat};
};
```
