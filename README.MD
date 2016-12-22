#CycleMenu 



## Setup and usage
To include this library to your project add dependency in **build.gradle** file:
```groovy
    dependencies {
        compile 'com.cleveroad:'
    }
```

Use the CycleMenu in layout file
```XML
<com.cleveroad.sy.cyclemenuwidget.CycleMenuWidget
        android:id="@+id/itemCycleMenuWidget"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        
        <!--  non mandatory params -->
        app:cm_autoMaxRadius="220dp"
        app:cm_autoMinRadius="10dp"
        app:cm_corner="right_top"
        app:cm_fixedRadius="200dp"
        app:cm_radius_scale_type="auto"
        app:cm_scroll_type="endless"
        app:cm_item_background_tint="#449955"
        app:cm_corner_image_src="@drawable/ic_corner_image"
        app:cm_ripple_color="#009933"
        />
/>
```
or programmatically
```JAVA
CycleMenuWidget cycleMenuWidget = new CycleMenuWidget(mContext);
cycleMenuWidget.setLayoutParams(new RelativeLayout.LayoutParams(ViewGroup.LayoutParams.WRAP_CONTENT, ViewGroup.LayoutParams.WRAP_CONTENT));           
container.addView(cycleMenuWidget);
```
To set menu resources from xml resource or Collection use:
```JAVA
cycleMenuWidget.setMenuRes(R.menu.menu_items);
cycleMenuWidget.setMenuItems(Collection<CycleMenuItem> items);
```

methods for changing any settings you can set via attribute in xml:
```JAVA
void setScrollType(SCROLL scrollType)
void setAutoMinRadius(int autoMinRadius)
void setAutoMaxRadius(int autoMaxRadius)
void setScalingType(RADIUS_SCALING_TYPE scalingType)
void setCorner(CORNER corner)
void setFixedRadius(int fixedRadius)
void setItemsBackgroundTint(ColorStateList itemsBackgroundTint)
void setRippleColor(int rippleColor)
void setCornerImageDrawable(Drawable cornerImageDrawable)
void setCornerImageResource(@DrawableRes int drawableRes)
void setCornerImageBitmap(Bitmap bitmap)

```

For listening changing menu state use
```JAVA
void setStateChangeListener( new OnStateChangedListener() {                                 
                                     void onStateChanged(CycleMenuWidget.STATE state){};                                 
                                     void onOpen(){};                                 
                                     void onClose(){};                                 
                                 })
```
For listening menu items clicks use
```JAVA
void setOnMenuItemClickListener( new OnMenuItemClickListener() {
                                        void onMenuItemClick(View view, int itemPosition) {}
                                    })
                                
                                
                                
```

For providing saving state listener use
```JAVA
setStateSaveListener( new StateSaveListener() {
                            void saveState(int itemPosition, double lastItemAngleShift){}
});
```

## Support

If you have any other questions regarding the use of this library, please contact us for support at info@cleveroad.com (email subject: "Android CycleMenu widget. Support request.")


## License
* * *
    The MIT License (MIT)

    Copyright (c) 2016 Cleveroad Inc.

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in all
    copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
    SOFTWARE.