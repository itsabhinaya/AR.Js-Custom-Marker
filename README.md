# AR.Js Custom-Marker
Basic Code for AR.js Custom Marker

1. Upload the image you want inside the black border [here](https://jeromeetienne.github.io/AR.js/three.js/examples/marker-training/examples/generator.html) (try to avoid white backgrounds).
2. Download the .patt file and the pdf file
3. Change this code in the aframe-ar.js file
```
      // honor this.data.preset
			if( _this.data.preset === 'hiro' ){
				arProfile.defaultMarkerParameters.type = 'pattern'
				arProfile.defaultMarkerParameters.patternUrl = THREEx.ArToolkitContext.baseURL+'examples/marker-training/examples/pattern-files/pattern-hiro.patt'
				arProfile.defaultMarkerParameters.markersAreaEnabled = false
			}else if( _this.data.preset === 'kanji' ){
				arProfile.defaultMarkerParameters.type = 'pattern'
				arProfile.defaultMarkerParameters.patternUrl = THREEx.ArToolkitContext.baseURL+'examples/marker-training/examples/pattern-files/pattern-kanji.patt'
				arProfile.defaultMarkerParameters.markersAreaEnabled = false
			}else if( _this.data.preset === 'area' ){
				arProfile.defaultMarkerParameters.type = 'barcode'
				arProfile.defaultMarkerParameters.barcodeValue = 1001	
				arProfile.defaultMarkerParameters.markersAreaEnabled = true
			}else {
				// console.assert( this.data.preset === '', 'illegal preset value '+this.data.preset)
			}	    
```
to this. You need to add the last else if statment.
```
      // honor this.data.preset
			if( _this.data.preset === 'hiro' ){
				arProfile.defaultMarkerParameters.type = 'pattern'
				arProfile.defaultMarkerParameters.patternUrl = THREEx.ArToolkitContext.baseURL+'examples/marker-training/examples/pattern-files/pattern-hiro.patt'
				arProfile.defaultMarkerParameters.markersAreaEnabled = false
			}else if( _this.data.preset === 'kanji' ){
				arProfile.defaultMarkerParameters.type = 'pattern'
				arProfile.defaultMarkerParameters.patternUrl = THREEx.ArToolkitContext.baseURL+'examples/marker-training/examples/pattern-files/pattern-kanji.patt'
				arProfile.defaultMarkerParameters.markersAreaEnabled = false
			}else if( _this.data.preset === 'area' ){
				arProfile.defaultMarkerParameters.type = 'barcode'
				arProfile.defaultMarkerParameters.barcodeValue = 1001	
				arProfile.defaultMarkerParameters.markersAreaEnabled = true
			}else if( _this.data.preset === 'custom' ){
				arProfile.defaultMarkerParameters.type = 'pattern'
				arProfile.defaultMarkerParameters.patternUrl = _this.data.patternUrl;
				arProfile.defaultMarkerParameters.markersAreaEnabled = false
			}else {
				// console.assert( this.data.preset === '', 'illegal preset value '+this.data.preset)
			}	    
```
4. Change the marker reference.
```
<a-marker-camera preset='custom' url='path/to/the/file.patt'></a-marker-camera>
```

In this repo you can see the example files from Ar.js modified to accomodate the custom marker.
