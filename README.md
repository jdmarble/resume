# `resume.jdmarble.com`

## Local Build

Check spelling using [`pyspelling`](https://facelessuser.github.io/pyspelling/#installing):

```sh
sudo dnf install hunspell
pip install pyspelling
pyspelling -c .spellcheck.yml
```

Render as HTML and PDF using [`markdown-resume`](https://github.com/there4/markdown-resume):

```sh
mkdir public
podman run -v ${PWD}:/resume:z there4/markdown-resume md2resume html --template readable resume.md ./public
podman run -v ${PWD}:/resume:z there4/markdown-resume md2resume pdf --template readable resume.md ./public
```

Check for leaking metadata:

```sh
pdfinfo *.pdf
```
