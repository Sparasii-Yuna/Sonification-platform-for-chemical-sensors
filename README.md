# Sonification-platform-for-chemical-sensors
This repository contains resource for a sonification platform for chemical sensors developed with Pure Data.


## SonificationFinal.pd
This is a patch for sonification PureData patch.
You need to download PureData to run this patch.
also need freeverb~
block size 256 is recommended.
------------------------------------------------------------------------------------------------------------------
Files Description:
SonificationFinal.pd                		<executable puredata patch>
alert.wav				<audio sample for the patch>
CueSample-ONE.wav		<audio sample for the patch>
CueSample-TWO.wav		<audio sample for the patch>
CueSample-THREE.wav		<audio sample for the patch>
CueSample-FOUR.wav		<audio sample for the patch>
test_chn1.txt			<dataset for channel1>
test_chn2.txt			<dataset for channel2>
test_chn3.txt			<dataset for channel3>
test_chn4.txt			<dataset for channel4>
test_chn13.txt			<dataset for channel13>
test_chn14.txt			<dataset for channel14>
test_chn15.txt			<dataset for channel15>
test_chn16.txt			<dataset for channel16>
[Sonification]K and NH4.xlsx		<original dataset>
FeedbackSheetWithQuestions_ES.docx	<completed questionnaire_U1>
FeedbackSheetWithQuestions_AR.docx<completed questionnaire_U2>
FeedbackSheetWithQuestions_ES2.docx<completed questionnaire_U1_2> after an extra interview, U1 submitted a modified version

________________________________________________________________________________________________________
Guideline for running the patch:

After run the patch (Seq1-4 is already connected to Chn13-16 playback system.)
- You need to set the the volume for <CHN13-16> <Speech Cues> and <Click Sound>
Recommend levels are:                         86dB               91dB                          100dB

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

The green button is for start/stop playing.
- Click the green button to start a sonification session for data from Chn13-16.

Chn14 is the target problematic sensor we want to identify by this patch in this session.
Click sounds will be observed in the beginning of a session for about 1 minute in other sensors Chn13, Chn15 and Chn16
But for Chn14, click sounds still frequently appear after 1 minute, which indicates it is problematic (acting very noisy) 

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Variables：
RangeforNote(Scaling ratio control)  			inside pdUpdateWindow
basicLoop(dataReadin rate)                			inside pdUpdateWindow

Duration of a whole group                  			inside pdtrigger
Interval between speech cue and note sequence 	inside pdtrigger
IOI						inside pdreadChn[xx]>>pdreadWindow
AlertRange1(AlertThreshold positive)			inside pdAlert
AlertRange2(AlertThreshold negative)			inside pdAlert
