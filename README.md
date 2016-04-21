## About

This is a mandelbrot image renderer written in Go. It's using Go's concurrent and parallel programming feature called *goroutines*. The output is highly customizable and the rendered mandelbrot set color palette is very adaptive due to the various color palettes (these can be extended easily) and the interpolation algorithm used to blend these colors together.

Mandelbrot images are generated by applying a mathematical function to each complex number projected in the complex plane and determining for each whether they are bounded or escapes towards infinity. The mandelbrot set is defined by the following formula: <strong>`z_{n+1} = z_n^2 + c`</strong>. 

Treating the real and imaginary parts of each number as image coordinates, pixels are colored according to how rapidly the sequence diverges, if at all.

### Install
```
go get github.com/esimov/gobrot
```

Before to run the code you need to include the project into the `GOPATH` environment variable. See the documentation: https://golang.org/doc/code.html#GOPATH
### Run
```
go run mandelbrot.go
```
<img src="https://raw.githubusercontent.com/esimov/gobrot/master/images/test5.jpg"/>
```
go run mandelbrot.go --help
```

Will give all the options supported by the renderer at the moment.

Here are some options you can try out. (The attached images are generated using the below commands.)

```
go run mandelbrot.go -palette "Hippi" -xpos -0.0091275 -ypos 0.7899912 -radius .01401245 -file "mandelbrot.png"
```
```
go run mandelbrot.go -palette "Plan9" -xpos -0.0091275 -ypos 0.7899912 -radius .01401245 -file "test2.png" -iteration 600 -step 600
```
```
go run mandelbrot.go -palette "Vivid" -xpos -0.00991275 -ypos 0.7899912 -radius .02401245 -file "test3.png" -iteration 800 -step 600 -smoothness 10 -width 1920 -height 1080
```
```
go run mandelbrot.go -palette "Hippi" -xpos -0.00275 -ypos 1.012 -radius .089999 -file "test4.png" -iteration 800 -step 600 -smoothness 10 -width 1920 -height 1080
```
```
go run mandelbrot.go -palette "Hippi" -xpos -0.00275 -ypos 0.78912 -radius .1256789 -file "test5.png" -iteration 800 -step 6000 -smoothness 10 -width 1920 -height 1080
```

By combining `-palette`, `-iteration` and `-step` values you can obtain differently colorized mandelbrot sets.

### TODO

- Generate various images with a single command
- Find dynamically the regions where a deep zoom will emerge new mandelbrot sets 

### Resources

- https://en.wikipedia.org/wiki/Mandelbrot_set
- https://en.wikibooks.org/wiki/Fractals/Iterations_in_the_complex_plane/MandelbrotSetExterior
- http://linas.org/art-gallery/escape/escape.html
- https://rosettacode.org/wiki/Mandelbrot_set
- https://youtu.be/2AZYZ-L8m9Q
