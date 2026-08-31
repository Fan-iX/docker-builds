# HiCExplorer

Main tool: [HiCExplorer](https://github.com/deeptools/HiCExplorer)

Full documentation: https://hicexplorer.readthedocs.org/

> HiCExplorer is a powerful and easy to use set of tools to process, normalize and visualize Hi-C data.

## Example Usage

```
hicBuildMatrix --samFiles mate_R1.bam mate_R2.bam \
                 --binSize 10000 \
                 --restrictionSequence GATC \
                 --danglingSequence GATC \
                 --restrictionCutFile cut_sites.bed \
                 --threads 4 \
                 --inputBufferSize 100000 \
                 --outBam hic.bam \
                 -o hic_matrix.h5 \
                 --QCfolder ./hicQC
hicCorrectMatrix correct -m hic_matrix.h5 --filterThreshold -1.5 5 -o hic_corrected.h5
hicPlotMatrix -m hic_corrected.h5 -o hic_plot.png --region 1:20000000-80000000 --log1p
hicFindTADs -m hic_corrected.h5 --outPrefix hic_corrected --numberOfProcessors 16
```
