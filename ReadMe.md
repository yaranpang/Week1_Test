# week1_test

## Insert Api
1. **How long does it take to insert one image and this image can be searchable?**  
    It is tried to insert four images that is loaded from internet, it takes about total 3 min and 56 sec to finish indexing. The average processing time is 1min.
    <img src="img1.png" width=890/>

    It is tried to use tagging way of inserting the pictures, it took about 2 min and 13 sec to finish uploading pictures. The average processing time is 0.5min
    <img src="img2.png" width=890/>

     It is tried to use one image to insert picture, it took about 11 second to finish uploading pictures with indexing file.
    <img src="img3.png" width=890/>

    It is tried yesterday using external connection, it took 4 min 59 second to finish uploading pictures with indexing file.
    <img src="img4.png" width=890/>

    <br />
2. **Where can you get the application key for integrating a     new application?  Please paste the screenshot below**  
    In the new app, under integration -> Client-side Integration can see the app keys.
    <img src="img5.png" width=890/>

## Search Api

1. **Can you paste a screenshot of you successfully get the response from the Postman given an image URL as the input using /uploadsearch?**    
    <img src="img6.png" width=590/>

<br />

2. **What is the meaning of ‘fq’ and 'fl' parameter?**  
    The fl is the url field name which is same as the field name in upload .csv file. I did not see fq param in the params. 
    <img src="img7.png" width=590/>  
    From development docs, it shows the definition of fl and fq
    <img src="img8.png" width=590/>

<br />

3. **What is the image size/resolution requirement/limitation for upload search?**  
    From the development document, the image size is 10MP, it is suggested to be around 1024 * 1024 pixels
    <img src="img9.png" width=590/>
    <img src="img10.png" width=890/>
<br />

4.  **What does the similarity score mean?**    
    The similarity score suggest how many percentage of similarity of the search image with images in the database with category or other metadata defined in the schema.

<br />

5. **What’re results will you return if you don’t find anything similar in our database?**  
    <img src="img11.png" width=590/>
    <img src="img12.png" width=890/>
<br/>

6. **Which search endpoints support automatic object detection?**   
    /v1/image/recognize

7. **Which parameters to use when a user wants to filter by price? Please give an example parameter?**  
    <img src="img13.png" width=890/>
    <img src="img14.png" width=890/>

## Image database ingestion
1. **If the customer shares their images with ViSenze, how does ViSenze handle the data security?**  
    <img src="img15.png" width=890/>

<br />

2. **What is the approximate indexing time for a new image given a base set of 500,000 images? Does this time increase linearly?**    
Not able to do experiment on this but from understanding the way system works, the priority is given to large size image file. Performance is auto scaled if more resouce is needed to process large amount of image files.
<br />

3. **Which are the mandatory fields of uploading images for furniture domain? What about fashion domain?**   
    Image Id(im_id), image url(im_url) and category(did not find difference from metadata definition). Category field is discarded with increasing accuracy of algorithm. Features extracted from image are more accurate to define image compare to previous version.

<br />

4. **Which are the supported methods for image database ingestion?**  
    method: post
    api: /insert

<br />

5. **Can an image database be deployed to more than 1 data centers?**  
    Yes. Can select more than one data centers.
    <img src="img16.png" width=890/>

## Visual Search Integration

1. **Is integration of  /search and /uploadsearch using Javascript feasible?**
    visenze javascript sdk supports it.

<br />

2. **What is the throughput our visual search system can support? Does this scale horizontally?**
The througput of search system can be adjusted based on the speed image provider can support. It can be scaled when the amount of images that needed to be searched is large(not sure).
<br />

3. **Does /uploadsearch support .ai files? If not, what is the error message?**  
    It does not support .ai file, the error message shows file format does not support.

<br />

4. **Which API is the fastest, which is the slowest, among /search, /uploadsearch, /discoversearch? Can you explain why?**  
    /search is the fastest. It is fast since it only search the image from the database that have been indexed.
    /discovrsearch is the slowest. It needs to first indexing the image to find features and categorize all the features. Each feature categorization will show the results that has similar features.



















