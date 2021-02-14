# FGVC Video completion in google colab using google drive

## Introduction

As the time of this writing (February, 2021) [FGVC](https://github.com/vt-vl-lab/FGVC) is one of the best video inpainting projects out there.

The authors did a great work and made it as easy a possible for others to use their video inpaiting tool. They even made a [google colab notebook](https://colab.research.google.com/drive/1pb6FjWdwq_q445rG2NP0dubw7LKNUkqc?usp=sharing).

However, their tool is command-line based. I struggled a little to use it with my own data in colab. I was not very confortable with the workflow.
 - Every time I needed to run it, I needed to clone the tool and download the models again.
 - It was hard for me to upload my own data and adjust the tool parameters using the %%bash magic command.
 - It was hard for me to se the results after running the video completion.

So I decided to adapt the original [google colab notebook](https://colab.research.google.com/drive/1pb6FjWdwq_q445rG2NP0dubw7LKNUkqc?usp=sharing) for my personal use.

I think it might me useful for others. Check it in [nbviewer](https://nbviewer.jupyter.org/github/brunomsantiago/FGVC_video_inpaint_colab_drive/blob/main/FGVC_video_completion.ipynb) or in [google colab](https://colab.research.google.com/github/brunomsantiago/FGVC_video_inpaint_colab_drive/blob/main/FGVC_video_completion.ipynb).

## What I changed
 - I wrote a function to view data data (folders with image files) as animated gif. It allows to easily see the results in google colab.
 - The [FGVC tool](https://github.com/vt-vl-lab/FGVC) and the deep learning models are saved to google drive, which is mounted at the beginning of the notebook.
 - Both input data and results are also saved to google drive.
 - The FGVC tool now runs in Python instead of bash.
   - To do that I change the current working directory in Python, import the video_completion_seamless() function from video_completion.py
   - The I simulate the argparse result with a custom dict and call the function
 - I also added a little bit of code to measure the execution time of video_completion_seamless() function.

# How to use
 1. Open FGVC_video_completion.ipynb in [google colab](https://colab.research.google.com/github/brunomsantiago/FGVC_video_inpaint_colab_drive/blob/main/FGVC_video_completion.ipynb).
 2. Mount your google drive.
 4. (just once) Download the tool and model to your google drive.
    - You can use the commented bash code block, located in cell 2.1. Run it once and comment it again.
    - As february 2021, there is no need to install any package on google colab (pytorch, etc).
 5. Activate GPU on colab.
 6. Configure the input data at cell 3.3.
    - By default it uses the Tennis demo from FGVC.
 7. Run all cells.
 8. See the results at cell 3.6.
