# SinLlama Dataset Visual Analysis

Statistical and visual analysis of the SinLlama Sinhala corpus for
font-image and pixel-based language-model research.

## Analysis

The project examines:

- Dataset row length
- Word-count distribution
- Unicode code-point distribution
- Sinhala grapheme-cluster distribution
- Sinhala Unicode character frequencies
- Rendered font width
- Wrapped image-line distribution
- Font glyph coverage

## Dataset

Hugging Face dataset:

`polyglots/MADLAD_CulturaX_cleaned`

## Repository Structure

- `notebooks/` – Google Colab notebooks
- `figures/` – generated graphs
- `reports/` – statistical CSV results
- `samples/` – representative Sinhala font images

## Key Findings

- **Top characters:** `U+0DCA` (SINHALA SIGN AL-LAKUNA) is the single most frequent Sinhala-block Unicode character; several vowel signs and common letters follow. See [figures/top_sinhala_characters.png](figures/top_sinhala_characters.png).
- **Word-count distribution:** The dataset is skewed toward shorter rows with a long tail of longer examples. See [figures/word_count_distribution.png](figures/word_count_distribution.png).
- **Grapheme distribution:** Grapheme-cluster frequencies are uneven — a relatively small set of graphemes covers a large portion of tokens. See [figures/grapheme_distribution.png](figures/grapheme_distribution.png).
- **Rendered widths & pixel metrics:** Rendered image widths vary considerably and correlate with grapheme length; longer grapheme sequences generally produce wider images. See [figures/rendered_width_distribution.png](figures/rendered_width_distribution.png) and [figures/graphemes_vs_pixel_width.png](figures/graphemes_vs_pixel_width.png).
- **Wrapped lines:** Many samples fit in a single line while longer examples wrap to multiple lines; monitor wrapped-line counts when designing image-based models. See [figures/wrapped_line_count_distribution.png](figures/wrapped_line_count_distribution.png).
- **Source & codepoint concentration:** The corpus sources are unevenly distributed and Unicode codepoints concentrate in the Sinhala block. See [figures/source_distribution.png](figures/source_distribution.png) and [figures/codepoint_distribution.png](figures/codepoint_distribution.png).
- **Practical implication:** Frequent combining marks and variable rendered widths imply models and OCR/font pipelines must robustly handle combining diacritics and variable image widths. Check font coverage via `reports/characters_missing_from_font.csv`.
