# getANSIfrequencies
Matlab function to obtain the array of frequencies in octave bands or fractional octave bands.

According to the standards ANSI s1.11-2004 and IEC 61260-1-2014.

Return the central frequencies and its edges (upper and lower).

It works similar to matlab's internal function:
```matlab
[cf,g] = signal.internal.octave.getListOfANSICenterFrequencies(limits, b)
```
But `getANSIfrequencies` returns both center frequencies and edges.

## Use

```matlab
[fc,fl,fu] = getANSIfrequencies(b,limits,normalized)
```

The first input is the bandwidth:

- `b=1` One-octave band.
- `b=3` Third-octave band.
- `b=2` Half-octave band.
- `b=3/2` 2/3-octave band.
- `b=24` 1/24-octave band.


The second input is the limits of the array, by default frequencies between 12Hz and 20kHz are generated, enter another value if you need it or leave it empty to use the default value.

The third input only affects when the value of `b` is 1 or 3. It indicates whether you want the normalized or calculated frequencies. By default they are returned normalized (`true`).

**One-octave band normalized frequencies:**

  `fc = [16	31.5 63	125	250	500	1000 2000 4000 8000 16000]`
  
**One-octave band calculated frequencies:**

  `fc = [15.85 31.62 63.1 125.89 251.19 501.19 1000 1995.26 3981.07 7943.28 15848.93]`



## Examples of use

```matlab
% To get one-octave frequencies normalized between [12, 20000]
[fc,fl,fu] = getANSIfrequencies(1)
```

```matlab
% To get one-octave frequencies normalized between [125, 8000]
[fc,fl,fu] = getANSIfrequencies(1,[125,8000])
```

```matlab
%   To get one-octave frequencies standard between [12, 20000]
[fc,fl,fu] = getANSIfrequencies(1,[],false)
```
