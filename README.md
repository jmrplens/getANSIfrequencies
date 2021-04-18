# ANSI-frequencies
Matlab function to obtain the array of frequencies in octave bands or fractional octave bands.

According to the standards ANSI s1.11-2004 and IEC 61260-1-2014.

Return the central frequencies and its edges (upper and lower).

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
