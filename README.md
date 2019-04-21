### Use: 

1) Go to [colab.research.google.com](https://colab.research.google.com/) and log-in with Google account.
2) Select Github -> copy this git repo address -> select runner.ipynb
3) Go to your Google Drive, create a new folder, copy scripts & data to it
4) Fill `GDRIVE_DIR` in cell 5
5) Run cells 1-5
6) Update RUN cell with the name of the script we want to run (first string arg) and all of its parameters (second string arg) 
7) Execute run cell, click on tensorboard url (on ngrok.io domain)

### Notes: 
- Your whole GDrive is mounted under `/drive` and so you can access any data in it via realative path, e.g.  `../some-other-gdrive-root-folder/mydata.in`.
- The script specified in `run` cell is executed with current directory being `GDRIVE_DIR`.
- Sometimes the synchronization with GDrive doesn't work properly (e.g. you have the drive mounted and make a lot of changes from your computer / web interface). If that happens just kill the VM (cell 7) and start again. 
  - Try to not to work with your GDrive while training is underway. Might cause issues with logs / results not being properly synced. 
- If your script doesn't put logs to `./logs/` change the log folder in cell 4 (`LOG_DIR`).
- The execution limit of GColab can vary and so checkpointing frequently is adviced. 

### TODO: 
- Change current tensorboard from utils to [tensorboardcolab](https://medium.com/looka-engineering/how-to-use-tensorboard-with-pytorch-in-google-colab-1f76a938bc34)
- Change current GDrive mounting from some weird custom solution to Google's [drive.mount()](https://colab.research.google.com/notebooks/io.ipynb)

