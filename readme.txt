Quick start:    open ITMTF in jupyter notebook, look at the parameters and press run
                after a run .csv files can be examined in the LDA_data directory
                or one of the saved models can be examined in the ITMTF_vis_topic notebook

Setup:          Windows: Open an anaconda prompt
                         navagate to the project's directory
                         type:  conda env create -f ITMTF.yml
                                the created environment will be called "Gensim"
                                when you open the notebook, you will have to change kernels to Gensim
                                detailed instructions are in the project write-up's appendix
                                
                If you can't use the windows yml file, please follow the instructions in the project write-up's appendix
                to manually create an environment
                                

Primary notebooks:
ITMTF               - the main notebook to run
itmtf_improved      - has the code for the "improved" ITMTF algorithm; called from ITMTF
itmtf_withsplit     - has the code the the "classic" ITMTF algorithm, with splits and buffers; called from ITMTF
ITMTF_vis_topic     - used to visualize the words in a saved model
load_helper         - loads preprocessed files; called from ITMTF
itmtf_prerun_stats  - not really used in processing, but preprocessed pearson and granger stats per word stream
                      was important in creating the "improved" algorithm

Other notebooks:
baseline_create_helper  - used to create baselines
coherence_create_helper - used to test baselines to estimate the best number of topics
itmtf_cleaning          - a bunch of cells used to clean, mine, and reduce data

LDA_data directory      - used to store pre-processed data
                          also used to store artifacts from algorithm runs
                          (models must be stored in order to use the ITMTF_vis_topic notebook)   

ITMTF_analysis directory:
Demonstration Spreadsheets used in the project write-up

    "Improved" algorithm:
    wordanalysis.xls        - analysis of words in significant topics for 20, 30, 40 topics
    topicanalysis.xls       - analysis of avg confidence scores for runs of 20, 30, 40 topics
    Decayanalysis.xls       - analysis of decay parameters on 30 topic runs
    30iterationanalysis.xls - analysis of confidence for a 30 topic run over 30 iterations

    "Classic" algorithm:
    Paper.sigwords.xls      - analysis of words in significant topics for a classic run (30 topics, 5 buffers)
    Paper.confidence.xls    - analysis of the confidence scores for the classic run (30 topics, 5 buffers)

Other files:
*.log                   - left over artifact files showing the tuning of the model
CS410.cpp               - MP3 re-writen in c++ to improve speed, 
                          not used but there if anyone was interested (spent too many hours to discard)
                          
Libraries used:
Gensim Python LDA                       https://radimrehurek.com/gensim/models/ldamodel.html
SciPy's pearson r                       https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.pearsonr.html
statsmodels granger causality tests:    https://www.statsmodels.org/stable/generated/statsmodels.tsa.stattools.grangercausalitytests.html    

Library tested but not used:
pypi.orgs PLSA:                         https://pypi.org/project/plsa/

