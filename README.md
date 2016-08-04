# CropUtils
对ucrop的封装工具类,让其使用更加快捷



[uCrop主项目地址](https://github.com/Yalantis/uCrop)





# 封装的api

``` 
public static void pickFromGallery(Activity context)//

public static void pickFromCamera(Activity context)

public static void pickAvatarFromGallery(Activity context)//从图库中选头像

public static void pickAvatarFromCamera(Activity context)

public static void pickFromGallery(Activity context,CropConfig config,int type)
//需要自定义设置时使用

public static void handleResult(Activity context, CropHandler cropHandler, int requestCode, int resultCode, Intent data)

public interface CropHandler {
        void handleCropResult(Uri uri,int tag);
        void handleCropError(Intent data);
    }
```



# 使用

点击选择图片或拍照的地方调用pickxxx



实现CropHandler接口



在activity的onActivityResult里调用CropUtils.handleResult(this,cropHandler,requestCode,resultCode,data);.注意无需预先对intent做为空的判断.



tag字段用于同一个页面多个地方接收裁剪图片的区分,如无需要,不必设置.

