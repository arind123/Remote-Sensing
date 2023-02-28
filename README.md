# Remote-Sensing[Readme.docx](https://github.com/arind123/Remote-Sensing/files/10833781/Readme.docx)
![image](https://user-images.githubusercontent.com/36856593/221840305-590b29c0-4012-43a2-8c3b-d434fe118b46.png)
1.	VV: single co-polarization, vertical transmit/vertical receive
2.	HH: single co-polarization, horizontal transmit/horizontal receive
3.	VV + VH: dual-band cross-polarization, vertical transmit/horizontal receive
4.	HH + HV: dual-band cross-polarization, horizontal transmit/vertical receive
        
![image](https://user-images.githubusercontent.com/36856593/221840464-aa3f0f38-c180-404b-846d-130a892e003b.png) ![image](https://user-images.githubusercontent.com/36856593/221840480-1dfe6447-0b6a-45e7-ab1f-fec670766e3a.png)

![image](https://user-images.githubusercontent.com/36856593/221840504-16a0bf51-fd44-4005-9ea5-bd5285696daa.png)![image](https://user-images.githubusercontent.com/36856593/221840522-eb56d7ad-9d6f-4cd4-84c7-7edb4113d6dc.png)


Polarization refers to the direction of travel of an electromagnetic wave vector’s tip: vertical (up and down), horizontal (left to right), or circular (rotating in a constant plane left or right). The direction of polarization is defined by the orientation of the wave’s electric field, which is always 90°, or perpendicular, to its magnetic field.
A radar antenna can be designed to send and receive electromagnetic waves with a well-defined polarization. By varying the polarization of the transmitted signal and receiving several different polarized images from the same series of pulses, SAR systems can gather detailed information on the polarimetric properties of the observed surface, which can reveal the structure, orientation and environmental conditions of the surface elements. For example, linearly oriented structures such as buildings or ripples in the sand tend to reflect and preserve the coherence (same linear direction) of the polarimetric signal. Randomly oriented structures such as tree leaves scatter and depolarize the signal as it bounces multiple times. Multiple polarizations and wavelength combinations provide different and complementary surface information.
1.	Apply orbit file
•	Updates orbit metadata with a resituated orbit file (or a precise orbit file if the resituated one is not available). The default metadata provided when SAR data are downloaded is generally not very accurate. In SNAP, the updated orbit file, with more accurate information to help improve geocoding and other processing results, is automatically downloaded by the AOF operator. This operation should be performed as a priority before all other pre-processing steps for better results
2.	GRD border noise removal
•	Removes low intensity noise and invalid data on scene edges. (As of January 12, 2018). Because of irregularities on the Earth’s surface, deformations can appear on the Level-1 images during their generation. The BNR operation allows one to correct and remove noises present on the edges of images.
3.	Thermal noise removal
•	Removes additive noise in sub-swaths to help reduce discontinuities between sub-swaths for scenes in multi-swath acquisition modes. (This operation cannot be applied to images produced before July 2015)
4.	Application of radiometric calibration values
•	Computes backscatter intensity using sensor calibration parameters in the GRD metadata. The calibration step (calibrate) aims to correct the signal intensity according to the sensor characteristics and the local incidence angle. The metadata of the input products allows SNAP to automatically determine the corrections to be applied. In this work, the operation is performed for both VV and VH polarizations.
5.	Terrain correction (orthorectification)
•	Converts data from ground range geometry, which does not take terrain into account, to σ° using the SRTM 30 meter DEM or the ASTER DEM for high latitudes (greater than 60° or less than -60°). The initially downloaded S1 images are devoid of geographic coordinates, which makes them unusable for most applications. The orthorectification step is performed to geo-reference images in order to project them into the Universal Transverse Mercator system or World Geodetic System 1984. This process also allows one to correct the distortion effects that occurred during the acquisition (overlay, shading). The terrain correction operation is based on a digital elevation model (DEM) automatically downloaded by SNAP or provided by the user.

Limitations: 
One of the limitations of working with SAR data has been the somewhat tedious pre-processing steps that lower-level SAR data requires. Depending on the type of analysis you want to do, these pre-processing steps can include: applying the orbit file, radiometric calibration, de-bursting, multi-looking, speckle filtering, and terrain correction. 
Special software is required to process SAR data, depending on the data provider, starting level of data, and desired level of data. 
Installing SNAP
1.	Create a Virtual Environment.
2.	Download SNAP
3.	While installing SNAP, within the installer you can simply activate a checkbox and select the path to the python executable (Path to the python.exe from the virtual environment). 
 
4.	Open SNAP Command-Line interface run snappy-conf “path to the python.exe in the virtual environment”
5.	If you configure snappy using an Anaconda environment, you need to run it with the same Anaconda environment. 
6.	Go to anaconda prompt cd to the snap-python folder within .snap folder in the windows C Drive. Run python
7.	Link to configuration

SNAP Tool :
 
Each downloaded S1 image covers an area of 250 km × 250 km

Important Definitions: 
Backscatter
Backscatter is the portion of the outgoing radar signal that the target redirects directly back towards the radar antenna. Backscattering is the process by which backscatter is formed. The scattering cross section in the direction toward the radar is called the backscattering cross section; the usual notation is the symbol sigma (?). It is a measure of the reflective strength of a radar target. The normalised measure of the radar return from a distributed target is called the backscatter coefficient, or sigma nought , and is defined as per unit area on the ground. If the signal formed by backscatter is undesired, it is called clutter. Other portions of the incident radar energy may be reflected and scattered away from the radar or absorbed.
Band
A selection of wavelengths or range of radar frequencies. For example Sentinel-1 operates at C-band (central frequency of 5.404 GHz). Other spaceborne SAR's operate at L-band (1.3 GZ) or X-band (9.6 GHz).
Beam
A selection of wavelengths or range of radar frequencies. For example Sentinel-1 operates at C-band (central frequency of 5.404 GHz). Other spaceborne SAR's operate at L-band (1.3 GZ) or X-band (9.6 GHz).
Beam Mode
The SAR operating configuration defined by the swath width and spatial resolution.
Beam Position
The area within the total possible swath that is actually illuminated while being governed by the characteristics of a specific beam mode.
Beta Nought
ß° radar brightness coefficient. The reflectivity per unit area in slant range which is dimensionless.
C-Band
A nominal frequency range, from 8 to 4 GHz (3.75 to 7.5 cm wavelength) within the microwave (radar) portion of the electromagnetic spectrum. Imaging radars equipped with C-band are generally not hindered by atmospheric effects and are capable of imaging through tropical clouds and rain showers. Its penetration capability with regard to vegetation canopies or soils is limited and is restricted to the top layers.
Calibration
Calibration is the process of quantitatively defining the system response to known controlled signal inputs.
Coherence
Coherence is the fixed relationship between waves in a beam of electromagnetic (EM) radiation. Two wave trains of EM radiation are coherent when they are in phase. That is, they vibrate in unison. In terms of the application to things like radar, the term coherence is also used to describe systems that preserve the phase of the received signal.
Complex Number
For radar systems, a complex number implies that the representation of a signal, or data file, includes both magnitude and phase values. In the digital SAR context, a complex number is often represented by an equivalent pair of numbers, the real in-phase component (I) and the imaginary quadrature component (Q).
Data take
A data take is a continuous temporal segment of SAR acquisition without instrument mode change (due to on-board memory handling, a data take can be downlinked in distinct moments and in different channels).
Detection (Radar)
Processing stage at which the strength of the signal is determined for each pixel value. Detection removes phase information from the data file. The preferred detection scheme uses a magnitude squared method, which is energy conserving, and has units of voltage squared per pixel.
Doppler Frequency
The Doppler frequency depends on the component of satellite velocity in the line-of-sight direction to the target. This direction changes with each satellite position along the flight path, so the Doppler frequency varies with azimuth time. For this reason, azimuth frequency is often referred to as Doppler frequency.
Horizontal Polarisation
Linear polarisation with the electric vector oriented in the horizontal direction in antenna co-ordinates.
Horizontal Transmit - Horizontal Receive Polarisation (HH)
A mode of radar polarisation where the microwaves of the electric field are oriented in the horizontal plane for both signal transmission and reception by means of a radar antenna.
Horizontal Transmit - Vertical Receive Polarisation (HV)
A mode of radar polarisation where the microwaves of the electric field are oriented in the horizontal plane for signal transmission, and where the vertically polarised electric field of the backscattered energy is received by the radar antenna.
Imaging Radar
Most imaging radars produce two-dimensional images. The two dimensions are called range, and azimuth.
Impulse Response Function
Also known as the point spread function, the impulse response function (IRF) is the two-dimensional brightness pattern in an image (after processing) of a point target such as a corner reflector or transponder. The 3dB width of IRF gives the spatial resolution of the product while IRF sidelobes give an indication of the performance of the SAR instrument and the SAR processor.
Interferometry
A technique that uses the measured differences in the phase of the return signal between two satellite passes to detect slight changes of locations on the Earth's surface. Mapping height changes provides information on, for example, earthquake damage, volcanic activity, landslides and glacier movement.
Level-0
Reconstructed unprocessed data at full space-time resolution with all available supplemental information to be used in subsequent processing (e.g. orbit ephemeris) appended. SAR Level-0 products may cover part of an acquisition segment (in case only part of a segment is down linked at a certain ground station in the same pass) or a full acquisition segment. Level-0 products are generated at the receiving station right after acquisition.
Level-1
Reconstructed data at full resolution, time-referenced, and annotated with ancillary information, including radiometric and geometric calibration coefficients and geo-referencing parameters. Data may be radio-metrically corrected and calibrated at full spatial resolution, and re-sampled to a specified grid.
Level-2
Derived geophysical parameters derived from Level-1 data.
Look Direction
The radar look direction defines the angle in the horizontal plane in which the radar antenna is pointing when transmitting a pulse and receiving the return signal from the ground or from an object. The look direction is an angular measurement (in degrees) and is usually made with respect to true North. In side-looking imaging radar, the look direction is often orthogonal (normal) to the flight trajectory (azimuth) of the platform carrying the radar and is thus synonymous with the range direction. The radar look direction is an important parameter when analysing features with a preferred orientation, for example fracture patterns in rock formations, regular street patterns, or ocean waves, as these may be enhanced through choice of appropriate radar illumination direction.
Looks
Radar terminology refers to individual looks as groups of signal samples in a SAR processor that splits the full synthetic aperture into several sub-apertures, each representing an independent look of the identical scene. The resulting image formed by incoherent summing of these looks is characterised by reduced speckle and degraded spatial resolution. The SAR signal processor can use the full synthetic aperture and the complete signal data history in order to produce the highest possible spatial resolution, albeit very speckled, single-look complex (SLC) SAR image product. Multiple looks may be generated by averaging over range and/or azimuth bandwidths. For an improvement in radiometric resolution using multiple looks there is an associated degradation in spatial resolution.
Noise Equivalent Sigma Nought
The backscatter or sigma0 of the thermal noise in SAR imagery.
Polarisation
The process of confining the vibrations of the magnetic, or electric field, vector of light or other radiation to one plane.
Pulse Repetition Frequency (PRF)
Rate of recurrence of the pulses transmitted by a radar.
SAR Focusing
In a long synthetic aperture, SAR focusing involves the removal and compensation of path length differences from the antenna to the target on the ground. The main advantage of a focused synthetic aperture is that it increases its array length over those radar signals that can be processed, and thus increases potential SAR resolution at any range. SAR focusing is a necessary process when the length of a synthetic array is a significant fraction of the range to ground being imaged, as the lines-of-sight (range) from a particular point on the ground to each individual element of the array differ in distance. These range differences, or path length differences, of the radar signals can affect image quality. In a focused SAR image these phase errors can be compensated for by applying a phase correction to the return signal at each synthetic aperture element.
Sigma
The conventional measure of the strength of a radar signal reflected from a geometric object (natural or manufactured) such as a corner reflector. Sigma specifies the strength of reflection in terms of the geometric cross section of a conducting sphere that would give rise to the same level of reflectivity. (Units of area, such as metres squared).
Sigma Nought
Scattering coefficient, or the conventional measure of the strength of radar signals reflected by a distributed scatterer, usually expressed in dB. It is a normalised dimensionless number, comparing the strength observed to that expected from an area of one square meter. Sigma nought is defined with respect to the nominally horizontal plane, and in general has a significant variation with incidence angle, wavelength, and polarisation, as well as with properties of the scattering surface itself.
Swath
The width of an imaged scene in the range dimension, measured in either ground range or slant range.
Synthetic Aperture Radar (SAR)
A synthetic aperture radar, or SAR, is a coherent radar system that generates high-resolution remote sensing imagery. Signal processing uses magnitude and phase of the received signals over successive pulses from elements of a synthetic aperture to create an image. As the line of sight direction changes along the radar platform trajectory, a synthetic aperture is produced by signal processing that has the effect of lengthening the antenna. The achievable azimuth resolution of a SAR is approximately equal to one-half the length of the actual (real) antenna and does not depend on platform altitude (distance). High range resolution is achieved through pulse compression techniques.
Vertical Polarisation
Linear polarisation with the electric vector oriented in the vertical direction in antenna co-ordinates.
Vertical Transmit-Horizontal Receive Polarisation (VH)
A mode of radar polarisation where the microwaves of the electric field are oriented in the vertical plane for signal transmission, and where the horizontally polarised electric field of the backscattered energy is received by the radar antenna.
Vertical Transmit-Vertical Receive Polarisation (VV)
A mode of radar polarisation where the microwaves of the electric field are oriented in the vertical plane for both signal transmission and reception by means of a radar antenna.
Zero Doppler Time
Zero Doppler time is the along track (azimuth) time at which a target on the ground would have a Doppler shift of zero with respect to the satellite (i.e. when the target was perpendicular to the flight path). Also called the closest approach azimuth time. The SAR processor locates targets in the image at the zero-Doppler azimuth time.

Important Pre-processing steps:
Calibration is the procedure that converts digital pixel values to radiometrically calibrated SAR backscatter. The information required to apply the calibration equation is included within the Sentinel-1 GRD product; specifically, a calibration vector included as an annotation in the product allows simple conversion of image intensity values into sigma nought values. The calibration reverses the scaling factor applied during level-1 product generation and applies a constant offset and a range-dependent gain, including the absolute calibration constant.

SAR data are generally sensed with a varying viewing angle greater than 0 degrees, resulting in images with some distortion related to side-looking geometry. Terrain corrections are intended to compensate for these distortions so that the geometric representation of the image will be as close as possible to the real world. Range Doppler terrain correction is a correction of geometric distortions caused by topography, such as foreshortening and shadows, using a digital elevation model to correct the location of each pixel. The range Doppler terrain correction operator available in SNAP implements the Range Doppler orthorectification method for geocoding SAR scenes from images in radar geometry. It makes use of available orbit state vector information in the metadata, the radar timing annotations, and the slant to ground range conversion parameters together with the reference digital elevation model data to derive the precise geolocation information. The target Coordinate Reference System (CRS) can be selected and optionally set to match the UTM zone of the overlaying Sentinel-2 granules. The operator allows the selection of the image resampling method and the target pixel spacing in the target CRS. This processing step allows the spatial snapping of Sentinel-1 GRD products to Sentinel-2 MSI data grids, to geolocate data to a common spatial grid and promote the use of satellite virtual constellations.

Resolution: 5m * 20m 
C band wavelength: 3.8 to 7.5 (Longer the wave length more the penetration) (agriculture work: L, X and C band)


