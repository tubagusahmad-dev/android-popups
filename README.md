[![](https://jitpack.io/v/tubagus216/PopUps.svg)](https://jitpack.io/#tubagus216/PopUps)

# PopUps
This is simple and lightweight android library to make PopupMenu and ContextMenu with icon and beautiful UI :D

## Instalation

Add it in your root build.gradle at the end of repositories:
```
allprojects {
  repositories {
		...
		maven { url 'https://jitpack.io' }
	}
}
```
Add the dependency
```
dependencies {
	implementation 'com.github.tubagus216:PopUps:v0.1.0'
}
```


## Use It
```java

// View such as Button, TextView ListView etc.

private void showMenu(View view, boolean isPopUp){  
  
  //Menu Builder
  
  MenuBuilder builder = new Menu.Builder().build(); 
  builder.addItem(new MenuItem("Android", R.drawable.ic_android));
  builder.addItem(new MenuItem("Share", R.drawable.ic_share));
  
  PopUps.createWith(view)
          .instanceAs(isPopUp ? Menu.asPopUpMenu() : Menu.asContextMenu()) //Showing popup or contextmenu
          .setMenu(builder)
          .setOnItemClickListener(new PopUps.OnItemClickListener() {
              @Override
              public void onItemClickListener(int position, MenuItem item) {
                  Toast.makeText(getApplicationContext(), item.getTitle(), Toast.LENGTH_LONG).show();
              }
          })
          .show();
}
```
Full code [here](https://github.com/tubagus216/PopUps/blob/main/app/src/main/java/dev/tubagusahmad/popups_example/MainActivity.java)
