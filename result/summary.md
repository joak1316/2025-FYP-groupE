# Projects in Data Science (2025)

The purpose of this repository is to develop a model which correctly identifies cancerous skin lesions.
In 2022, approximately 331,722 new cases of melanoma were diagnosed worldwide, wcrf.org.
Melenoma and Skin Cancers account around 60,000 deaths per year according to Skin Cancer Statistics wcrf.org.
In Denmark Melenoma is the 5th most comman cancer who.org.

Medical image analysis plays a crucial role in diagnosing skin conditions, such as melanoma and other dermatological diseases. However, hair in clinical images can obstruct important details, making it difficult for automated algorithms and human experts to accurately assess lesions. Removing hair from images improves the visibility of skin features, allowing for better segmentation and analysis.

In this project, we implement a hair removal method based on morphological operations and inpainting techniques using OpenCV. The method detects hair strands, creates a mask, and fills in the obstructed areas using surrounding pixel information.

While annotating the images, we generally agreed on the classification of hair presence (None, Some, A Lot). However, there were still some mismatches in ratings. The differences were mostly due to varying strictness in defining 'having hair.' Some team members classified an image as 'No Hair' only if there was absolutely no visible hair, while others were more lenient and allowed for a small presence of hair as long as it did not obstruct the lesion significantly.


Going to the images we have seen I saw the hair removal algorithm struggle more specifically with white/grey haired images classified as hairy.
![output_img_0713.png]("C:\Users\Peter\Documents\Data Science\Semester 2 - Projects in Data Science\Mandatory Assignment\2025-FYP-groupE\result\output_img_0713.png")output_img_0713, output_img_0642 & output_img_0686 are good examples of this. If compared to output_img_0573 which is an image also with a lot of hair but darker and of a balding man.
It can be seen that algorithm has a better time processing this. All of these were conducted underneath the parameters of :


apply hair removal
blackhat, thresh, img_out = removeHair(img_rgb, img_gray, kernel_size=10, threshold=2)


Moving forward it was best to adjust and develop higher contrast in the image such that these hairs could be removed. 













