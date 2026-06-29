This repository started it's life as the Oscilloplasm module which existed for a brief time in the Wiard 300 Series format, and has now expanded into a complete and separate take on the audio synthesis paradigm based on continuous computing techniques that occur in the physical and non-physical domains. Here, we present both a general method to solve computing problems using electronic means, and ready made solutions to build and install yourself. The licensing is strictly for non-commercial use only, e.g. education, DIY.

The place to begin is the representation of physical phenomena as periodic information, starting in two dimensions as sound waves and following through into three dimensional particles as persistant standing wave patterns that make up our physical universe. This representation can be done in maths using differential equations, from simple linear ordinary differential equations (ODEs) that describe electron shell configurations, into complex non-linear partial differential equations (PDEs) that can describe motion in a body of water, likely with multiple flow velocities and different viscosities. At the most extreme form, a single equation might be able to describe the entire universe, for example reaction-diffusion equations can give rise to cell like growth.

The first commercially available synthesizers referenced these mathematical principles directly, but between the reverence for analog computing methods for aesthetic reasons only, and the advent of the general purpose digital computer, the capability for continuous computing (analog) techniques to solve the most complex mathematical problems has been forgotten. Setting aside the practical problem of solving these equations for a moment, it is also worth noting that this extended class of analog computing methods needs to be explored and redefined, because it is a movement directly away from the conventional structure of sound source, sound shaper, and instead sees the instrument as a dynamical system composed of states, forces, nonlinearities, and observations, and even the metaphors between the new system variables and musical concepts need to be defined, such as in manipulating attractors.

The primitive in analog computing is the state variable, which appears in both the harmonic oscillator (sine wave) and the multimode filter. Mathematically:

$$
\frac{d^2x}{dt^2} + \omega^2 x = F(t)
$$

Where, ω = 2πf is the angular frequency of the sine wave. To solve in analog form, the second differential x'' (with respect to time) is passed through two voltage controlled integrators, comprised of a variable input gain opamp and a capacitor as a memory device, with the inversion of the x output is connected to the input to solve.  

The harmonic oscillator circuit here is unique to the system, a self stablizing sine wave based around a trig identity for instant in the loop gain correction:

$$
sin^2 + cos^2 - 1 = 0
$$

Using two Gilbert Cell mulitpliers and a zener diode stabilized DC reference, this generates a real time error value which can be used to modulate the oscillator loop gain and maintain long term amplitude stability, as well as two second harmonic outputs for the sine and cosine portions of the waveform. The complete equation with stabilization is:

$$ \lambda^2 - 2k \epsilon \lambda + (\omega^2 + k^2 \epsilon^2) = 0 $$


Output oscillator is a variable harmonic wavetable that solves Legendre's Ordinary Differential Equation in real time:

$$
(1 - t^2) \frac{d^2x}{dt^2} - 2t \omega \frac{dx}{dt} + (\omega^2 - l(l+1))x = 0
$$

Where L represents the azimuthal quantum number, thus generating polynomial functions in a completely novel (and sometimes frustrating) way.

The stabilization technique in this oscillator is also state of the art, although there is a compromise between harmonic distortion and ampltiude distortion. Ampltitude distortion as the RMS to DC converter gets stuck in a modulation loop is probably the more destructive force here for audio work. It can be mitigated by avoiding rapid changes in oscillator frequency, perhaps by using a slew limiter on your seqeuncer.

Output oscillator uses four quadrant multipliers and is designed for through zero behaviour.



[![DOI](https://zenodo.org/badge/721372010.svg)](https://doi.org/10.5281/zenodo.15828937)

