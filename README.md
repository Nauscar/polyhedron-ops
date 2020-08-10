# Polyhedron Operators

This crate implements the [Conway Polyhedral
Operators](http://en.wikipedia.org/wiki/Conway_polyhedron_notation)
and their extensions by [George W. Hart](http://www.georgehart.com/)
and others.

This is an experiment to improve my understanding of iterators
in Rust. It is based on Hart’s OpenSCAD code which, being
functional, lends itself well to translation into functional Rust.

![Some brutalist Polyhedron, rendered with 3Delight|ɴsɪ](polyhedron.jpg)

## Supported Operators

- [x] kN - kis on N-sided faces (if no N, then general kis)
- [x] a - ambo
- [x] g - gyro
- [x] d - dual
- [x] r - reflect
- [x] e - explode (a.k.a. expand, equiv. to aa)
- [ ] b - bevel (equiv. to ta)
- [x] o - ortho (equiv. to jj)
- [x] m - meta (equiv. to k3j)
- [ ] tN - truncate vertices of degree N (equiv. to dkNd; if no N, then truncate all vertices)
- [x] j - join (equiv. to dad)
- [x] s - snub (equiv. to dgd)
- [ ] p - propellor
- [ ] c - chamfer
- [ ] w - whirl
- [ ] q - quinto

## Playing

While I work on this crate there is a binary
that allows me to test things.

```
cargo run --release
```

### Keyboard Commands

Use keys matching the operator name from the above
list to apply.

Use `Up` and `Down` to adjust the parameter of the
the last operator.
Combine with `Shift` for 10× the change.

`Delete` undoes the last (and only the last)
operation.

Press `R` to render with 3Delight (requires a
[3Delight|ɴsɪ installation](https://www.3delight.com/download)).
Combine with `Shift` to render with 3Delight Cloud.

Press `Space` to save as `$HOME/polyhedron.obj`.

I use `kiss3d` for realtime preview which is
close to the metal enough to limit meshes to
65k vertices. This means the preview will be
broken if your mesh hits this limit.

Export & render will always yield a correct OBJ though.
Which you can view in Blender or another DCC
app. 

The app may crash though if your graphics driver
doesn't handle such ill-defined meshes gracefully. :)
