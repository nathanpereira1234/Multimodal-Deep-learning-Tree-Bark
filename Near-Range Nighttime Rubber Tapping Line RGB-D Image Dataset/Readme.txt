** NEARCAM Rubber Tapping Line Image Dataset **

-	An image dataset for tapping line detection

- 	Data collection : August 2018 to September 2018

- 	Owner/contact: Rattachai Wongtanawijit, 
		Computer Engineering, Prince of Songkla University, HatYai, Thailand

#####################################
** >Folders and --Files Structure **
#####################################

> annotations : storing ground truth 
	>> TaplinePixels : directory contains Tapping Line Data in 1280x720 pixels, 1-bit grayscale PNG image
	
	--TaplineBox.csv : Tapping Line Bounding Box in csv file, line no = image name, 
						Comma delimiter x, y, w, h = [x y width height] = [image_column image_row box_width box_height]
	
	--TaplineBox.JSON : Tapping Line Bounding Box in JSON format,
						image name as a dict Key ( ex. "0001", "0002", ... ),
						"xb" "yb" "wb" "hb" as a sub-key = [image_column image_row box_width box_height]

> images : directory for image data
	>> RGB1 : directory contains RGB1 Images, 1280 by 720, width by height pixels, 
			24-bit (8-bit/channel) RGB PNG images

	>> RGB2 : directory contains RGB2 Images, 1280 by 720, width by height pixels, 
			24-bit (8-bit/channel) RGB PNG images

	>> Depth-u8 : directory contains Depth Images, 1280 by 720, width by height pixels, 
			8-bit grayscale PNG images, 8-bit pixel's values map by 255 = 20.0 centimeter,
			0 = 40.0 centimeter from the camera 0-depth plane

	>> Depth-u16 : directory contains Depth Images, 1280 by 720,width by height pixels, 
			16-bit grayscale PNG images, 16-bit pixel's values 65535-0, 
			increment value of 1 = 0.1 millimeters outward from the camera 0-depth plane

> k-fold : directory for train-test image name indicies (logical mask), 
			splited for k-fold cross-validation (k=5)
	--c.mat : MATLAB K-fold cross validation partitioner object
	>> fold_1
		--train.txt : csv(txt) file contains training image mask, newline delimiter
		--test.txt	: csv(txt) file contains test image mask, newline delimiter

	>> fold_2 ..
	>> fold_3 ..
	>> fold_4 ..
	>> fold_5 ..