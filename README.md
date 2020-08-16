# F-FADE
F-FADE, short for Frequency-Factorization forAnomaly DEtection.

## Getting started
1. Create a directory `result`.
2. Run `./run.sh` to test on DARPA dataset with default hyper-parameters.
3. Check the accuracy (AUC) and anomaly scores in `result`.

## Command line options
  * `--embedding_size`: the number of dimensions of node embeddings.
  * `--t_setup`: the time to setup the model.
  * `-W_upd-`: the time interval for model update
  * `--T_th`: the cut-off threshold of the time to record, which is the inverse of the cut-off threshold frequency.
  * `--alpha`: the decay rate when updating frequency.
  * `--M`: the upper limit of memory size.

## Input file format
F-FADE expects the input edge streams to be stored in a single file containing the following four columns in order:
1. `time (int or float)`: time stamp of the edge
2. `source (int)`: source ID of the edge
3. `destination (int)`: destination ID of the edge
4. `label (int)`: label of the edge (1 denotes anomalies, 0 otherwise)

Each line represents an edge. Edge should be sorted in non-decreasing order of their time, source, and destination, and the delimiter should be " ".
