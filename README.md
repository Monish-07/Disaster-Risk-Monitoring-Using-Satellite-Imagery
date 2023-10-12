# Disaster Risk Monitoring Using Satellite Imagery

## Nvidia Deep Learning Institute 

## Disaster Risk Monitoring ##
Natural disasters such as flood, wildfire, drought, and severe storms wreak havoc throughout the world, causing billions of dollars in damages, and uprooting communities, ecosystems, and economies. The ability to detect, quantify, and potentially forecast natural disasters can help us minimize their adverse impacts on the economy and human lives. While this lab focuses primarily on detecting flood events, it should be noted that similar applications can be created for other natural disasters. 

### Flood Detection ###
[Flooding](https://en.wikipedia.org/wiki/Flood) occurs when there is an overflow of water that submerges land that is usually dry. They can occur under several conditions: 
* Overflow of water from water bodies, in which the water overtops or breaks levees (natural or man-made), resulting in some of that water escaping its usual boundaries
* Accumulation of rainwater on saturated ground in an areal flood
* When flow rate exceeds the capacity of the river channel

Unfortunately, flooding events are on the rise due to climate change and sea level rise. Due to the increase in frequency and intensity, the topic of flood has garnered international attention in the past few years. In fact, organizations such as the [United Nations](https://www.un.org/en/) has maintained effective response and proactive risk assessment for flood in their [Sustainable Development Goals](https://en.wikipedia.org/wiki/Sustainable_Development_Goals). The research of flood events and their evolution is an interdisciplinary study that requires data from a variety of sources such as: 
* Live Earth observation data via satellites and surface reflectance
* Precipitation, runoff, soil moisture, snow cover, and snow water equivalent
* Topography and meteorology

The ability to detect flood and measure the extent of the disaster, can help decision makers develop tactical responses and scientists study flood behavior over time. Ultimately, we want to enable long-term mitigation strategies that are informed by science to help us achieve sustainability.

### Satellite Imagery ###
In this lab, we demonstrate the ability to create a flood detection segmentation model using satellite imagery. Using satellites to study flood is advantageous since physical access to flooded areas is limited and deploying instruments in potential flood zones can be dangerous. Furthermore, satellite remote sensing is much more efficient than manual or human-in-the-loop solutions. 

There are thousands of man-made satellites currently active in space. Once launched, a satellite is often placed in one of several orbits around Earth, depending on what the satellite is designed to achieve. Some satellites, such as those discussed in this lab, are used for Earth observation to help scientists learn about our planet while others could be used for communication or navigation purposes. 


Earth observation satellites have different capabilities that are suited for their unique purposes. To obtain detailed and valuable information for flood monitoring, satellite missions such as [Copernicus Sentinel-1](https://sentinel.esa.int/web/sentinel/missions/sentinel-1), provides C-band [**Synthetic Aperture Radar**](https://en.wikipedia.org/wiki/Synthetic-aperture_radar) (SAR) data. Satellites that use SAR, as opposed to _optical satellites_ that use visible or near-infrared bands, can operate day and night as well as under cloud cover. This form of radar is used to create two-dimensional images or three-dimensional reconstructions of objects, such as landscape. The two polar-orbiting Sentinel-1 satellites (Sentinel-1A and Sentinel-1B) maintain a repeat cycle of just _6_ days in the [Lower Earth Orbit (LEO)](https://en.wikipedia.org/wiki/Low_Earth_orbit). Satellites that orbit close to Earth in the LEO enjoy the benefits of faster orbital speed and data transfer. These features make the Sentinel-1 mission very useful for monitoring flood risk over time. Thus, a real-time AI-based remote flood level estimation via Sentinel-1 data can prove game-changing. 


More information about the Sentinel-1 mission can be found [here](https://directory.eoportal.org/web/eoportal/satellite-missions/c-missions/copernicus-sentinel-1).

![data distribution 446](https://github.com/Monish-07/Nvidia/assets/95215581/8fee4202-b488-43cd-a5c8-f8568e8cf6ec)


### Computer Vision ###
At the heart of this type of disaster risk monitoring system is one or more machine learning models to generate insights from input data. These are generally deep learning neural network models that have been trained for a specific task. There are numerous approaches for drawing insight from images using machine learning such as: 
* **Classification** is used for identifying the object contained in an image. It is the task of labeling the given frame with one of the classes that the model has been trained with. 
* **Object detection**, which includes image localization, can specify the location of multiple objects in a frame. 
    * **Localization** uses regression to return the coordinates of the potential object within the frame. 
* **Segmentation** provides pixel level accuracy by creating a fine-grained segmentation mask around the detected object. Applications for segmentation include: an AI-powered green screen to blur or change the background of the frame, autonomous driving where you want to segment the road and background, or for manufacturing to identify microscopic level defects. 
    * **Semantic segmentation** associates every pixel of an image with a class label such as `flood` and `not-flood`. It treats multiple objects of the same class as a single entity. 
    * In contrast, **instance segmentation** treats multiple objects of the same class as distinct individual instances. 


For the purposes of detecting flood events, we will develop a _semantic segmentation_ model trained with labelled images that are generated from Sentinel-1 data.

### Deep Learning-Based Disaster Risk Monitoring System ###
The system that we envision consists of the below workflow: 
1. Satellite remote sensors capture data
2. Data are used to (continuously) train deep learning neural network models
3. Different models and versions are managed by the model repository
4. Model inference performance is actively monitored
5. Data are passed to the inference server 
6. The deep learning inference results are post-processed for either 
7. Further analytics by 3rd party or 
8. Raising alerts

When processing data in real-time, this system can help us in delineating open water flood areas. In addition, identifying flood levels will enable effective disaster response and mitigation. If we combine the flood extent mapping with other data such as topography and/or population, we can create a plan of action with downstream. We can also use this information to predict the direction of flow of water, redirect flood waters, organize resources for distribution, etc. Importantly, such a 
system can recommend a path of least flood levels in real-time that disaster response professionals can potentially adopt.




