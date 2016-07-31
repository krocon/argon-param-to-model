#&lt;argon-param-to-model&gt;

## Usage

This polymer element extracts the parameters from url and copies these values to the local model.

#### Example 1

```

http://localhost:8121/reader.html?epub=../0/file/demo.epub
...
<argon-param-to-model/>  <!-- paramstring will be auto extracted from url -->
...
ready: function () {
  console.info('epub', this.epub);
}
 
```

