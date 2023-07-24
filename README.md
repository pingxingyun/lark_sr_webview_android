Demo show android webview open LarkSR Web client

## Code

```java  
WebSettings webSettings = webView.getSettings();  
//enable JavaScript 
webSettings.setJavaScriptEnabled(true); 
//load url  
webView.loadUrl(url);             
webView.setWebViewClient(new HelloWebViewClient ());  

@Override
private class HelloWebViewClient extends WebViewClient {  
    @Override  
    public boolean shouldOverrideUrlLoading(WebView view, String url) {  
        view.loadUrl(url);  
        return true;  
    }  
}  
@Override  
public boolean onKeyDown(int keyCode, KeyEvent event) {  
    if ((keyCode == KeyEvent.KEYCODE_BACK) && webView.canGoBack()) {  
        webView.goBack();
        return true;  
    }  
    return false;  
}  
```

## notice

* http should open `usesCleartextTraffic`
* fullscreen should set in android code.

## 兼容测试

- [:heavy_check_mark:] huawei Mate20X
- [:heavy_check_mark:] xiaomi 6
- [:heavy_check_mark:] huawei P30 
- [:heavy_check_mark:] honor V8
- [:heavy_check_mark:] honor V30
