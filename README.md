# veheeavis

[veheeavis](https://zongl.github.io/VehEeaVis-Demo/) is a JavaScript library for visualizing Vehicle Electrical/Electronic Architectures(EEA).

**veheeavis** = Vehicle Electrical/Electronic Architecture Visualizer

[![npm](https://img.shields.io/github/release/ZongL/VehEeaVis-Demo)](https://www.npmjs.com/package/veheeavis)
[![open issues](https://img.shields.io/github/issues-raw/ZongL/VehEeaVis-Demo)](https://github.com/ZongL/VehEeaVis-Demo/issues)
[![last commit](https://img.shields.io/github/last-commit/ZongL/VehEeaVis-Demo)](https://github.com/ZongL/VehEeaVis-Demo/commits/main/)
[![downloads](https://img.shields.io/npm/dw/veheeavis.svg)](https://www.npmjs.com/package/veheeavis)


Read more about veheeavis at [VehEeaVis-Demo](https://zongl.github.io/VehEeaVis-Demo/)

The library can be installed by running:

```bash
$ npm install veheeavis
```


## Sample

The sample demonstrates the construction of a graph representing the electrical architecture of a Cybertruck.

```html
<body>
  <h1>veheeavis Example</h1>
  <h2>Cybertrcuk-EEA</h2>
  <div id="diagram"></div>
  <!--  import veheeavis.js -->
  <script src="veheeavis.min.js"></script>
  <script>
    const jsonData = {
      modules: [
        { id: "1", name:"AutopilotECU", type: "ECU", position: { x: 350, y: 50 , width: 150, height:100, color: '#ccc'},
          leftArray: [{portid: "leftport0", portcolor:0},{portid: "leftport1", portcolor:1}],
          rightArray: [{portid: "rightport0", portcolor:0},{portid: "rightport1", portcolor:1}],
          topArray: [{portid: "topport0", portcolor:0}],
          bottomArray: [{portid: "bottomport0", portcolor:0},{portid: "bottomport1", portcolor:1}]
        },
        { id: "2", name:"LeftController", type: "ECU", position: { x: 100, y: 150 , width: 150, height:60, color: '#ccc'},
          leftArray: [],
          rightArray: [{portid: "rightport0", portcolor:0},{portid: "rightport1", portcolor:1}],
          topArray: [],
          bottomArray: []
        },
        { id: "3", name:"RightController", type: "ECU", position: { x: 550, y: 160 , width: 150, height:80, color: '#ccc'},
          leftArray: [{portid: "leftport0", portcolor:0},{portid: "leftport1", portcolor:1},{portid: "leftport2", portcolor:0}],
          rightArray: [{portid: "rightport4", portcolor:0},{portid: "rightport5", portcolor:1}],
          topArray: [],
          bottomArray: [{portid: "bottomport4", portcolor:0},{portid: "bottomport5", portcolor:1}]
        },
        { id: "3", name:"RearController", type: "ECU", position: { x: 350, y: 300 , width: 150, height:80, color: '#ccc'},
          leftArray: [{portid: "leftport0", portcolor:0}],
          rightArray: [{portid: "rightport4", portcolor:0},{portid: "rightport5", portcolor:1}],
          topArray: [{portid: "topport4", portcolor:0},{portid: "topport5", portcolor:1}],
          bottomArray: []
        }
      ],
      connections: [
        { from: "AutopilotECU", to: "LeftController" ,fromPort: "leftport0",toPort:"rightport0",points:[10,20,]}, 
        { from: "AutopilotECU", to: "RightController", fromPort: "rightport0",toPort:"leftport0"}
      ]
    };

    const myveheeavis = new veheeavis.Ploteeavis({
      container: '#diagram',
      data: jsonData,
      styles: {
        module: {
          width: 150,
          height: 100,
          color: '#ccc'
        },
        connection: {
          color: '#000',
          width: 2
        }
      }
    });
  </script>
</body>
```

## Support

please visit [contact form](https://zongl.github.io/).

## License

The veheeavis [software license](https://your-project-url.com/license).

Copyright@ ZongL