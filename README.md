# Master's thesis data

This repository contains audio, annotation and evaluation data related to my Master's thesis project, "A comparison and evaluation of approaches to the automatic formal analysis of musical audio". For more details about the thesis and full text, visit http://jblsmith.github.io/projects/masters-thesis/.

## Audio and Annotation data

The evaluation used:

- The Beatles dataset, a standard collection of all the band’s album recordings, with structural annotations by TUT, UPF and QMUL, all based on annotations by Allan Pollack;
- The Popular Music Database of the RWC collection, with annotations also created by RWC;
- Two new sets of jazz and classical music assembled and annotated for this thesis.

This last corpus contains entirely public domain (and hence freely shareable) pieces downloaded from the Internet Archive. The list of tracks, and links to the Internet Archive, can all be found in [audio_file_list.tsv](https://github.com/jblsmith/ma-thesis/blob/master/audio_file_list.tsv). The audio and annotations files are all contained in this repository under [ma-thesis/corpora](https://github.com/jblsmith/ma-thesis/tree/master/corpora).

## Algorithm evaluation details

Five algorithms were evaluated in this experiment. Three of these, Peiszer (2007), Levy and Sandler (2008) and Barrington et al. (2009), produce full structural analyses, segmenting the piece into large-scale sections and providing group labels. The other two, Mestres (2007) and the "Analyze" method of the Echo Nest API, perform only the segmentation step, producing a list of boundaries between the sections of a piece.

Access to these algorithms was kindly provided by the following researchers: Luke Barrington at UCSD Computer Audition Laboratory provided the code for his algorithm, with assistance from Emanuele Coviello. The evaluation of Xavier Janer Mestres' segmentation algorithm was carried out by Nicholas Wack and Emilia Gómez at Universitat Pompeu Fabra. Ewald Peiszer has made his algorithm and many of his previous results available online. Mark Levy has implemented his and Mark Sandler's algorithm as a Vamp plugin for Sonic Visualiser, both of which are free to download. Finally, Tristan Jehan and Brian Whitman, founders of The Echonest, allow free public use of their analysis tools via a developer API. I am grateful for all of the above researchers and inspired by their willingness to share.

The five analysis algorithms were fed the songs listed in the audio data section; in the case of the three full structure analysis algorithms, several combinations of parameters were tested, shown in the table below. The output of the algorithms is provided here as a [17 MB archive](https://github.com/jblsmith/ma-thesis/blob/master/algorithm_outputs.zip), the contents of which are organized by algorithm, corpus, album, and piece. The different outputs using different parameters for a single piece are all contained in a single folder, with the parameters embedded in the filename. It is hoped that by sharing this information, other researchers who find fault with my evaluation procedure or who conceive of new evaluation procedures may incorporate this data into their study. After all, it is a far more painstaking affair to obtain and operate algorithms than it is to evaluate them; since reusing this data is the easy part, it would seem a waste not to invite others to do so.

### Evaluated parameters:

| Algorithm | Features | Number of cluster types k | Other parameters |
|---|---|---|---|
| Barrington et al. | chroma, MFCC | 3, 4, 6 | fine or coarse output |
| Levy and Sandler | CQT, MFCC | 3, 4, 5, 6, 8, 10 | 4 or 10 second minimum section length |
| Peiszer | CQT, MFCC | 3, 4, 5, 6, 8, 10 | k-means, agglomerative, or DTW clustering |


