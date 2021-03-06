osis2usfm
=========

Python script for transforming Bible in OSIS format to USFM format.
The script transforms OSIS Bible to USFM Bible. It is assumed that the
XML structure of the OSIS file is:

    <osis>
      <osisText>
        <header>
          ... this is ignored ...
        </header>
        <div type="x-testament">
          <div type="book">
            <chapter>
              <verse>
              </verse>
              ...
            </chapter>
            ...
          </div>
        </div>
        <div type="x-testament">
          <div type="book">
            <chapter>
              <verse>
              </verse>
              ...
            </chapter>
            ...
          </div>
        </div>
      </osisText>
    </osis>

No other tags are understood, thus it is a very simple transformation.

Usage:

    python osis2usfm.py inputfile.osis

Outputs a set of files named inputfile_##_XXX.usfm where ## is the
number of the book and XXX is the id of the book.

It is also possible to give the names of the books as a separate text
file. This file should have syntax:

    GEN=Genesis
    EXO=Exodus
    ...
    XXX=Whatever name you want to give to the book
    ...

where XXX is the ID of the book.  Usage:

    python osis2usfm.py inputfile.osis booknames.txt
