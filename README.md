# Tips for RTL:
1. Use this module to force language better than use device language [link](http://shareourideas.com/2013/12/02/titanium-locale-module-for-both-android-and-ios/)
2. Add  `android:supportsRtl="true"` into <application> tag into `tiapp.xml
```xml
<android xmlns:android="http://schemas.android.com/apk/res/android">
    <manifest>
        <application android:supportsRtl="true" />
    </manifest>
</android>
```
3. Use if in .tss file to switch RTL & LTR
```javascript
// alloy.js
Alloy.Globals.isRTL = Ti.Locale.currentLanguage === 'ar';
```
```css
'#exampleLabel' : {
	color: ‘red'
}
'#exampleLabel[if=Alloy.Globals.isRTL]' : {
	right: 5
}
'#exampleLabel[if=!Alloy.Globals.isRTL]' : {
	left: 5
}
```
4. Force your app to work on iOS 9+ _check good and bad points below_
5. Force Android 4.2 as minimum,

# Good points (iOS 9+ & Android 4.2+)
1. LeftNavButton & RightNavButton will inverted automatically
2. Default ListView/TableView templates will inverted
3. iOS Window.open() transition will be inverted
4. ActionBar and menus will be inverted
5. CollectionView on iOS will inverted

# Bad points of Titanium with RTL
Some items will not inverted automatically and you have to use tss (explained in 1st part) to handle position by yourself
1. Since Android 4.2 RTL supported natively for linearlayout (ScrollView with horizontal/vertical layout), but Titanium not using any of this, they calculate the top and left for both iOS and Android  [ref](http://android-developers.blogspot.com.eg/2013/03/native-rtl-support-in-android-42.html)
2. Text can aligned automatically in native for both iOS and Android, [Android](http://developer.android.com/intl/es/reference/android/view/View.html#attr_android:textDirection) [iOS](https://developer.apple.com/library/ios/documentation/UIKit/Reference/NSString_UIKit_Additions/index.html#//apple_ref/c/econst/NSTextAlignmentNatural)

# Example
Sooooon
