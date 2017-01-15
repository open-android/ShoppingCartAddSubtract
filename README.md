
# Android-ShoppingCartAddSubtract
一种漂亮的UI控件，能更灵活的控制数字的增减。

项目地址:[https://github.com/open-android/ShoppingCartAddSubtract](https://github.com/open-android/ShoppingCartAddSubtract "购物车加减控件")


简书：[http://www.jianshu.com/p/be3d0f763c5a](http://www.jianshu.com/p/be3d0f763c5a "购物车加减控件")
# 运行效果
 
  ![]( http://upload-images.jianshu.io/upload_images/4037105-ad779cfe6a715668.gif?imageMogr2/auto-orient/strip)

## 使用步骤
### 1. 在project的build.gradle添加如下代码(如下图)

	allprojects {
	    repositories {
	        ...
	        maven { url "https://jitpack.io" }
	    }
	}

![](http://oi5nqn6ce.bkt.clouddn.com/itheima/booster/code/jitpack.png)

### 2. 在Module的build.gradle添加依赖

     compile 'com.github.open-android:ShoppingCartAddSubtract:0.1.0'


### 3. 在XML添加如下代码

    <LinearLayout
        android:padding="15dp"
        android:gravity="center_vertical"
        android:orientation="horizontal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <com.bigkoo.snappingstepper.SnappingStepper
            android:id="@+id/stepper"
            android:layout_width="120dp"
            android:layout_height="30dp"/>

        <TextView
            android:id="@+id/tvValue"
            android:layout_marginLeft="30dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content" />
    </LinearLayout>

### 4. 在java类中添加如下代码

    tvValue = (TextView) findViewById(R.id.tvValue);
    stepper = (SnappingStepper) findViewById(R.id.stepper);
    tvValue.setText(String.valueOf(stepper.getValue()));
    stepper.setOnValueChangeListener(this);
    @Override
    public void onValueChange(View view ,int value) {
        switch (view.getId()){
            case R.id.stepper:
                tvValue.setText(String.valueOf(value));
                break;
        }
    }





   
---

* 注意细节

> 支持更多的自定义属性XML表示

    <com.bigkoo.snappingstepper.SnappingStepper
	  android:id="@+id/stepperCustom2"
	  stepper:max="200"
	  stepper:min="50"
	  stepper:step="5"
	  stepper:value="100"
	  android:layout_width="150dp"
	  android:layout_height="40dp"
	  stepper:stepper_background="@color/colorStepperButtonNormal"
	  stepper:stepper_leftButtonBackground="@drawable/sl_steppercustom_button_bg"
	  stepper:stepper_rightButtonBackground="@drawable/sl_steppercustom_button_bg"
	  stepper:stepper_contentBackground="@color/colorStepperContentBg"
	  stepper:stepper_contentTextColor="#0099ff"
	  stepper:stepper_contentTextSize="18"
	  stepper:stepper_leftButtonResources="@drawable/ic_stepper_left"
	  stepper:stepper_rightButtonResources="@drawable/ic_stepper_right"
      />

> 支持更多的自定义属性java代码表示

    stepperCustom.setBackgroundColor(getResources().getColor(R.color.colorStepperButtonNormal));
    stepperCustom.setButtonBackGround(R.drawable.sl_steppercustom_button_bg);
    stepperCustom.setContentBackground(R.color.colorStepperContentBg);
    stepperCustom.setContentTextColor(R.color.colorStepperText);
    stepperCustom.setContentTextSize(18);
    stepperCustom.setLeftButtonResources(R.drawable.ic_stepper_left);
    stepperCustom.setRightButtonResources(R.drawable.ic_stepper_right);



欢迎关注微信公众号

![](http://oi5nqn6ce.bkt.clouddn.com/itheima/booster/code/qrcode.png)
