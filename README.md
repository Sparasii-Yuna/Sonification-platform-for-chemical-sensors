# Sonification-platform-for-chemical-sensors
Welcome to the Sonification Platform for Chemical Sensors repository! This project focuses on developing a sonification platform using Pure Data to translate data from chemical sensors into sound, aiding in real-time monitoring and analysis.

## Introduction
In this project, we have created a sonification platform utilizing Pure Data (Pd) to convert data from chemical sensors into audible sounds. The platform offers an innovative approach to sensor data analysis, enabling users to perceive and interpret sensor readings through sound.


## Repository Structure
```
|-- README.md                 # Introduction and usage guidelines
|-- SonificationFinal.pd      # Main Pure Data patch for sonification
|-- audio_samples             # Folder containing audio samples
|   |-- alert.wav             # Audio sample for the patch
|   |-- CueSample-ONE.wav     # Audio sample for the patch
|   |-- CueSample-TWO.wav     # Audio sample for the patch
|   |-- CueSample-THREE.wav   # Audio sample for the patch
|   |-- CueSample-FOUR.wav    # Audio sample for the patch
|-- datasets                  # Folder containing datasets
|   |-- test_chn1.txt         # Dataset for channel 1
|   |-- test_chn2.txt         # Dataset for channel 2
|   |-- ...                   # Other datasets for channels
|-- original_dataset          # Folder containing the original dataset
|   |-- [Sonification]K and NH4.xlsx   # Original dataset
|-- resources
|   |-- introduction_video.md # Markdown file with link to the introduction video
|   |-- audio_playlist.md     # Markdown file with link to the audio playlist
```


## Usage Guidelines
### 1. Pure Data Patch:
  - Use `SonificationFinal.pd` as the main Pure Data patch for sonification.
  
  - Ensure you have Pure Data installed to run this patch.
  
  - Required external dependency: freeverb~.
  
  - Guideline for running the patch:

    ```
    block size setting as 256 is recommended.

    After run the patch (Seq1-4 is already connected to Chn13-16 playback system.)
    Need to set the volume for <CHN13-16> <Speech Cues> and <Click Sound>

    Recommend levels are: 86dB, 91dB and 100dB

    The green button is for start/stop playing.

    Click the green button to start a sonification session for data from Chn13-16.

    Chn14 is the target problematic sensor we want to identify by this patch in this session.

    Click sounds will be observed in the beginning of a session for about 1 minute in other sensors Chn13, Chn15 and Chn16

    But for Chn14, click sounds still frequently appear after 1 minute, which indicates it is problematic (acting very noisy)
    ```
    
    > #### Variables explanation:

    ```
    RangeforNote(Scaling ratio control)  			#inside pdUpdateWindow

    basicLoop(dataReadin rate)                			#inside pdUpdateWindow

    Duration of a whole group                  			#inside pdtrigger

    Interval between speech cue and note sequence 	#inside pdtrigger

    IOI						#inside pdreadChn[xx]>>pdreadWindow

    AlertRange1(AlertThreshold positive)			#inside pdAlert

    AlertRange2(AlertThreshold negative)			#inside pdAlert
    ```


      

### 2. Audio Samples:
  - Find audio samples used in the patch inside the `audio_samples` folder.

### 3. Datasets:
  - Access datasets for 16 channels of sensors used for testing and development in the `datasets` folder.

### 4. Orginal Dataset:
  - Explore the original dataset used for developing the sonification platform in the original_dataset folder.
  
  - This dataset served as the foundation for creating the sonification algorithms.



## Additional Resources
- ### Introduction Video:

  - View the introduction video showcasing the final design [here](https://youtu.be/-I8y_FUYg9Q).

- ### Audio Playlist:

  - Listen to the audio playlist featuring samples of different iterations [here](https://soundcloud.com/yuna-787448399/sets/audio-samples-of-prototypes).
