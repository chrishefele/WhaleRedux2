Whale Detection Challenge Code

This code is a hacked-up version of the code pulled from https://github.com/nmkridler/moby

It uses the following python packages:
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

