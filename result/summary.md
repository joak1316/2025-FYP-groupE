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

 - apply hair removal
- blackhat, thresh, img_out = removeHair(img_rgb, img_gray, kernel_size=10, threshold=2)


Moving forward it was best to adjust and develop higher contrast in the image such that these hairs could be removed.


We also discovered that in the pictures with a marker there is often more noise after processing. The images become more blurry therefore, the lesions appear more faded and less distinguishable on the skin. One reason for this could be that the marker causes bias in the algorithm’s colour detection. It could be a possible way forward to tackle down this problem by training the algorithm to recognise the marker as well. 
A few examples for this error:
- img_0630.png
- img_0611.png
- img_0551.png



One possible approach to fix this error is to first identify the color of the marker, which in this dataset most often appears as blck, blue and darkblue. Instead of converting the image to grayscale, we can convert it to HSV and define a suitable HSV range to distinguish the marked area. For blue markers, an effective range would be:

Lower bound: [100, 150, 0]

Upper bound: [140, 255, 255]

Once the marker is detected, we can use the inpainting function to replace it with a background color that matches the person’s skin tone.

However, a  when the lesion and the marker have similar colors, making it difficult for the algorithm to differentiate between them. In such cases, alternative methods can be explored, such as analyzing the shape and compactnes of both the lesion and the marker. Since lesions typically have irregular, compact shapes, whereas markers tend to form thin lines or non-circular patterns, we could use this distinction to identify and remove the marker while preserving the lesion.

By looking at the dataset, most images with markers display reddish lesions, blue markers, and light skin tones, which makes this a good method. Examples of such images include img_0528, img_0556, and img_0610. This would therefore be a method we would explore further if we had more time to work on this project.







