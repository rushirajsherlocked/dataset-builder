# dataset-builder

A script to help you quickly build custom computer vision datasets for classification and detection.

If you opt for the detection task, the script uploads the downloaded images with the corresponding labels to http://makesense.ai (or locally to http://localhost:3000) so that all you have to do in annotate yourself. 

Once the annotation is done, your labels can be exported and you'll be ready to train your awesome models.

# Requirements:

- google_images_download: ``pip install google_images_download``
- Selenium: pip install - U selenium
- Chrome Driver

In case you wish to run make-sense locally:

```bash
# clone repository
git clone https://github.com/SkalskiP/make-sense.git

# navigate to main dir
cd make-sense

# install dependencies
npm install

# serve with hot reload at localhost:3000
npm start
```

# Example:

When you run the script, you can specify the following arguments:

- `output_directory`: the root folder when images are downloaded
- `limit`: the maximum number of downloaded images per category
- `delete_history`: whether you choose to erase previous downloads or not
- `task`: classification, detection or segmentation
- `driver`: path to chrome driver

```bash
python dataset_builder.py --limit 20 --delete_history yes
```
Once the script runs, you'll be asked to define your classes (or queries)

<img src = "./images/screenshot.png" >

Here's what the output looks like after the download:

<img src = "./images/output.png" width=350>

# Object detection with make-sense:

Makesense is an awesome open source webapp that lets you easily label your image dataset for tasks such as localization.

You can check it out here: https://www.makesense.ai/ 
You can also clone it and run it locally (for better performance): https://github.com/SkalskiP/make-sense

In order to use this tool, I'll be running it locally and interface with it using Selenium: Once the dataset is downloaded, Selenium opens up a Chrome browser, upload the images to the app and fill in the label list: this ultimately allows you to annotate.



