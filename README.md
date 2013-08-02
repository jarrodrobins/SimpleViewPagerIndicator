*This has been forked from [https://github.com/Papercloud/SimpleViewPagerIndicator](https://github.com/Papercloud/SimpleViewPagerIndicator). However, since leaving Papercloud I don't have access to the repository anymore. Any future updates to SimpleViewPagerIndicator will be pushed [here](https://github.com/jarrodrobins/SimpleViewPagerIndicator) instead.*

SimpleViewPagerIndicator
========================
SimpleViewPagerIndicator is a small, easy to use class that you can add to your Android projects to graphically display the number of elements in a ViewPager, as well as allow users to quickly switch pages by touching the page indicators.

![SimpleViewPagerIndicator screenshot](http://i.imgur.com/QALrG.png)

After checking out some existing libraries for doing similar things, I found that many were overly complicated for what I was trying to accomplish. SimpleViewPagerIndicator is designed to allow developers to specify a simple (hence the name), customisable container in an XML layout file, and add elements (in the case of the screenshot, light bulbs) on the fly. The elements have two states - normal, and highlighted. Changing pages simply changes the image state.

Included in this repository is the SimpleViewPagerIndicator class itself, as well a a sample indicator layout file and a few small images. 

Installation
------------
+ Add the SimpleViewPagerIndicator class, view\_pager\_indicator.xml layout file and sample images to your project.
+ Import your project's R file in SimpleViewPagerIndicator.
+ In your activity's layout file, add: 

		<au.com.papercloud.pager.SimpleViewPagerIndicator
	        android:id="@+id/page_indicator"
	        android:layout_width="match_parent"
	        android:layout_height="wrap_content"
	        android:gravity="center" />
   
+ In your activity that contains a ViewPager, just add:

		SimpleViewPagerIndicator pageIndicator = (SimpleViewPagerIndicator) findViewById(R.id.page_indicator);
		pageIndicator.setViewPager(pager);
		
+ Of course, you may also create the indicator in code and add it to your activity's content view. 
+ Any time the view pager's data is changed, be sure to call

		pageIndicator.notifyDataSetChanged();
		
+ Change the layout file and images to your heart's content. 
		
If you intend to add an OnPageChangeListener to your view pager, add it to the SimpleViewPagerIndicator instead.

Notes
-----
This is a simple set of files that I've decided to open source because I thought it'd be useful to someone else. In no way is it guaranteed to be highly optimised nor bug free. If anyone has any suggestions for improvement, please create a pull request. 

Licence 
-------
This project is licenced under the Apache Licence v2. You may use and change as you wish. No attribution is required.

Developed by Jarrod Robins 2012, 2013.
