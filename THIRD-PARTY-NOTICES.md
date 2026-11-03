# Third-party notices - LocalDoc Kit

Every outside component the phone page (`web/filer.html`, `dist/filer-standalone.html`) and the laptop
side (`filer.py`) use, with its licence and where to get its source. Inventory: `../LEGAL-RESEARCH.md` section A
(10 Oct 2026). **`tests/notices_test.py` keeps this honest:** every package, wheel, model and CDN library named in the
page's code must have a row here, and every row in the "Phone page" tables must appear in the page's own
"Licences and privacy" fold.
**The FULL licence text of every part below** (MIT/BSD notices, Apache-2.0, MPL-2.0, LGPL-3.0 and GPL-3.0 for lamejs, the OFL, PDFium's third parties) is inside the page, in "Every licence, in full", read from each pinned release by `make_licence_texts.py` into `web/licence-texts.js` (10 Oct 2026). The privacy policy is `web/privacy.html`.

"Downloaded" means the page fetches the component, unmodified, from the address shown, the first time a tool needs
it; it is not inside the file. "Inside" means it is part of the file.

## Phone page - inside the file (dist/filer-standalone.html)

| Component | Version | Licence | Source |
|---|---|---|---|
| Fonts: Fraunces, Outfit, Chivo Mono (latin, latin-ext) | `web/fonts`, made by make_fonts.py | SIL Open Font License 1.1 (licence texts: `web/fonts/OFL-*.txt`) | https://fonts.google.com |
| pdf-lib | 1.17.1 (`web/vendor`, made by make_vendor.py, checked against the SRI cdnjs publishes) | MIT | https://github.com/Hopding/pdf-lib |
| JSZip | 3.10.1 (`web/vendor`, same check) | MIT (dual MIT or GPL-3.0; used under MIT) | https://github.com/Stuk/jszip |
| docx-preview (docxjs) | vendored | Apache-2.0 (licence text: `web/docx-preview.LICENSE.txt`) | https://github.com/VolodymyrBaydalka/docxjs |

## Phone page - downloaded when a tool first needs it

| Component | Version | Licence | Source |
|---|---|---|---|
| pdf.js | 3.11.174 | Apache-2.0 | https://github.com/mozilla/pdf.js |
| MODNet portrait matting (White background), ONNX conversion Xenova/modnet, `onnx/model_fp16.onnx` | @fa2fa546052f (pinned by SHA-256 in `web/bg-core.js`) | Apache-2.0 (the model and the conversion) | https://github.com/ZHKKKe/MODNet , https://huggingface.co/Xenova/modnet |
| transformers.js | 4.3.0 | Apache-2.0 | https://github.com/huggingface/transformers.js |
| onnxruntime-web | see leaflet-core.js ORT_VERSION | MIT | https://github.com/microsoft/onnxruntime |
| tesseract.js and tesseract.js-core | 7.0.0 | Apache-2.0 | https://github.com/naptha/tesseract.js |
| Tesseract English data (eng.traineddata, best_int) | 4.0.0 | Apache-2.0 (tessdata); npm package MIT | https://github.com/tesseract-ocr/tessdata_best |
| lamejs (@breezystack/lamejs) | 1.2.7 | LGPL-3.0 - loaded unmodified as its own file, so it can be replaced; LAME source: https://lame.sourceforge.io | https://github.com/breezystack/lamejs |
| mediabunny | 1.60.0 | MPL-2.0 - unmodified; source at the link | https://github.com/Vanilagy/mediabunny |
| Pyodide (with its micropip installer) | 0.28.3 | MPL-2.0 - unmodified; source at the link | https://github.com/pyodide/pyodide |
| p2w_reader (this app's own, `web/p2w-reader.js` from `p2w_reader.py`): pdf2docx's "fitz" calls answered from pdfminer.six, pypdf and PDFium (below). PyMuPDF (AGPL-3.0) is NOT shipped since 10 Oct 2026 | - | this app's licence | - |
| PDFium, WebAssembly build in @hyzyla/pdfium (PDF -> Word figure pictures; pinned by SHA-256 in `web/pdf2word-core.js`) | 2.1.9 | PDFium: BSD-3-Clause (Copyright 2014 The PDFium Authors). The wrapper/loader: MIT. Libraries PDFium builds in - FreeType and OpenJPEG and Little CMS were seen inside this wasm; the rest is PDFium's standard build, not confirmed for this one: FreeType (FreeType License: "Portions of this software are copyright (c) The FreeType Project (www.freetype.org). All rights reserved."), libjpeg-turbo (IJG + BSD-3-Clause + zlib: "This software is based in part on the work of the Independent JPEG Group."), OpenJPEG (BSD-2-Clause), Little CMS (MIT), zlib (zlib), libpng (libpng), AGG 2.3 (BSD-3-Clause-style), Abseil (Apache-2.0) | https://pdfium.googlesource.com/pdfium , https://github.com/hyzyla/pdfium |
| cryptography 45.0.5, cffi 1.17.1, pycparser 2.22, charset-normalizer 3.4.2, six 1.17.0 (Pyodide builds; pdfminer.six imports cryptography and charset-normalizer at load; PDF tables and PDF -> Word) | Pyodide 0.28.3's | Apache-2.0 or BSD-3-Clause (cryptography); MIT (cffi, charset-normalizer, six); BSD-3-Clause (pycparser) | https://github.com/pyca/cryptography |
| OpenSSL (Pyodide's libopenssl, under cryptography) | 1.1.1w | OpenSSL + SSLeay dual licence (BSD-style with an advertising clause; NOT the Apache-2.0 of OpenSSL 3). "This product includes software developed by the OpenSSL Project for use in the OpenSSL Toolkit (http://www.openssl.org/)". "This product includes cryptographic software written by Eric Young (eay@cryptsoft.com)" | https://github.com/openssl/openssl/blob/OpenSSL_1_1_1w/LICENSE |
| pdf2docx | 0.5.13 | MIT | https://github.com/ArtifexSoftware/pdf2docx |
| python-docx | 1.2.0 | MIT | https://github.com/python-openxml/python-docx |
| pypdf | 6.14.2 | BSD-3-Clause | https://github.com/py-pdf/pypdf |
| pdfminer.six | 20251230 | MIT | https://github.com/pdfminer/pdfminer.six |
| pdfplumber | 0.11.9 | MIT | https://github.com/jsvine/pdfplumber |
| openpyxl | 3.1.5 | MIT | https://foss.heptapod.net/openpyxl/openpyxl |
| et_xmlfile | 2.0.0 | MIT | https://foss.heptapod.net/openpyxl/et_xmlfile |
| Pyodide builds of numpy, opencv-python, lxml, fonttools, Pillow, cryptography, charset-normalizer, typing-extensions | as shipped with Pyodide 0.28.3 | upstream: numpy BSD-3, OpenCV Apache-2.0, lxml BSD-3, fonttools MIT, Pillow MIT-CMU, cryptography Apache-2.0 or BSD-3, charset-normalizer MIT, typing-extensions PSF-2.0 | https://github.com/pyodide/pyodide |
| Whisper small (onnx-community/whisper-small) | @36050c46 | Apache-2.0 (base model openai/whisper-small) | https://huggingface.co/onnx-community/whisper-small |
| Silero VAD (onnx-community/silero-vad) | @e71cae96 | MIT | https://huggingface.co/onnx-community/silero-vad |
| IndicTrans2 en-indic 200M int8 (hari31416/indictrans2-en-indic-dist-200M-ONNX-int8) | @1eaa43a3 | MIT (base model ai4bharat IndicTrans2) | https://huggingface.co/hari31416/indictrans2-en-indic-dist-200M-ONNX-int8 |

## Data and text inside the page

| Component | Licence | Source |
|---|---|---|
| Wiktionary language tags (medical word roots) | CC BY-SA 4.0 - attribution in `web/medroots-SOURCE.md` | https://en.wiktionary.org |
| MedlinePlus "Understanding Medical Words" word parts | US federal government work | https://medlineplus.gov |
| Norvig word counts (count_1w) | no licence stated by the source | https://norvig.com/ngrams/ |
| Jan Aushadhi product list (PMBI) | no terms stated by the source | https://www.pmbi.co.in |
| National List of Essential Medicines 2022 (CDSCO) | no terms stated by the source | https://cdsco.gov.in |
| Short quotations from government notices, Acts and Rules (KEA, MCC, MMCRI, UPSC, RTI Act, Supreme Court handbook, Bhoomi, PM-KISAN, KERC, RBI) | quoted with their source named beside each quote | each `web/*-SOURCE.md` |

## Outside services the user can choose to call

None of these is called unless the user taps the tool that uses it, and the page's network counter names each call.

| Service | When | What is sent |
|---|---|---|
| Open Library, Wikidata, Google Books | Book reader, "find the book" | the book title typed |
| Google Gemini, Groq | Book words, only with the user's own key | parts of the book's text |
| jsDelivr, cdnjs, PyPI files, Hugging Face | first use of a tool that needs a component above | nothing from the user's file |
| cdnjs (pdf-lib, JSZip) | every open of the development page `web/filer.html` only; the single-file copy carries both | the viewer's IP; nothing from any file |

## Laptop side (`filer.py`, not shipped in the phone page)

| Component | Licence |
|---|---|
| PyMuPDF | NOT used since 10 Oct 2026: PDF -> Word runs pdf2docx on `p2w_reader.py` (pdfminer.six MIT, pypdf, pypdfium2) in `.venv-p2w`. A developer-only `.venv-convert` keeps PyMuPDF (AGPL-3.0) to MEASURE p2w_reader against; it is never shipped or called by the app |
| pdf2docx 0.5.13, pdfminer.six 20251230 | MIT |
| python-docx, openpyxl, pdfplumber, python-pptx, faster-whisper | MIT |
| pypdf, lxml, PyAV 18.0.0, pillow-heif 1.7.0 | BSD-3-Clause (PyAV's bundled FFmpeg and pillow-heif's libheif: licence of the build not yet checked) |
| pypdfium2 5.5.0 | BSD-3-Clause or Apache-2.0 |
| Pillow | MIT-CMU |
| websocket-client | Apache-2.0 |
| pywin32 | PSF |
| External programs called, not bundled: Microsoft Word/Excel/PowerPoint (COM), FFmpeg/ffprobe, Chrome, Node | their own licences |
