# freeverb

A Rust implementation of the Freeverb algorithm.

## About Freeverb

Freeverb was originally written in C++ by "Jezar at Dreampoint", and was released into the public domain in June 2000. It is now widely used in various incarnations in multiple software packages.

- [Analysis of the Freeverb algorithm](https://ccrma.stanford.edu/~jos/pasp/Freeverb.html)
- [More information and a link to original C++ source](http://freeverb3vst.osdn.jp/sites.shtml)

## About the `freeverb` crate

This implementation of Freeverb in Rust is an almost direct conversion of the original source, created as a demonstration project for a [talk Ian Hobson gave about Rust at the Audio Developer Conference 2018](https://www.youtube.com/watch?v=Yom9E-67bdI).

There are a couple of (intentional) differences to the original implementation:

- Delay line buffers are dynamically allocated for simplicity. This may have a performance impact; making the buffer static with generic constants is an alternative.
- 64 bit processing is used internally whereas the original is 32 bit. Making the sample type configurable is an option.
