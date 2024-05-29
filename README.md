# cal_app
package com.example.app1

import android.os.Bundle
import android.view.View
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AppCompatActivity
import androidx.core.view.ViewCompat
import androidx.core.view.WindowInsetsCompat

class MainActivity : AppCompatActivity() , View.OnClickListener {
    lateinit var btnAdd :Button
    lateinit var btnsub :Button
    lateinit var btnmultiply :Button
    lateinit var btndivide :Button
    lateinit var etA : EditText
    lateinit var etB : EditText
    lateinit var resultTv :  TextView
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
btnAdd=findViewById(R.id.btn_add)
        btnsub=findViewById(R.id.btn_subtraction)
        btnmultiply=findViewById(R.id.btn_multiplication)
        btndivide=findViewById(R.id.btn_division)
        etA=findViewById(R.id.et_a)
        etB=findViewById(R.id.et_b)
        resultTv=findViewById(R.id.result_tv)
        btnAdd.setOnClickListener(this)
        btnsub.setOnClickListener(this)
        btnmultiply.setOnClickListener(this)
        btndivide.setOnClickListener(this)

    }

    override fun onClick(v: View?) {
        var a = etA.text.toString().toDouble()
        var b = etB.text.toString().toDouble()
        var result=0.0
        when(v?.id){
            R.id.btn_add -> {
                result=a+b
            }
            R.id.btn_subtraction -> {
                result=a-b
            }
            R.id.btn_multiplication -> {
                result=a*b
            }
            R.id.btn_division -> {
                result=a/b
            }
        }
        resultTv.text="result is $result"
    }
}
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:layout_margin="20px"
    tools:context=".MainActivity">

    <EditText
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/et_a"
        android:layout_margin="20dp"
        android:hint="Enter a "/>

    <EditText
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/et_b"
        android:layout_margin="20dp"
        android:hint="Enter b "/>

<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="horizontal">

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/btn_add"
        android:layout_margin="4dp"
        android:text="+"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/btn_subtraction"
        android:layout_margin="4dp"
        android:text="-"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/btn_multiplication"
        android:layout_margin="4dp"
        android:text="*"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/btn_division"
        android:layout_margin="4dp"
        android:text="/"/>


</LinearLayout>

<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="Result "
    android:textSize="24sp"
    android:layout_margin="20dp"
    android:id="@+id/result_tv"
    android:gravity="center"/>

    </LinearLayout>
