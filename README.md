# I24_processed_data
 
## Context
There is a lot of traffic on I-24, but how will we know where the heavy traffic is? What is the time gap of the cars? The density of traffic? This data can help answer those questions.

## Content

This is a snapshot of a dataset created by Matt Nice.

It was created by recording CAN and GPS data from a single vehicle driving on I-24 during morning (8AM-9AM) and evening (5PM-6PM) traffic. Matt cleaned the raw data and now it's up to you to make data analysis magic. The dataset includes Time, Velocity, Acceleration, Space Gap, Lateral Distance, Relative Velocity, Longitude GPS, Latitude GPS, Score, TrackID, L_Approach, R_Approach, L_Adjacent, and R_Adjacent.

## Notes on Specific Variables
Time - This is Epoch time (seconds) from a GPS module. All other features are interpolated to GPS time.

Velocity - Measurements are in kph.

Acceleration - Measurements are in m/s^2. This is the acceleration of the ego vehicle from the onboard accelerometer.

Space Gap - This is the space gap to the lead vehicle. Measurements are in meters. These measurements are from the onboard radar.

Lateral Distance, Relative Velocity, Score, TrackID - These measurements are derived from the raw radar data. Some drives are missing these CAN messages, so they are not included in all data. Lateral Distace(m) is the 'y-coordinate' of the lead vehicle, paired with the 'x-coordinate' of the Space Gap. Relative velocity (m/s) is the relative velocity of the lead vehicle. Score is the CAN 'rating' of the radar data, where a 100 is the lead vehicle, and a 0 would be total noise (these should be integers, but is compromised by interpolating to GPS time). TrackID is the ID of the CAN msg that the radar data came from (these should be integers, but is compromised by interpolating to GPS time).

Longitude GPS, Latitude GPS - The absolute position of the vehicle.

L_Approach, R_Approach - Binary signal, signifying a vehicle approaching in the lane to L/R. (these should be integers, but is compromised by interpolating to GPS time)

L_Adjacent, R_Adjacent - Binary signal, signifying a vehicle directly adjacent in the lane to L/R. (these should be integers, but is compromised by interpolating to GPS time)

Acknowledgements: Gracie Gumm and Michael Roman did the vast majority of driving to record this driving data.

This is intended as a limited snapshot of driving data to provide insight into traffic patterns on I-24 outside of Nashville. It was created in May 2021.
