1) apply gaussian blur
	2) apply grayscale
	3) apply canny edges
	4) define region of interest
	5) calculate hough lines
	6) draw lines
		a) iterate over each hough line
		b) get the slope of each hough line
		c) if slope is > 0 & < 1.5 it is the right line else < 0 &                    > -1.5 left line
		d) for right lines: iterate over end points of hough line
		c) store the coordinates of the 'highest' end point to use when 		   drawing the line
		d) repeat for left lines
		e) get the average of each left and right slope to use as main 		   	   slope	
		f) get the bottom x coordinates
			g) iterate over each point of each line
			h) determine the line equation (y=mx+b) based on the 				   point and its slope
			i) plug in the bottom (y) value to the line equation to 			   get the x end point 
			j) take the average of these x points for both left and 			   right
		h) draw the lines using acquired end points with cv2.line()
	7) cv2.addWeighted()