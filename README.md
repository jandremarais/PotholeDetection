# Pothole Detection

This repository contains all the files and code necessary to reproduce my winning solution to the pothole detection problem given at the [MIIA - Deep Learning Hackathon](http://machineintelligenceafrica.org/activities/hackathon/). I hope this can be helpful to the participants new to the field of Machine/Deep Learning (or anyone else).

Note, since this was a hackathon, we had <10 hours to solve the problem. I'm sure there is still plenty of room for improvement and wouldn't be surprised if the code contains some bugs. I'll leave that to you to discover. Feel free to contact me if you have any questions and/or suggestions (maraisjandre9@gmail.com).

## Setup

I strongly recommend the cloud service, [Crestle](crestle.com). It takes 3 minutes to create an account and two clicks to open up a Jupyter Notebook with all the necessary libraries pre-installed and access to a powerful GPU.

Once your server is set up, clone this repo with the terminal command

``` 
git clone https://github.com/jandremarais/PotholeDetection.git 
```

Since the data is too big to save in a Github repo, you need to download it from [this](https://drive.google.com/open?id=0B1IZ6xxwxyvTcWNOWHAxeVgyTlU%C2%A0) Google Drive link. If using a cloud server, you can download the data with this command (thanks to [this](https://stackoverflow.com/a/39225039/6785054) SO answer)

```
python gddown.py 'file_id' 'file_destination'
```

and then extract files with `jar -xf train.zip`.

Note the directory structure:

```{txt}
data  
├── test  
│   └── unknown  
│       └── QCiNkpJJqhUrhJw.JPG  
├── train  
│   ├── negative  
│   │   └── QBvfRmpwrRbuhxE.JPG  
│   └── positive  
│       └── QBJSjQDEIQPuaxb.JPG  
└── valid  
    ├── negative  
    │   └── QbKxDKiHtsYBtZq.JPG  
    └── positive
        └── QPJVBLDFqTEnvrc.JPG 
```

The images inside the folders are only samples and should be deleted before downloading the data.

`data_crop` follows the same structure. Its contents will be created by a code cell in the `solution.ipynb` notebook. 

**Edit:** The data is no longer available at that link. I will contact the organisers to explore alternative options.

The folder `custom_layers` and the files `densenet121.py` and `resnet_101.py` are from [this](https://github.com/flyyufelix/cnn_finetune) awesome repo. It contains code to create common ConvNet architectures in Keras, including pretrained ImageNet weights. See the `README.md` of the original repo to get access to the pretrained weights and save them in the `models` directory (again using the `gddown.py` script).

Now you are ready to run the code in the `solution.ipynb` notebook. I've included some explanations and comments in-between the code cells to increase readability.
