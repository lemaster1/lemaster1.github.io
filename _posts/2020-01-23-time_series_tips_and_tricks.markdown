---
layout: post
title:      "Time Series Tips & Tricks"
date:       2020-01-23 21:30:39 +0000
permalink:  time_series_tips_and_tricks
---


I just finished a Python time series project.  I spent more time on this project, then I had anticipated.  I thought that I would share some learner insights as well as the code to save others time doing time series for the first time.  

There are a bunch of great resources from Medium blogs to Google search results to get all the code that you need to convert to datetime with pandas so I will not write about that code.  Here are some of the tips and tricks and functions that I think could be of value to you.

Oh real quick, I want to make sure that I mention the pandas .get_group method.  I have somehow missed this great method with all the Python learning I have been doing for the last several month.   It use to build a DataFrame when using groupby.  See below for example of the code that I used:


     df2 = df.drop('Month', axis=1).groupby(‘City').get_group("Chicago")

     Here's the generic form of the code from pandas:  GroupBy.get_group(self, name, obj=None) 

     and the Link to Pandas documentation:  https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.GroupBy.get_group.html. 

Okay, here’s the functions that you can use as templates to build your own.  In advance, I must recognize a couple of colleagues for their help: 

     * James Irving, my Flatiron instructor.  
     * Terry Ollila, one of my Flatiron instructors

The first function can be used over and over to get Time Series (ts) with a column name.  By the way, this data as well as all the data for these funtions are from Zillow in a CSV file format that listed home prices by zip codes.  

     def get_ts_from_chicago(chicago, group_name):

         ts = chicago.groupby('RegionName').get_group(group_name)
         ts = ts.resample('MS').asfreq()
         ts = ts['MeanValue'].rename(group_name)
         return ts

A function to plot Autocorrelation & Partial Autocorrelation:

     def plot_acf_pacf(ts, figsize=(10,6),lags=15):
         fig,ax = plt.subplots(nrows=2,figsize=figsize)
        plot_acf(ts,ax=ax[0],lags=lags)
        plot_pacf(ts, ax=ax[1],lags=lags) 
        plt.tight_layout()
    
        for a in ax:
            a.xaxis.set_major_locator(mpl.ticker.MaxNLocator(min_n_ticks=lags, integer=True))
            a.xaxis.grid()
    
      plot_acf_pacf(ts['MeanValue'])


A function to get the best pdq parameters for 1 zip code

    def get_best_params(ans):
     
         df_result = pd.DataFrame(ans[1:], columns=ans[0])
        df_result = df_result.sort_values('AIC', ascending= True).reset_index()
        best_params = df_result.iloc[0]['pdq']
        display(df_result.head())
    
        return best_params

The last one is a function for graphing a Train, Test, Prediction data as well as having confidence intervals

    def graph_sarimax(ts_train, ts_test, output=output):
    
        start=ts_test.index[0]
        end=ts_test.index[-1]    
        # Getting predictions starting from 2016 and calculate confidence intervals.
        predictions = output.get_prediction(start=start, end= end, dynamic=True)
        ts_pred = predictions.predicted_mean
        ts_conf = predictions.conf_int()  #makes confidence intereval graph
    
        ts_train.plot(label= 'Training Data')
        ts_test.plot(label= 'Test Data')
        ts_pred.plot(label= 'Prediction')
        plt.fill_between(ts_conf.index, ts_conf.iloc[:,0], ts_conf.iloc[:,1])  #confidence interval
        plt.legend()
        plt.ylabel('Dollar Amounts')
       plt.xlabel('Years')
       plt.title('Time Values')
       plt.show()
  
        return ts_pred

I am hopeful that you can find these examples to help you build your functions for time series coding with Python.  I really think that they will provide a really nice start for new coders.  





