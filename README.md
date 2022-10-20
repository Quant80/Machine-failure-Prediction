# Machine-failure-Prediction
Attribute Information:
The dataset consists of 10 000 data points stored as rows with 14 features in columns

UID: Unique identifier ranging from 1 to 10000

Product ID: Consisting of a letter L, M, or H for low (50% of all products), medium (30%) and high (20%) as product quality variants and a variant-specific serial number

Air temperature [K]: Generated using a random walk process later normalized to a standard deviation of 2 K around 300 K

Process temperature [K]: Generated using a random walk process normalized to a standard deviation of 1 K, added to the air temperature plus 10 K.

Rotational speed [rpm]: Calculated from a power of 2860 W, overlaid with a normally distributed noise

Torque [Nm]: Torque values are normally distributed around 40 Nm with a Ïƒ = 10 Nm and no negative values.

Tool wear [min]: The quality variants H/M/L add 5/3/2 minutes of tool wear to the used tool in the process. and a 'machine failure' label that indicates, whether the machine has failed in this particular datapoint for any of the following failure modes are true.

The machine failure consists of five independent failure modes

Tool wear failure (TWF): The tool will be replaced of fail at a randomly selected tool wear time between 200 â€“ 240 mins (120 times in our dataset). At this point in time, the tool is replaced 69 times, and fails 51 times (randomly assigned).

Heat dissipation failure (HDF): Heat dissipation causes a process failure, if the difference between air- and process temperature is below 8.6 K and the toolâ€™s rotational speed is below 1380 rpm. This is the case for 115 data points.

Power failure (PWF): The product of torque and rotational speed (in rad/s) equals the power required for the process. If this power is below 3500 W or above 9000 W, the process fails, which is the case 95 times in our dataset.

Overstrain failure (OSF): If the product of tool wear and torque exceeds 11,000 minNm for the L product variant (12,000 M, 13,000 H), the process fails due to overstrain. This is true for 98 datapoints.

Random failures (RNF): Each process has a chance of 0,1 % to fail regardless of its process parameters. This is the case for only 5 datapoints, less than could be expected for 10,000 datapoints in our dataset.

If at least one of the above failure modes is true, the process fails and the 'machine failure' label is set to 1. It is therefore not transparent to the machine learning method, which of the failure modes has caused the process to fail.
