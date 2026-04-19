# graphical

Higher-level plot primitives — line + shaded bounds, Gantt charts, phase histograms, 3-D wireframes.

Part of the Prerau Lab [`utils`](https://github.com/preraulab/utils) meta-repository. Can also be used standalone.

## When to use which

| Task | Use |
|---|---|
| Line plot with shaded confidence / error bounds | `shadebounds` |
| Circular / phase histogram (0–2π) | `phasehistogram` |
| Gantt-style timeline of events | `gantt` |
| Grouped box-charts with sensible defaults | `group_boxchart` |
| Linear-model fit + scatter plot | `lm_plot` |
| Matrix → RGB image (arbitrary colormap) | `mat2rgbpic` |
| Plot highlighted above/below a threshold | `threshold_plot` |
| Horizontal "number line" with a range marker | `range_numberline` |
| 3-D wireframe surface | `wireframe` |
| Smooth-and-decimate for fast plotting of very long signals | `conv_downsample` |

## Examples

```matlab
% Line + shaded confidence band
[m, sem] = grpstats(y, group, {'mean', 'sem'});
shadebounds(x, m, m+sem, m-sem);

% Phase histogram
phasehistogram(angle(hilbert(signal)), 36);

% Downsample for plotting a long signal
N = 1e6;
x = (1:N)/Fs;
y = randn(1, N);
plot(conv_downsample(x, 5000), conv_downsample(y, 5000));
```

## Function list

`conv_downsample`, `gantt`, `group_boxchart`, `lm_plot`, `mat2rgbpic`, `phasehistogram`, `range_numberline`, `shadebounds`, `threshold_plot`, `wireframe`

See `help <function>` at the MATLAB prompt for the full docstring of each.

## Install

```matlab
addpath('/path/to/graphical');
```

## Dependencies

MATLAB R2020a+. Signal Processing Toolbox (for Hilbert transform used by `phasehistogram`).

## License

BSD 3-Clause. See [`LICENSE`](LICENSE).
