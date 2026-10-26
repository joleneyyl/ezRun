# The `secondRef` parameter

`secondRef` adds reference sequences to the species reference, for example transgenes, viral sequences or sequences from another species.

Provide a FASTA file that is readable at runtime. Suggested locations are:

- `/srv/gstore/projects/p<current project>/<extraSequences or another informative name>`
- `/srv/GT/databases/extra_references/<your informative folder name>`

The gstore location is preferred because it provides persistent storage.

## How the reference is interpreted

If `file.exists(sub(".fa", ".gtf", param$secondRef))` is true, the FASTA is treated as genomic DNA and the GTF supplies gene coordinates. Without a matching GTF, sequences are used directly; RNA workflows treat each sequence as a spliced transcript representing a separate gene.

## Tool behaviour

| Tool | Behaviour |
| --- | --- |
| STAR | With a GTF, a temporary reference combines the species reference and `secondRef`. Without a GTF, STAR adds the sequences during alignment without building a new reference. Specify `secondRef` again when running `featureCounts`. |
| CellRanger | A temporary reference is always built. |
| Kallisto | Not yet supported in the recorded workflow. |
