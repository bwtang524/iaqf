# Pairs Trading using Machine Learning

<div style="text-align: justify">

Traditional Pairs Trading is a strategy that has heavily been dependent on and its efficiency limited by its two main processes, (a) identify correlated pairs by cointegration, a suitable but rudimentary tool, and (b) identify entries and exits based on the spread’s deviation from the mean (SMR), a very simplistic policy. We propose alternative approaches to these two processes. For identifying the pairs, we use OPTICS and Hierarchical clustering. Both of these models study the returns of the individual securities and attempt to intelligently identify naturally occurring clusters in the data, transcending the linearity restrictions imposed by the cointegration pair-selection technique. For determining entry and exits, we introduce two forecasting techniques – ARIMA and LSTM - to study the expected changes in the spread and capitalize on any predicted divergences. For the purpose of this study, we select 120 equity ETFs as our universe for identifying eligible pairs, with our data ranging from 2018 to 2022.

The content of this repository is structured as follows:

- `Clustering and Pair Selection.ipynb`: Illustrates the process of data loading, sanitization, cluster identification, and pair selection.
- `Trading.ipynb`: Documents the validation and testing of the pairs identified in `Clustering and Pair Selection.ipynb`. 5 different combinations of pair-selection and forecasting techniques are used to backtest the pairs trading strategy and their relative performances are reported within.
- `/data/`: Contains the pairs generated using OPTICS and Hierarchical Clustering along with the tickers included in this study.
- `/models/`: Contains pre-trained models for the below combinations:
    - OPTICS with ARIMA (`arima_optics.pkl`)
    - OPTICS with RNN (`rnn_optics.pkl`)
    - Hierarchical Clustering with ARIMA (`arima_hierarchical.pkl`)
</div>