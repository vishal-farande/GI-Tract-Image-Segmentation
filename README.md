The data we use is anonymized MRIs of patients treated with MRI guided radio therapy provided by the UW Madison Carbone Cancer Center. Specifically, the dataset contains 85 cases with 38496 scan slices of organs represented in 16-bit grayscale PNG format, and the annotations are provided in a csv format with the segmented areas represented as RLE-encoded masks. Sample csv annotations are shown in Table 1. An empty segmentation entry represents no mask presented for the class in the MRI scan slice.
Figure 2. Mask R-CNN Head Architecture: Faster R-CNN with ResNet Backbone
Figure 3. Mask R-CNN Head Architecture: Faster R-CNN with FPN Backbone
id class segmentation
case123 day20 slice 0081 large bowel 17746 6 18010 9 ...
case123 day20 slice 0081 small bowel
case123 day20 slice 0081 stomach 11055 4 11315 14 ...
case123 day20 slice 0082 large bowel 17481 4 17746 7 ...
case123 day20 slice 0082 small bowel 22236 2 22500 6 ...
case123 day20 slice 0082 stomach 11052 8 11314 15 ...
Table 1. MRI Scan Dataset CSV Annotation Sample


We use the Dice score to evaluate the mask predicted by our model against the true mask. As described above, the Dice score of a predicted mask is defined by
2|Mpred ∩ Mtrue|
|Mpred| + |Mtrue|
where Mpred is the set of pixels masked in (i.e. predicted to class ”1”) by the model, Mtrue is the set of pixels masked in by ground truth mask, and the absolute value means the number of pixels.