# Formatting

- GitHub markdown
  - emojies & icons:
    [webfx](https://www.webfx.com/tools/emoji-cheat-sheet/)
    [fa](https://fontawesome.com/v4/icons/)
  - [frontmatters](https://docs.github.com/en/contributing/writing-for-github-docs/using-yaml-frontmatter)
  - [diagrams](): [Diag-aC](https://github.com/HariSekhon/Diagrams-as-Code)
    - `mermaid`: [live edit](https://mermaid.live/edit)
- org-mode
  - [test](https://github.com/novoid/github-orgmode-tests/blob/master/README.org)

# How To in *nix

- parse image text
  ```bash
    sudo apt install tesseract-ocr tesseract-ocr-eng tesseract-ocr-ukr
    find . -name "*.png" | xargs -I '{}' -d '\n' tesseract "{}" "{}" -l eng
  ```

# IDEs

## Emasc

- diagrams: [mermaid](https://github.com/arnm/ob-mermaid)