# FGVC Video completion in google colab using google drive

## Introduction

As the time of this writing (February, 2021) [FGVC]((https://github.com/vt-vl-lab/FGVC) is one of the best video inpainting projects out there.

The authors did a great work and made it as easy a possible for other to use their video inpaiting tool. They even made a [google colab notebook](https://colab.research.google.com/drive/1pb6FjWdwq_q445rG2NP0dubw7LKNUkqc?usp=sharing).

However, their tool is command-line based. I struggled a little to use it with my own data in colab. I was not very confortable with the workflow.
 - Every time I needed to run it, I needed to clone the tool and download the models again.
 - It was hard for me to upload my own data and adjust the tool parameters using the %%bash magic command.
 - It was hard for me to se the results after running the video completion

So I decided to adapt the original [google colab notebook](https://colab.research.google.com/drive/1pb6FjWdwq_q445rG2NP0dubw7LKNUkqc?usp=sharing) for my personal use.

I think it might me useful for others.

## What I changed
 - I wrote a function to view data data (folders with image files) as animated gif. It allows to easy see the results in google colab
 - The [FGVC tool]((https://github.com/vt-vl-lab/FGVC) and the deep learning models are saved to google drive, which is mounted at the beginning of the notebook.
   - Both input data and results are also saved to google drive.
