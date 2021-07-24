# shrinkpdf

`shrinkpdf` is a simple Bash script which attempts to reduce the size of a PDF file
by calling GhostScript with some parameters that would otherwise be hard to memorize.

Usage:	`shrinkpdf input.pdf output.pdf`

where `input.pdf` is the path to an input PDF (or PostScript) file and `output.pdf` is 
the desired output PDF.

Given the above arguments, `shrinkpdf` will attempt to use GhostScript (`gs`) to reduce 
the size of the input file **without compromising its quality**.
This is accomplished by the following means:

* lossless compression of images in the input file,
* de-duplicating embedded fonts and images,
* introducing a more efficient internal organization of the PDF.

However, if the input PDF file is already highly compressed or very efficiently structured,
then `shrinkpdf` may not be able to further reduce its file size.
In such case, `shrinkpdf` will print a suitable message to stdout. 

In any case, the input file is not modified; only `output.pdf` is ever written to.

## Authorship and license information

`shrinkpdf`: (C) Copyright 2021 by Rafał M. Siejakowski

The program is distributed under the terms of the BSD 3-Clause License.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

