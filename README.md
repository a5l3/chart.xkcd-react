# chart.xkcd-react
## React wrapper around [chart.xkcd](https://github.com/timqian/chart.xkcd)
[![](https://raw.githubusercontent.com/timqian/images/master/20190819131226.gif)](https://timqian.com/chart.xkcd/)

docs for configurations you can find in the official library [page](https://timqian.com/chart.xkcd/)

## Dependencies
`chart.xkcd@^1.0.7` must be installed to use this library

## Quick Start

```
yarn add chart.xkcd-react
```


```js
import React from 'react';
import chartXkcd from 'chart.xkcd';
import { Line, Bar, Pie, XY } from "chart.xkcd-react"

const App = () => (
  <div>
    <div>
      <Line 
        config={{
          title: 'Monthly income of an indie developer', // optional
          xLabel: 'Month', // optional
          yLabel: '$ Dollors', // optional
          data: {
            labels: ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10'],
            datasets: [{
              label: 'Plan',
              data: [30, 70, 200, 300, 500, 800, 1500, 2900, 5000, 8000],
            }, {
              label: 'Reality',
              data: [0, 1, 30, 70, 80, 100, 50, 80, 40, 150],
            }],
          },
          options: { // optional
            yTickCount: 3,
            legendPosition: chartXkcd.config.positionType.upLeft
          }
        }}/>

      <Bar
        config={{
          title: 'github stars VS patron number', // optional
          // xLabel: '', // optional
          // yLabel: '', // optional
          data: {
            labels: ['github stars', 'patrons'],
            datasets: [{
              data: [100, 2],
            }],
          },
          options: { // optional
            yTickCount: 2,
          },
        }}
      />

      <Pie
        config={{
          title: 'What Tim made of', // optional
          data: {
            labels: ['a', 'b', 'e', 'f', 'g'],
            datasets: [{
              data: [500, 200, 80, 90, 100],
            }],
          },
          options: { // optional
            innerRadius: 0.5,
            legendPosition: chartXkcd.config.positionType.upRight,
          },
        }}
      />

      <XY 
        config={{
          title: 'Pokemon farms', //optional
          xLabel: 'Coodinate', //optional
          yLabel: 'Count', //optional
          data: {
            datasets: [{
              label: 'Pikachu',
              data: [{ x: 3, y: 10 }, { x: 4, y: 122 }, { x: 10, y: 100 }, { x: 1, y: 2 }, { x: 2, y: 4 }],
            }, {
              label: 'Squirtle',
              data: [{ x: 3, y: 122 }, { x: 4, y: 212 }, { x: -3, y: 100 }, { x: 1, y: 1 }, { x: 1.5, y: 12 }],
            }],
          },
          options: { //optional
            xTickCount: 5,
            yTickCount: 5,
            legendPosition: chartXkcd.config.positionType.upRight,
            showLine: false,
            timeFormat: undefined,
            dotSize: 1,
          },
        }}
      />
    </div>
  </div>
);

export default App;


```