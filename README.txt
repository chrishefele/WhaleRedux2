Whale Detection Redux Challenge Code

This code is based on code pulled from https://github.com/nmkridler/moby
which was code used for the first Kaggle Whale Challenge.
This was used as a starting point for an entry in the 
the second Kaggle Whale Redux Challenge.

Modifications include:
- Added time between last clip and the current clip as a feature
- To capture serial correlation, the algorithm makes test-set
  preditions, then uses an average of 32/64 'local' predictions
  to provide a 'temporally local' estimation of a whale call
  (since whale upcalls occur in bursts/clusters)
- Changed cross validation folds from random to non-random
- Various modifications to allow the old code to use easily the 
  new dataset, including: 
  - Seperated templates from clips (here, templates=old clips, clips=new data)
  - Added data-preprocessing scripts to 0-pad clips to the same length


This code uses the following python packages:
Numpy/Scipy
Pandas
OpenCV
Sci-kit Learn

It assumes the user has access to the "sox" tool via the command line
(SoX - Sound eXchange, the Swiss Army knife of audio manipulation)

User must edit the baseDir variable in globalConst.py 
The code assumes a folder structure as follows:

baseDir=.  (as set in globalConst.py)
./src
./download
./data
./data_WhaleRedux2
./data_Whale
./template_data
./moby
./workspace
./workspace/metrics-no-shift
./workspace/metrics-diffdaysec
./features
./submissions

Use this procedure to generate a submission:
1. Create directory structure above. Put source in ./src
2. Put downloaded dataset in ./download
3. Edit globalConst.py to set the baseDir directory 
4. cp use-*.sh ../workspace
5. Run mk_data_WhaleRedux2.sh
6. Run mk_data_Whale.sh
7. Run genTestMetrics.py
8. Run genTrainMetrics.py
9. Run diff_daysec_features.py
10. Run mk-metrics-diffdaysec.sh
11. Run go-sub-diffdaysec-start-noshift.sh

