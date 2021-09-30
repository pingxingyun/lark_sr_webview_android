# lark_sr_webview_android
本项目演示在 android webview 中嵌入 LarkSR Web 客户端

#主要代码
WebSettings webSettings = webView.getSettings();
 webSettings.setJavaScriptEnabled(true);//允许运行JavaScript
webView.loadUrl(url);             //加载外网
webView.setWebViewClient(new HelloWebViewClient ());
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
    
   需要在配置单打开 usesCleartextTraffic 选项
   版本min22 target30
   测试机型华为Mate20X 小米6通过
   暂不支持全屏，需手动设置
