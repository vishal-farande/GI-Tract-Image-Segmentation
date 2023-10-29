The data we use is anonymized MRIs of patients treated with MRI guided radio therapy provided by the UW Madison Carbone Cancer Center. Specifically, the dataset contains 85 cases with 38496 scan slices of organs represented in 16-bit grayscale PNG format, and the annotations are provided in a csv format with the segmented areas represented as RLE-encoded masks. Sample csv annotations are shown in Table 1. An empty segmentation entry represents no mask presented for the class in the MRI scan slice.


We use the Dice score to evaluate the mask predicted by our model against the true mask. As described above, the Dice score of a predicted mask is defined by
2|Mpred ∩ Mtrue|
|Mpred| + |Mtrue|
where Mpred is the set of pixels masked in (i.e. predicted to class ”1”) by the model, Mtrue is the set of pixels masked in by ground truth mask, and the absolute value means the number of pixels.
