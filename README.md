SHIRLEY				Protein comparison tool

## NAME
    shirley


## SYNOPSIS
    shirley [-h] [-w WIDTH | -l LINES] [--out [{full,rbd,rbm}]] [-V] input


## DESCRIPTION
    Compare protein sequences, writing to standard output.

    -h
        display help information and exit
	
    -l, --lines
        Specify the number of lines in the output
        This option cannot be used with -w
	
    --out
        Specify output display type
        rbd - display only the receptor binding domain
        rbm - display only the receptor binding motif
        full - display the entire sequence (default)
        includes labelling of the rbd (!) and rbm (?)

    -V, --version
        display program version and exit

    -v, --verbose
        increase verbosity of display, use twice for maximum effect

    -w, --width
        Specify the width of the display in characters
        This option cannot be used with -l


## CONFIGURATION
    shirley.ini, in the same directory as shirley.py provides a persistent
    configuration.

    Configuration items are:
	
    [email]
        address - Email address for the user. This is used to identify the
        user to the Entrez API...

    [reference]
        Details of the sequence to be used as the reference, against which
        all the other sequences are compared

        name - sequence name
        rbd_start - position of the start of the receptor binding domain
        rbd_end - position of the end of the receptor binding domain
        rbm_start - position of the start of the receptor binding motif
        rbm_end - position of the end of the receptor binding motif
		

## INPUT FILE
        The input file specifies the sequences to be compared and a friendly
        name for display.

        Format for each line is: the friendly name followed by whitespace
        followed by the accession ID.

        Example:
            Wuhan-Hu-1    YP_009724390.1
	
        Friendly names may contain any printable character, but must be
        followed by at least one whitespace character.

        Placement of a '#' character at the start of the line will omit the
        sequence from comparison
		

## PREREQUISITES
        The biopython library is required, see https://biopython.org/
        To install: python -m pip install biopython
	
        The mafft program is required, see
        https://mafft.cbrc.jp/alignment/software/

	
## COMPATIBILITY
        Shirley was developed with:
        "Python 3.8.8"
        "MAFFT v7.526 (2024/Apr/26)"
        "biopython 1.83"


## RECEPTOR BINDING SECTION OF STANDARD ACCESSION ID (YP_009724390.1)
        These identifications have been provided as manual observations for
        the purpose of validating program output

        Receptor binding domain (223 characters, 319 to 542)
        RVQPTESIVRFPNITNLCPFGEVFNATRFASVYAWNRKRISNCVADYSVLYNSASFSTFKCYGVSPTKLNDLCFTNVYADSFVIRGDEVRQIAPGQTGKIADYNYKLPDDFTGCVIAWNSNNLDSKVGGNYNYLYRLFRKSNLKPFERDISTEIYQAGSTPCNGVEGFNCYFPLQSYGFQPTNGVGYQPYRVVVLSFELLHAPATVCGPKKSTNLVKNKCVNF

        Receptor binding motif (71 characters, 438 to 509)
        SNNLDSKVGGNYNYLYRLFRKSNLKPFERDISTEIYQAGSTPCNGVEGFNCYFPLQSYGFQPTNGVGYQPY


## CALCULATION OF SIMILARITY
        These calculations have been made manually, for the purpose of
        validating program output
		
        Receptor binding domain of UFO69279.1, compared to YP_009724390.1
            --------------------D-------------------------------L-P-F-----------------------------------------N----------------------K-----S------------------------------NK-----A--------R--S-R--Y---H------------------------------------
        223 characters
        DLPFNKSNKARSRYH
        15 non dashes & 208 dashes
        similarity = 208/223 = 0.9327


        Receptor binding motif of UFO69279.1, compared to YP_009724390.1
        --K-----S------------------------------NK-----A--------R--S-R--Y---H---
        71 characters
        KSNKARSRYH
        10 non dashes & 61 dashes
        similarity = 61/71 = 0.8592


        Entire sequence
        V//ID////IEPEDLPFNKSNKARSRYHKGYKHKYKHKF
        1276 characters
        39 non dashes & 1237 dashes
        similarity = 1237/1276 = 0.9694


## NOTES
    Sequences are loaded from local files named with the accession ID.

    If the relevant files are not present, then shirley will use the
    Entrez API to collect the data from the database hosted at
    www.ncbi.nlm.nih.gov
    The collected data will be saved in local files for future use.
	

## AUTHOR
    Written by baseten418


## COPYRIGHT
    Copyright © 2024 baseten418
	
    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>.


SHIRLEY				August 2024
