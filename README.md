
# Ex.No:4 Design an android application Send SMS using Intent.


## AIM:

To create and design an android application Send SMS using Intent using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as smsintent and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Send SMS and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to create and design an android application Send SMS using Intent.
Developed by: Sanjay.R
Registeration Number : 212222220038
*/
```

## MainActivity.java:

```
package com.example.app4;


import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText phoneNumber, messageText;
    Button btnSendSMS;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        setTitle("MY APP"); // optional, overrides label

        phoneNumber = findViewById(R.id.phoneNumber);
        messageText = findViewById(R.id.messageText);
        btnSendSMS = findViewById(R.id.btnSendSMS);

        btnSendSMS.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String number = phoneNumber.getText().toString().trim();
                String message = messageText.getText().toString().trim();

                if (!number.isEmpty() && !message.isEmpty()) {
                    Intent intent = new Intent(Intent.ACTION_SENDTO);
                    intent.setData(Uri.parse("smsto:" + number));
                    intent.putExtra("sms_body", message);
                    startActivity(intent);
                }
            }
        });
    }
}

```
## activitymain.xml:

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:orientation="vertical">

        <EditText
            android:id="@+id/phoneNumber"
            android:layout_width="200dp"
            android:layout_height="wrap_content"
            android:hint="Enter Phone Number"
            android:inputType="phone"
            android:minHeight="48dp" />

        <EditText
            android:id="@+id/messageText"
            android:layout_width="200dp"
            android:layout_height="wrap_content"
            android:layout_marginTop="10dp"
            android:hint="Enter Message"
            android:inputType="textMultiLine"
            android:minHeight="48dp" />

        <Button
            android:id="@+id/btnSendSMS"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Send SMS"
            android:layout_gravity="center"
            android:layout_marginTop="20dp"/>
    </LinearLayout>


</RelativeLayout>

```

## OUTPUT

![Screenshot 2025-04-12 112901](https://github.com/user-attachments/assets/8ef30ed3-91a8-43ec-a883-bb60675024ec)
![Screenshot 2025-04-12 113123](https://github.com/user-attachments/assets/2c12ea60-5ada-44ab-8e87-6a78bf0c1862)

![Screenshot 2025-04-12 113138](https://github.com/user-attachments/assets/32206445-b3a3-449f-a1b3-4d43891841d2)




## RESULT
Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.
