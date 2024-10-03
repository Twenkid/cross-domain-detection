# cross-domain-detection
Editing demo.py of the original repo

https://github.com/naoto0804/cross-domain-detection

Edit demo.py:

...
 
See Colab:  Drawings-paintings-clipart-cross-domain-detection-3-10-2024.ipynb


In order to run one of the demos I found that a line in demo.py had to be changed from voc0712 to the name of the model I used: watercolor_dt_ssd300.

model = SSD300(
    n_fg_class=len(voc_bbox_label_names), pretrained_model='watercolor_dt_ssd300') #voc0712')

It produced a correct box. With the original voc0712 it was failing to load voc0712 (I don't know why it has to since an URL is given)

python demo.py input/watercolor_142090457.jpg output.jpg --gpu 0 --load models/watercolor_dt_pl_ssd300

(I actually used it without --gpu on a CPU session in Colab)

However with dt_ssd300:
python demo.py input/watercolor_142090457.jpg output.jpg --gpu 0 --load models/watercolor_dt_ssd300

Now that I read the whole readme.md, I see that _pl_ stands for pseudo labeling, I don't know is it a problem and haven't tried the right way, that could be another session.

https://github.com/Twenkid/cross-domain-detection
