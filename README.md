本项目演示在 android webview 中嵌入 LarkSR Web 客户端  

## 主要代码  

```java  
WebSettings webSettings = webView.getSettings();  
//允许运行JavaScript 
webSettings.setJavaScriptEnabled(true); 
//加载外网  
webView.loadUrl(url);             
webView.setWebViewClient(new HelloWebViewClient ());  

@Override
//Web视图  
private class HelloWebViewClient extends WebViewClient {  
    @Override  
    public boolean shouldOverrideUrlLoading(WebView view, String url) {  
        view.loadUrl(url);  
        return true;  
    }  
}  
@Override  
//设置回退  
public boolean onKeyDown(int keyCode, KeyEvent event) {  
    if ((keyCode == KeyEvent.KEYCODE_BACK) && webView.canGoBack()) {  
        webView.goBack(); //调用goBack()返回WebView的上一页面  
        return true;  
    }  
    return false;  
}  
```

## 注意事项

* 需要在配置单打开 `usesCleartextTraffic` 选项  
* 测试最低支持 Android 版本
* 不支持网页中调用全屏，需要在 Android 代码中设置

## 兼容测试

- [:heavy_check_mark:] 华为 Mate20X
- [:heavy_check_mark:] 小米6
- [:heavy_check_mark:] 华为 P30 
- [:heavy_check_mark:] 荣耀 V8
- [:heavy_check_mark:] 荣耀 V30
