# OpenCV

 _Open Source Computer Vision Library_ is a library of programming functions mainly aimed at real-time computer vision. 

 **Source**: https://www.docs.opencv.org/master/

 **Installation**: https://docs.opencv.org/2.4/doc/tutorials/introduction/windows_install/windows_install.html

  ## Introduction
 
  **Image Recognition**: https://blog.ieeemanipal.tech/image-recognition/

  **Image Analysis**

    //Importing Library
    import cv2 as cv

    //Reading an Image
    img = cv.imread('name.jpg')

    //Converting color image to grayscale
    gray=cv.cvtColor(img,cv.COLOR_BGR2GRAY)

    //Displaying the image
    cv.imshow('name',img)
    cv.waitKey(0)
    cv.destroyAllWindows()
    //here 'name' is the title of the displayed image

 **Video Analysis**
  
    //Reading a video file
    cap= cv.VideoCapture('video.mp4',0)

    //Capturing Live Video
    cap= cv.VideoCapture(0)

    //Displaying Video 
    while True:
       ret, frame=cap.read()
       cv.imshow('video',frame)
       if cv.waitKey(1) & 0XFF==ord('q'):
          break
    cap.release()
    cv.destroyAllWindows()

    //Writing Output to File
    fourcc=cv.VideoWriter_fourcc(*'XVID')
    out=cv.VideoWriter('output.avi',fourcc,20,(640,480))
    out.release()

**Drawing Images**

 1. Line
    
        cv.line(img,starting point,end position,colour(bgr))

 2. Rectangle
  
        cv.rectangle(img,point, diagonal point,color, width)

 3. Circle
 
        cv.circle(img,centre point,radius,color,-1(if circle is needed to be filled))

 4. Polygon
   
        import numpy as np
        pts=np.array((bunch of points),np.int32)
        pts=pts.reshape((-1,1,2))
        cv.polylines(img,[pts],True(whether or not final point should be connected to initial point), color)

**Text on Images**

    //Select a font
    font=cv.FONT_HERSHEY_SIMPLX
    cv.putText(img(on which text should be written), text to be written, starting point say (0,130),font, size(1), color, spacing b/w letters, cv.LINE_AA)

 **Basic Image Operations**

        px=img[@location value]
        print(px)
        //gives color value at point

    ROI => Region of Image

        roi=img[100:150,100:150]
        print(roi)
        //prints only that region

    Changing a region of an Image
  
        img[100:150,100:150]=[255,255,255]
        
    Shifting a part of image from one region to another
 
        roi=img[37:111,107:194]
        img[0:74,0:87]=roi
        //Both should be of same size

 **Image Arithmetic and Logic Operations**

        add=img1+img2

        [OR]
     
        add=cv.add(img1,img2)
        //This adds all pixel values together, so we do not get a proper image as there will be variations in color

        [OR]

        weighted=cv.addWeighted(img1,0.6,img2,0.4,0)
        //adds 60% of first image and 40% of second image




    

     
     
  
  




