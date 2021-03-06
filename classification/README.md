Sequence Classification
=======================

#Classification of Artificial Data

[Optional] Generate the data by running: `python generate_data.py`. This will generate the following datasets:
- Non-noisy data: sequence of 3 sine waves with different amplitude and frequency
- Data with spatial noise: same sequence of distinct sine waves, but with with white noise (spatial noise)
- Data with temporal noise: [TODO]

[Optional] Plot the data: 
* `python plot_artificial_data.py` will plot the artificial sensory sequences.

[Optional] Generate the model params for all the datasets: `python generate_model_params.py`

Classify the data: 
* Network API: `python classify_active_cells.py` (this will generate data AND model_params for various noise levels)
* OPF: `python opf_classify.py` [DEPRECATED]


#Classification of Real Data

## Benchmark datasets
The datasets were created by recording accelerometer data during the following tasks:
* 5min of walking
* 5min of running
* 5min of jumping
* 5min of going up stairs
* 5min of going down stairs
* 5min of stumbling around
* 5min of sitting

The sensor used to record accelerometer data is the TI SensorTag CC2541

## Record data
To connect to the SensorTag and write data to a file: enable bluetooth, and run `node sensortag/record_sensortag_data.js '<filename>.csv'`

## Visualize data
Run `python sensortag/plot_sensortag_data.py`. This will plot the accelerometer data recorded by the TI Sensortag

## Data preprocessing
To get good results on the data recorded by the sensor tag, it is necessary to account for misplacements of the sensor on the leg of the patient. So compensate, we convert and rotate the data before feeding it to the sequence classifier. Run `python sensortag/experiments/trajectory_converter.py` to clean the data out.


