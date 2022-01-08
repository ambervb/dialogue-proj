DatasetCreator:
  - Takes a folder with audiofiles from the AVA dataset, split according to AVA-Speech labels (NO_SPEECH, CLEAN_SPEECH, SPEECH_WITH_MUSIC, SPEECH_WITH_NOISE)
  - Outputs two files: a numpy array of half-second samples and a numpy array with corresponding labels
  - Is used to create datasets for the first model

SpeakerCombiGenerator:
  - Takes a folder with audiofiles, speaker ID in filename, and creates combinations of half-second excerpts, balanced 50/50 between same speaker and different speaker combinations.
  - Outputs these combinations in a numpy array, along with an array with corresponding labels
  - Is used to create datasets for the second model

TestAudioGenerator:
  - Takes two folders: one with 'no voice' audio files from CHIME-Home and one with 'voice' audio files from LibriSpeech, speaker ID contained within the filename.
  - Outputs a generated wav file of 10 minutes length, consisting of a mix of voice and no voice audio to roughly simulate a conversation in a household environment. Also outputs two arrays of labels: one with speaker IDs when the corresponding speaker is talking, and 'false' if there is no speech. The other indicates with 'true' when there is a conversation present as a whole.
