# CS445 Final Project

## Basketball Image Detection

This repository contains all the code, input data, and results of the basketball image detection project completed by Evan Chen (echen48), Elliot Sherman (ehs4), and Selina Tang (sytang2). Some of the initial work was done via Colab, but the final version of the code ran can be found in `src/CS445_final_code.ipynb`. The repository is located at https://github.com/zuyouchen/cs445-final-proj. 

### Running The Code 
To run the code and reproduce results, please use a Python 3.12.7 environment with the requirements specified by `src/requirements.txt`. An easy way to do so would be to create a `venv` and then `pip install -r requirements.txt` once inside the `src` directory. Then, run the code inside the `src/CS445_final_code.ipynb` - if this file is having trouble loading, our code can also be viewed via `src/CS445_final_code.pdf`. 

### Organization 
The organization of this repository is as follows:

- `/src` contains the notebook file and project dependencies 
- `/results` contains all images and videos that are results of running the basketball detection algorithm 
    - `/results/images/` contains final detection results overlayed on single individual frames
    - `/results/intermediate/` contains intermediate detection visualizations used to debug and understand the algorithm 
    - `results/videos/` contains the compiled videos where the detection was ran on each frame, including the final video we use to showcase our results (`results/videos/final_compiled_detections.mp4`), which is a combination of all other videos in this folder 
- `/data` contains the downloaded clips and videos with basketballs, and subdirectories include extracted frames we use as input to our algorithm 

### Data and Inspiration
Our data can be found at https://github.com/zuyouchen/cs445-final-proj/tree/main/data. 

Data Sources (in order of appearance in final video `results/videos/final_compiled_detections.mp4`):
- `data/free_throws_urichmond.mp4`: https://www.youtube.com/watch?v=TI5MeQuMWqA, clipped and extracted at 20 FPS
- `data/curry_kerr_free_throws.mp4`: https://makeagif.com/gif/stephen-curry-vs-steve-kerr-free-throw-contest-kvxAXL, extracted at 11 FPS
- `data/suns_warriors_kd3.mp4`: https://thehighlow.io/video/ids?ids=25QoIK, extracted at 30 FPS 
- `data/dame_logo_three.mp4`: https://www.youtube.com/watch?v=eEYpDGXJiTg&ab_channel=TopFloorHoops, clipped and extracted at 25 FPS
- `data/guangdong_beijing.mp4`: https://www.youtube.com/watch?v=1subqwgyDDY, clipped and extracted at 25 FPS 

The paper that this implementation is inspired by is *A New Method of Object Segmentation in the Basketball Videos* (Wu et. al, 2006) DOI: 10.1109/ICPR.2006.122

### Results (Frames)
As mentioned in Section 4 of our report, we have created a table of successful and unsuccessful frames saved by video under results. The frame number is appended at the end of files in `results/intermediate` and `results/images`.

| Original Video                  | Successful Frames | Failed Frames (No Detection) | Failed Frames (False Positives) |
|---------------------------------|-------------------|------------------------------|---------------------------------|
| data/free_throws_urichmond.mp4  | 180, 310          | 36, 167                      |                                 |
| data/curry_kerr_free_throws.mp4 | 30, 76            | 45                           | 46                              |
| data/suns_warriors_kd3.mp4      | 14, 176           | 1                            | 102                             |
| data/dame_logo_three.mp4        | 275, 295          | 2                            | 37                              |
| data/guangdong_beijing.mp4      | 220, 272          |                              | 1, 128                          |