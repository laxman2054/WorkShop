# WorkShop1_MAD

## Date: 24/10/2024
## Name: Alluguri Srikrishna Teja
## Reg.no: 212222040006
## Developing an Android Application Pass The Data Between The Activities Using Intent

## Procedure:
1. Open the android studio--->New Project.
2. And give the correct application name for the project.
3. And select the Java for the application.

## CODE:
## MainActivity.java code

```
package com.example.workshop1;

import androidx.appcompat.app.AppCompatActivity;
import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.os.Bundle;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

public class MainActivity extends AppCompatActivity {
    EditText e1,e2,e3,e4;
    Button res;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        e1=(EditText)findViewById(R.id.editTextTextPersonName);
        e2=(EditText)findViewById(R.id.editTextTextPersonAge);
        e3=(EditText)findViewById(R.id.editTextTextPersonEmailID);
        e4=(EditText)findViewById(R.id.editTextTextPersonPhNo);
        res=findViewById(R.id.button);
        res.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view)
 {
                //int n1=Integer.parseInt(e1.getText().toString());
                //int sum =1;
                //while(n1!=0)
                //{
                    //sum = sum * n1;
                    //n1--;
                //}
                Intent intent=new Intent(getApplicationContext(),SecondActivity.class);
                intent.putExtra("e1",e1.getText().toString());
                intent.putExtra("e2",e2.getText().toString());
                intent.putExtra("e3",e3.getText().toString());
                intent.putExtra("e4",e4.getText().toString());
                startActivity(intent);
            }
        });
    }
}



```


## SecondActivity.java code

```

package com.example.workshop1;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.content.Intent;
import android.os.Bundle;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class SecondActivity extends AppCompatActivity {

    TextView t1,t2,t3,t4;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);
        t1=findViewById(R.id.textViewName);
        Intent intent=getIntent();
        String r=intent.getExtras().getString("e1","e1");
        t1.setText(r);

        t2=findViewById(R.id.textViewAge);
        String e=intent.getExtras().getString("e2","e2");
        t2.setText(e);
        t3=findViewById(R.id.textViewEmailID);
        String s=intent.getExtras().getString("e3","e3");
        t3.setText(s);

        t4=findViewById(R.id.textViewPhNo);
        String u=intent.getExtras().getString("e4","e4");
        t4.setText(u);
    }
}



```


## ActivityMain.xml code

```

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:background="#FFFFFF">

    <TextView
        android:paddingTop="90px"
        android:id="@+id/textview"
        android:layout_width="match_parent"
        android:layout_height="55dp"
        android:fontFamily="sans-serif-black"
        android:lineSpacingExtra="12sp"
        android:text="ENTER THE DETAILS"
        android:textAlignment="center"
        android:textAppearance="@style/TextAppearance.AppCompat.Large"
        android:textColor="#FF0000"
        android:textSize="20sp"
        android:textStyle="bold"
        tools:layout_editor_absoluteX="97dp"
        tools:layout_editor_absoluteY="175dp"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.671"/>
   <EditText
        android:id="@+id/editTextTextPersonName"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:textColor="#FF0000"
        android:hint="Name"
        android:textStyle="bold"
        android:textColorHint="#625D5D"
        app:layout_constraintBottom_toTopOf="@+id/button"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.21" />

    <EditText
        android:id="@+id/editTextTextPersonAge"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:textColor="#FF0000"
        android:hint="Age"
        android:textStyle="bold"
         android:textColorHint="#625D5D"
        app:layout_constraintBottom_toTopOf="@+id/button"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.41" />


    <EditText
        android:id="@+id/editTextTextPersonEmailID"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:textColor="#FF0000"
        android:hint="Email ID"
        android:textStyle="bold"
        android:textColorHint="#625D5D"
        app:layout_constraintBottom_toTopOf="@+id/button"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.605" />

      <EditText
        android:id="@+id/editTextTextPersonPhNo"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:textColor="#FF0000"
        android:hint="Phone Number"
        android:textStyle="bold"
        android:textColorHint="#625D5D"
        app:layout_constraintBottom_toTopOf="@+id/button"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.797" />

    <Button
        android:backgroundTint="#FD0000"
        android:textColor="@color/white"
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="SUBMIT"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.622" />
   </androidx.constraintlayout.widget.ConstraintLayout>



```



## ActivitySecond.xml

```

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity2"
    android:background="#FFFFFF">

    <TextView

        android:id="@+id/textViewName"
        android:layout_width="240dp"
        android:layout_height="wrap_content"
        android:fontFamily="sans-serif-black"
        android:text="TextView"
        android:textColor="#FF0000"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.894"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.194" />
  <TextView

        android:id="@+id/textViewAge"
        android:layout_width="240dp"
        android:layout_height="wrap_content"
        android:fontFamily="sans-serif-black"
        android:text="TextView"
        android:textColor="#FF0000"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.894"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.303" />

    <TextView

        android:id="@+id/textViewEmailID"
        android:layout_width="240dp"
        android:layout_height="wrap_content"
        android:fontFamily="sans-serif-black"
        android:text="TextView"
        android:textColor="#FF0000"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.894"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.407" />

    <TextView

        android:id="@+id/textViewPhNo"
        android:layout_width="240dp"
        android:layout_height="wrap_content"
        android:fontFamily="sans-serif-black"
        android:text="TextView"
        android:textColor="#FF0000"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.894"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.516" />

    <TextView
        android:id="@+id/textViewName2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:fontFamily="sans-serif-black"
        android:text="Name : "
        android:textAlignment="textEnd"
        android:textAllCaps="true"
        android:textColor="#272323"
        android:textSize="20sp"
        android:textStyle="italic"
        android:typeface="normal"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.091"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.193" />

     <TextView
        android:id="@+id/textViewAge2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:fontFamily="sans-serif-black"
        android:text="Age : "
        android:textAlignment="textEnd"
        android:textAllCaps="true"
        android:textColor="#272323"
        android:textSize="20sp"
        android:textStyle="italic"
        android:typeface="normal"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.086"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.301" />

    <TextView
        android:id="@+id/textViewEmailID2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:fontFamily="sans-serif-black"
        android:text="Email ID : "
        android:textAlignment="textEnd"
        android:textAllCaps="true"
        android:textColor="#272323"
        android:textSize="20sp"
        android:textStyle="italic"
        android:typeface="normal"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.099"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.404" />

    <TextView
        android:id="@+id/textViewPhNo2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:fontFamily="sans-serif-black"
        android:text="Ph.No : "
        android:textAlignment="textEnd"
        android:textAllCaps="true"
        android:textColor="#272323"
        android:textSize="20sp"
        android:textStyle="italic"
        android:typeface="normal"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.092"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.512" />
  </androidx.constraintlayout.widget.ConstraintLayout>



```

## AndroidManifest.xml

```

<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    package="com.example.workshop1">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:supportsRtl="true"
        android:theme="@style/Theme.WorkShop1"
        tools:targetApi="31">
        <activity android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
        <activity android:name=".SecondActivity" />
    </application>

</manifest>

```
 
## OUTPUT:


<img src="https://github.com/user-attachments/assets/cad62105-44ca-4241-83df-2ad548bfc5fb" width="600">

<img src="https://github.com/user-attachments/assets/e3c7b979-45d3-45ca-80a0-ee64af1d239d" width="400">

<img src="https://github.com/user-attachments/assets/6074f69f-3667-49d0-94f3-7aeb2398536c" width="400">

<img src="https://github.com/user-attachments/assets/96094be3-e622-4ef1-a50b-b31467342b97" width="400">

## RESULT:
Thus, The Developing an Android Application To Pass The Data Between The Activities Using Intent and is excecuted successfully and the output is verified. 
