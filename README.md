General set up:

Python 3.8+ is required to run this file. Please run the requirements.txt file using the following command:
pip install -r requirements.txt
Please mention the correct path of requirements.txt in the above command

Speaker Diarization

audio-preprocessing-analysis.ipynb

    Functionality

        This file contains all the preprocessing steps for audio clustering.
        It will take a video, extract audio from it, and save the audio. It will read the saved audio,
        perform noise reduction, and sentence trimming. It can also save the the final preprocessed audio.

    Setup and Input File.

        The following directories must exist before running this file:
        -> videos/
        -> audios/
            -> without noise/
            -> preprocessing/

        The input file must be a mp4 video file placed inside videos/ folder. Extracted audio will be saved to a WAV audio file in audios/ folder. The denoised audio file will be saved in audios/without noise/ folder. Also, the final
        preprocessed files, with and without noise, will be stored in audios/preprocessing/ folder. 

speaker-diarization-two-features.ipynb

    Functionality

        This file contains all steps to perform audio clustering.
        It will take an audio as input, normalize it, extract audio features, scale the features, perform audio clustering, and save the clustered audio segments. It extracts MFCCs and ZCR features from the audios. It performs DBSCAN, K-Means, and Spectral Clustering.

    Setup and Input File.

        The following directories must exist before running this file:
        -> videos/
        -> audios/
            -> without noise/
            -> preprocessing/
        -> clusters/

        The input file must be any preprocessed audio file present in the audios/preprocessing/ folder. The csv file with clusters and features gets saved in clusters/ folder. Also, the final audio segment files will be stored in clusters/ folder. The number of clusters in K-Means must be changed depending on the number of speakers in the scrum meeting. Similarly, min_clusters parameter of Spectral clustering must be modified based on the number of speakers in the scrum meeting. Five speakers would mean 5 min_clusters and 5 n_clusters. 

speaker-diarization-five-features.ipynb

    It is almost as same as speaker-diarization-two-features.ipynb. The only difference is the number of features it extracts. It extracts three more features: Spectral Centroid, Spectral Bandwidth, and Spectral Rolloff.