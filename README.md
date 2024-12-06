
# Android note


### Copy text: ( java ) 
```bash
ClipboardManager manager = (ClipboardManager) getSystemService(Context.CLIPBOARD_SERVICE);
	ClipData data = ClipData.newPlainText("label","copy text");
	manager.setPrimaryClip(data);

```
### Call-web-location: ( java )
```bash
String sUri;	
sUri = " tel: +880 17094 09266"; //for calling
	sUri = " https://facebook.com "; //for website
	sUri = " geo: 24.56894, 95.854857 "; //for location
Intent i = new Intent(Intent.ACTION_VIEW, Uri.parse(sUri));
startActivity(i);

```
### auto link: ( xml )
```bash
android:autoLink = "all" or "phone" or "email"startActivity(i);
```
### Count Down
```bash
long duration = 1000 * 70;
    long interval = 1000;
    new CountDownTimer(duration,interval){

        @Override
        public void onTick(long millisUntilFinished) {
            long min = millisUntilFinished / 60000;
            long sec = (millisUntilFinished % 60000) / 1000;
            String second = String.valueOf(sec);
            if (sec < 10) second = "0"+second;
            tv_timer.setText("0"+min+" : "+second);
        }

        @Override
        public void onFinish() {
            tv_timer.setVisibility(View.GONE);
            tv_resend_otp.setVisibility(View.VISIBLE);
        }
    }.start();

```
### Nagigation / Status
```bash
<item name="android:navigationBarColor">@color/green</item>
<item name="android:statusBarColor">@color/green</item>
<item name="android:windowLightNavigationBar" tools:ignore="NewApi">true</item>
<item name="android:windowLightStatusBar" tools:ignore="NewApi">false</item>

```
### Splash Screen
```bash
<!-- drawable/splash.xml -->
<?xml version="1.0" encoding="utf-8"?>
<layer-list
    xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:drawable="@color/white"/>
    <item android:width="150dp"
        android:height="150dp"
        android:gravity="center"
        android:drawable="@drawable/ic_launcher_foreground"/>
</layer-list>

<!-- themes/themes.xml -->
<item name="android:navigationBarColor">@color/white</item>
<item name="android:statusBarColor">@color/white </item>
<item name="android:windowLightNavigationBar">true</item>
<item name="android:windowLightStatusBar">true</item>

<item name="android:windowBackground">@drawable/splash</item>

```
### Fragment
```bash

import android.app.Fragment; 
import android.app.FragmentManager;
import android.app.FragmentTransaction;

loadFragment(new LoginFragment());

private void loadFragment(Fragment fragment) {
    /*FragmentManager fm = getFragmentManager();
	FragmentTransaction fragmentTransaction = fm.beginTransaction();
	fragmentTransaction.replace(R.id.authFragment, fragment);//add
	fragmentTransaction.commit();*/
      getFragmentManager()
        .beginTransaction()
        .replace(R.id.authFragment, fragment)
        .commit();

}

```
### hideStatusAndNavigationBar : java
```bash
View decorView = getWindow().getDecorView();
    int uiOptions = View.SYSTEM_UI_FLAG_HIDE_NAVIGATION
            | View.SYSTEM_UI_FLAG_FULLSCREEN;
    decorView.setSystemUiVisibility(uiOptions);

```
### Lottie Animation
```bash
Boolean isCheckDone = false;
//xml e defind korte hobe
private void checkDoneLottieClick() {
    LottieAnimationView lav = findV……
    if(isCheckDone){
    	lav.setSpeed(-1);
isCheckDone = false;
    }else{
lav.setSpeed(1);
isCheckDone = true;
    }
    lav.playAnimation();nn
}
//==========================
Boolean isSwitchOn = false;
//xml e defind korte hobe
lav.setSpeed(1);//for firster
private void switchOnLottieClick() {
    LottieAnimationView lav = findV……
    if(isSwitchOn){
    	lav.setMinAndMaxProgres(0.5f , 1.0f);
isSwitchOn = false;
    }else{
lav.setMinAndMaxProgres(0.0f , 0.5f);
isSwitchOn = true;
    }
    lav.playAnimation();
}

```
### Spinner
```bash
<!-- XML::---- -->
<Spinner>

<!--  ARRAY::-- -->
<string-array name="category_array">
    <item>Transportation</item>
    <item>Housing</item>
</string-array>

// JAVA::----
String[] spinnerArray ;
Spinner CategorusSpinner;
spinnerArray = getResources().getStringArray(R.array.category_array);
CategorusSpinner = findViewById(R.id.category);
ArrayAdapter<String> spinnerAdapter = new ArrayAdapter<>(this,android.R.layout.simple_list_item_1,spinnerArray);
spinnerAdapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item);
CategorusSpinner.setAdapter(spinnerAdapter);
String category = categorusSpinner.getSelectedItem().toString();


CategorusSpinner.setOnItemSelectedListener(new AdapterView.OnItemSelectedListener() {
    @Override
    public void onItemSelected(AdapterView<?> parent, View view, int position, long id) {
        String ss = parent.getItemAtPosition(position).toString();
    }

    @Override
    public void onNothingSelected(AdapterView<?> parent) {
        //auto generate
    }
});


```
### Custom Alert Dialog
```bash
Context context = MainActivity.this;
View customDialog = LayoutInflater.from(context).inflate(R.layout.adding_dialog, null);
AlertDialog.Builder alertdialog = new AlertDialog.Builder(context);


alertdialog.setView(customDialog);
TextView submit = customDialog.findViewById(R.id.tv_submit);
TextView cancel = customDialog.findViewById(R.id.tv_close);

final AlertDialog dialog = alertdialog.create();
Objects.requireNonNull(dialog.getWindow()).setBackgroundDrawable(new ColorDrawable(Color.TRANSPARENT));
dialog.show();

submit.setOnClickListener(v -> {

    dialog.cancel();
});
cancel.setOnClickListener(v -> dialog.cancel());

```
### Radio Group and Button
```bash
<!--  XML:: -->
<RadioGroup
    android:id="@+id/rG>

    <RadioButton
        android:id="@+id/iR"
        android:text="Income"/>

    <RadioButton
        android:id="@+id/eR"
        android:text="Expense"/>

</RadioGroup>

// JAVA::
RadioGroup rG = findViewById(R.id.rG);
rG.clearCheck();
rG.setOnCheckedChangeListener((group, checkedId) -> {
    RadioButton rB = group.findViewById(checkedId);
});
//onclick
int selectedId = rG.getCheckedRadioButtonId();
if (selectedId == -1){
    //No Answer 
}else {
    RadioButton rB = rG.findViewById(selectedId);
    String text = rB.getText().toString();
}


```
### 1.	Dialog Fragment
```bash
null
```
### 2.	PHP mysql all join
```bash
null
```
### 3.	Mysql view
```bash
null
```
### 3.	Multithreading 
```bash
null
```
