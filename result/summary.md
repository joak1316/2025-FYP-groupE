# Projects in Data Science (2025)

The purpose of this repository is to develop a model which correctly identifies cancerous skin lesions.
In 2022, approximately 331,722 new cases of melanoma were diagnosed worldwide, wcrf.org.
Melenoma and Skin Cancers account around 60,000 deaths per year according to Skin Cancer Statistics wcrf.org.
In Denmark Melenoma is the 5th most comman cancer who.org.

Going to the images we have seen I saw the hair removal algorithm struggle more specifically with white/grey haired images classified as hairy.
output_img_0713, output_img_0642 & output_img_0686 are good examples of this. If compared to output_img_0573 which is an image also with a lot of hair but darker and of a balding man.
It can be seen that algorithm has a better time processing this. All of these were conducted underneath the parameters of :
# apply hair removal
blackhat, thresh, img_out = removeHair(img_rgb, img_gray, kernel_size=10, threshold=2)

Moving forward it was best to adjust and develop higher contrast in the image such that these hairs could be removed. 













