This repository started it's life as the Oscilloplasm module which existed for a brief time in the Wiard 300 Series format, and has now expanded into a complete and separate take on the audio synthesis paradigm based continuous computing techniques that occur in the quantum domain. For non-commercial use only, e.g. education, DIY.

Modulation oscillator is a self stablizing sine wave based around a trig identity for instant in the loop gain correction. Basic sine wave (harmonic oscillator) equation is:

$$
\frac{d^2x}{dt^2} + \omega^2 x = 0
$$

Where the second differential x'' (with respect to time) is passed through two voltage controlled integrators, and the inversion of the x output connected to the input to solve.  Here, ω = 2πf which is the angular frequency of the sine wave.

The trig identity used is:

$$
sin^2 + cos^2 - 1 = 0
$$

Which generates a real time error value, and out of phase sinusoidal outputs of the second harmonic. The complete equation with stabilization is:

$$ \lambda^2 - 2k \epsilon \lambda + (\omega^2 + k^2 \epsilon^2) = 0 $$


Output oscillator is a variable harmonic wavetable that solves Legendre's Ordinary Differential Equation in real time:

$$
(1 - t^2) \frac{d^2x}{dt^2} - 2t \omega \frac{dx}{dt} + (\omega^2 - l(l+1))x = 0
$$

Where L represents the azimuthal quantum number, thus generating polynomial functions in a completely novel (and sometimes frustrating) way.

The stabilization technique in this oscillator is also state of the art, although there is a compromise between harmonic distortion and ampltiude distortion. Ampltitude distortion as the RMS to DC converter gets stuck in a modulation loop is probably the more destructive force here for audio work. It can be mitigated by avoiding rapid changes in oscillator frequency, perhaps by using a slew limiter on your seqeuncer.

Output oscillator uses four quadrant multipliers and is designed for through zero behaviour.



[![DOI](https://zenodo.org/badge/721372010.svg)](https://doi.org/10.5281/zenodo.15828937)

