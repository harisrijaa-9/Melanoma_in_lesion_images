# Melanoma_in_lesion_images
### Identify melanoma in lesion images

# My Approach



We used **EfficientNet [B0-B6]**, **Resnest**,**Resnext**, with Sizes **192x192** **256x256** **384x384** **512x512** **768x768** **384x512**[HxW]

## Summary

#### What Worked for me

- Heavy TTA (X20)
- Cutmix
- Coarse dropout
- SWA(Stochastic Weight Averaging)
- Loss-Label Smoothing, BCE
- Optimizers - AdamW, Adam
- 2018, 2020 and malignant datasets
- 5 checkpoints' prediction averaging(stabalised our model's predictions)
- some models were trained with different height width ratios

#### What didn't Work for me

- Loss functions-Focal loss, dice loss
- Optimizer- Ranger
- Hair removal/addition
- Pseudo labelling
- 2019 dataset
- Preprocessing techniques from [Aptos Competition](https://www.kaggle.com/c/aptos2019-blindness-detection)
- Progressive learning

### Ensembling techniques

- Weighted average
- Power Average
- Minmax ensemble(didn't help)<br>
<br>3hr before end of competition we came across rank ensembling and and we did this ensemble and got **0.9697** for our last submission

## Final Submission

Different approaches.

1.  All 15+ pytorch gpu solution models(with context) - 0.9530 (public LB) 0.9380 (private LB) 0.9541 (CV)
2.  15+ pytorch model (with context) and 15+ tf models (without context) - 0.9627 (public LB) 0.9470 (private LB) 0.9618 (CV)
3.  Blend of public submission with 2nd submission with post proccessing technique - 0.9697 (public LB) 0.9126 (private LB) (overfitted)
all the above were also ensembled with the meta only submission.
<br>
