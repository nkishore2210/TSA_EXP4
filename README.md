
# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES

## AIM:
To implement ARMA model in python.

## ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using
plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using
plot_acf and plot_pacf.


## PROGRAM:
### Developed by: KISHORE N
### Register no: 212222240049
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.arima_process import ArmaProcess
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
import warnings
warnings.filterwarnings('ignore')

# Load the dataset
data = pd.read_csv('Goodreadsbooks.csv', nrows =200)

# Use the 'Close' price column
close_prices = data['ratings_count'].dropna()

plt.rcParams['figure.figsize'] = [10, 7.5]

# Simulate ARMA(1,1) Process
ar1 = np.array([1, 0.33])
ma1 = np.array([1, 0.9])
ARMA_1 = ArmaProcess(ar1, ma1).generate_sample(nsample=len(close_prices))
plt.plot(ARMA_1)
plt.title('Simulated ARMA(1,1) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(1,1)
plot_acf(ARMA_1)
plot_pacf(ARMA_1)

# Simulate ARMA(2,2) Process
ar2 = np.array([1, 0.33, 0.5])
ma2 = np.array([1, 0.9, 0.3])
ARMA_2 = ArmaProcess(ar2, ma2).generate_sample(nsample=len(close_prices) * 10)
plt.plot(ARMA_2)
plt.title('Simulated ARMA(2,2) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(2,2)
plot_acf(ARMA_2)
plot_pacf(ARMA_2)
```


## OUTPUT:
## SIMULATED ARMA(1,1) PROCESS:

![{8D908379-9FE6-4547-BF5F-0E74037500E8}](https://github.com/user-attachments/assets/1ab6d5b6-45f8-4f44-9041-37c262e00001)

## Partial Autocorrelation

![{644EAFDA-6B2B-422F-8B04-A001DAEE7EA0}](https://github.com/user-attachments/assets/d4edab96-73ac-4779-a67e-1c21f258ab8e)


## Autocorrelation

![{DC0F393C-D59F-4448-A5BF-0935B8AB23A1}](https://github.com/user-attachments/assets/40120b36-aff2-46ad-ae86-c50df9c68c28)


## SIMULATED ARMA(2,2) PROCESS:

![{787E6442-497B-4DEF-9775-1A2BBA51AD32}](https://github.com/user-attachments/assets/293ea509-8eea-4fa5-a9d1-8dc2a552b19a)


## Partial Autocorrelation

![{1A870BBD-DB69-49A4-841F-A506D5C67505}](https://github.com/user-attachments/assets/bcbbdcb6-380a-4368-9659-4a21fc219017)

## Autocorrelation

![{FB66E0B5-A0C7-49AB-B5CE-6806A25C1FFA}](https://github.com/user-attachments/assets/f3b23966-a546-435c-bef7-f7a8da8879ea)


## RESULT:
Thus, a python program is created to fir ARMA Model successfully.
