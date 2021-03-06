# in_silico_pcr

Script to run an in silico pcr for a set of primer pairs on an assembly

REQUIREMENTS:

Requires tre approximate regex module https://github.com/laurikari/tre/ to be in your path 

USAGE:

in_silico_pcr.py [options] fasta/multifasta input files

Options:<br>
  -h, --help            show this help message and exit<br>
  -p FILE, --primers=FILE
                        text file containing primers. For each region of
                        interest there should be one row. Each row should
                        contain 3 or 5 whitespace-delimited columns: 1) Name
                        of the region, 2) forward primer sequence, 3) reverse
                        primer sequence 4) maximum product length (optional)
                        5) minimum product length (optional, and can only be
                        included with 4). The file may contain a header row,
                        but if this is the case the -H option must be
                        specified (or strange things might happen)<br>
  -H, --header          primer file has a header row [default=False]
  -r, --rcreverse       Reverse primers require reverse complementing (use
                        this option if your reerse primers are in the same
                        direction as your forward primers) [default=False]<br>
  -i, --incprimer       include primer sequence in fasta output
                        [default=False]<br>
  -m MAXCOST, --maxcost=MAXCOST
                        maximum cost (number of changes in a primer sequences)
                        allowed for a valid match. [Default= 3]<br>
  -o PREFIX, --prefix=PREFIX
                        output file prefix<br>
  -e, --potentials      include potential primer locations in tab files in
                        cases where no pair within selected product size range
                        is found [default=False]<br>
  -c, --circular        sequences are circular [default=False]<br>
