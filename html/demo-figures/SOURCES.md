# Demo figure sources

The figures in this folder are taken or adapted from **Vaswani et al., “Attention Is All You Need”**
(arXiv:1706.03762v7, 2 Aug 2023; NIPS 2017), <https://arxiv.org/abs/1706.03762v7>.

License: the paper's front page states: "Provided proper attribution is provided, Google hereby grants
permission to reproduce the tables and figures in this paper solely for use in journalistic or scholarly
works." They are used here only for the scholarly demo deck `../demo.html`.

They are **not** covered by this repository's MIT license.

## Figures and tables

| Local file | Paper locator | Original source | Adaptation | License | Use |
|---|---|---|---|---|---|
| `demo-figures/transformer-architecture.png` | Fig. 1 | arXiv source `Figures/ModalNet-21.png` | unchanged | paper grant (above) | Slide 4 |
| `demo-figures/arch-crop-inputs.png` | Fig. 1 (bottom) | same | cropped (x 0–1, y 0.725–1.0) | paper grant | Slide 5 |
| `demo-figures/arch-crop-encoder.png` | Fig. 1 (encoder) | same | cropped (x 0–0.48, y 0.345–0.80) | paper grant | Slide 8 |
| `demo-figures/arch-crop-decoder.png` | Fig. 1 (decoder + output) | same | cropped (x 0.50–1.0, y 0–0.745) | paper grant | Slide 9 |
| `demo-figures/scaled-dot-product-attention.png` | Fig. 2 (left) | arXiv source `Figures/ModalNet-19.png` | unchanged | paper grant | Slide 6 |
| `demo-figures/multi-head-attention.png` | Fig. 2 (right) | arXiv source `Figures/ModalNet-20.png` | bottom whitespace cropped | paper grant | Slide 7 |
| `demo-figures/attention-vis-making.png` | Fig. 3 (appendix) | arXiv source `vis/making_more_difficult5_new.pdf` | rasterized at 300 dpi with `pdftoppm`; top 36 pt trimmed as the paper's own `trim=0 0 0 36`; white margin cropped | paper grant | Slide 17 |
| `demo-figures/lr-schedule.png` | Eq. 3 | generated | plotted from Eq. 3 with the paper's $d_{\text{model}}=512$, $warmup\_steps=4000$, steps 1–100K; no values read from a figure | own work | Slide 10 |
| inline SVG (unrolled RNN) | Sec. 1 text | presenter diagram | presenter-drawn illustration of the recurrence the paper describes; the cell symbol $f$ is presenter notation | own work | Slide 2 |
| HTML table | Table 1 | `why_self_attention.tex` | re-typeset, all 4 rows; shaded row = presenter highlight | paper grant | Slide 3 |
| HTML table | Table 2 | `results.tex` | re-typeset, all 10 rows; bold exactly as in v7 source (41.29, 28.4, 41.8, $3.3\cdot10^{18}$) | paper grant | Slide 12 |
| HTML tables | Table 3 | `results.tex` | re-typeset, all 20 rows split across three slides (base+A+B; base+C; base+D+E+big). The base row is repeated on each slide for reference; bold (4.33, 26.4) as in the paper | paper grant | Slides 13–15 |
| HTML table | Table 4 | `results.tex` | re-typeset, all 12 rows; row labels verbatim incl. the paper's "el al." typo; no bold in the paper | paper grant | Slide 16 |
| HTML table | — | Sec. 5.1, 6.1–6.3 | presenter summary of protocol | — | Slide 11 |


