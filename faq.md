# Formatting

- GitHub markdown
  - [emojies](https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md) & icons:
    [webfx](https://www.webfx.com/tools/emoji-cheat-sheet/)
    [fa](https://fontawesome.com/v4/icons/)
    [academicons](https://jpswalsh.github.io/academicons/)[^academic_icons]
    ([CTAN](https://www.ctan.org/pkg/academicons), [github](https://github.com/jpswalsh/academicons))
  - [frontmatters](https://docs.github.com/en/contributing/writing-for-github-docs/using-yaml-frontmatter)
  - [diagrams](): [Diag-aC](https://github.com/HariSekhon/Diagrams-as-Code)
    - `mermaid`: [live edit](https://mermaid.live/edit)
- org-mode
  - [test](https://github.com/novoid/github-orgmode-tests/blob/master/README.org)

[^academic_icons]: Academic icons [github](https://github.com/jpswalsh/academicons) [GH.IO](https://jpswalsh.github.io/academicons/) [CTAN](https://www.ctan.org/pkg/academicons)

# How To in *nix

- parse image text
  ```bash
    sudo apt install tesseract-ocr tesseract-ocr-eng tesseract-ocr-ukr
    find . -name "*.png" | xargs -I '{}' -d '\n' tesseract "{}" "{}" -l eng
  ```

# IDEs

## Emasc

- diagrams: [mermaid](https://github.com/arnm/ob-mermaid)

# Rendering & publishing

- [github pages](https://pages.github.com/):
  - supported md:
    [kramdown](https://github.com/gettalong/kramdown)
    [jekyll](https://docs.github.com/en/enterprise-server@3.9/pages/setting-up-a-github-pages-site-with-jekyll/setting-a-markdown-processor-for-your-github-pages-site-using-jekyll)

# Sharing

- Kindle: [send to](https://www.amazon.com/sendtokindle)
