## WKWebView API
#### WKWebView有14个类：
- WKBackForwardList: 之前访问过的 web 页面的列表，可以通过后退和前进动作来访问到。
- WKBackForwardListItem: webview 中后退列表里的某一个网页。
- WKFrameInfo: 包含一个网页的布局信息。
- WKNavigation: 包含一个网页的加载进度信息。
- WKNavigationAction: 包含可能让网页导航变化的信息，用于判断是否做出导航变化。
- WKNavigationResponse: 包含可能让网页导航变化的返回内容信息，用于判断是否做出导航变化。
- WKPreferences: 概括一个 webview 的偏好设置。
- WKProcessPool: 表示一个 web 内容加载池。
- WKUserContentController: 提供使用 JavaScript post 信息和注射 script 的方法。
- WKScriptMessage: 包含网页发出的信息。
- WKUserScript: 表示可以被网页接受的用户脚本。
- WKWebViewConfiguration: 初始化 webview 的设置。
- WKWindowFeatures: 指定加载新网页时的窗口属性。
- WKWebsiteDataStore: 包含网页数据存储和查找。
- WKNavigationDelegate: 提供了追踪主窗口网页加载过程和判断主窗口和子窗口是否进行页面加载新页面的相关方法。
- WKUIDelegate: 提供用原生控件显示网页的方法回调。
- WKScriptMessageHandler: 提供从网页中收消息的回调方法。

#### WKWebView
- WKNavigationDelegate：该代理提供的方法，可以用来追踪加载过程（页面开始加载、加载完成、加载失败）、决定是否执行跳转。
- WKUIDelegate：创建一个新的WKWebView
- WKScriptMessageHandler：这个协议中包含一个必须实现的方法，这个方法是native与web端交互的关键，它可以直接将接收到的JS脚本转为OC或Swift对象。

#### WKWindowFeatures
```objective-c
/*! @abstract BOOL. Whether the menu bar should be visible. nil if menu bar visibility was not specified.
*/
@property (nullable, nonatomic, readonly) NSNumber *menuBarVisibility;

/*! @abstract BOOL. Whether the status bar should be visible. nil if status bar visibility was not specified.
*/
@property (nullable, nonatomic, readonly) NSNumber *statusBarVisibility;

/*! @abstract BOOL. Whether toolbars should be visible. nil if toolbar visibility was not specified.
*/
@property (nullable, nonatomic, readonly) NSNumber *toolbarsVisibility;

/*! @abstract BOOL. Whether the containing window should be resizable. nil if resizability was not specified.
*/
@property (nullable, nonatomic, readonly) NSNumber *allowsResizing;

/*! @abstract CGFloat. The x coordinate of the containing window. nil if the x coordinate was not specified.
*/
@property (nullable, nonatomic, readonly) NSNumber *x;

/*! @abstract CGFloat. The y coordinate of the containing window. nil if the y coordinate was not specified.
*/
@property (nullable, nonatomic, readonly) NSNumber *y;

/*! @abstract CGFloat. The width coordinate of the containing window. nil if the width was not specified.
*/
@property (nullable, nonatomic, readonly) NSNumber *width;

/*! @abstract CGFloat. The height coordinate of the containing window. nil if the height was not specified.
*/
@property (nullable, nonatomic, readonly) NSNumber *height;

作者：李潇南
链接：https://www.jianshu.com/p/29b992b5d6af
來源：简书
简书著作权归作者所有，任何形式的转载都请联系作者获得授权并注明出处。
```

#### WKNavigationDelegate
```objective-c
// 页面开始加载时调用
- (void)webView:(WKWebView *)webView didStartProvisionalNavigation:(WKNavigation *)navigation;

// 当内容开始返回时调用
- (void)webView:(WKWebView *)webView didCommitNavigation:(WKNavigation *)navigation;

// 页面加载完成之后调用
- (void)webView:(WKWebView *)webView didFinishNavigation:(WKNavigation *)navigation;

// 页面加载失败时调用
- (void)webView:(WKWebView *)webView didFailProvisionalNavigation:(WKNavigation *)navigation;

页面跳转的代理方法有三种，分为（收到跳转与决定是否跳转两种）

// 接收到服务器跳转请求之后调用
- (void)webView:(WKWebView *)webView didReceiveServerRedirectForProvisionalNavigation:(WKNavigation *)navigation;

// 在收到响应后，决定是否跳转
- (void)webView:(WKWebView *)webView decidePolicyForNavigationResponse:(WKNavigationResponse *)navigationResponse decisionHandler:(void (^)(WKNavigationResponsePolicy))decisionHandler;

// 在发送请求之前，决定是否跳转
- (void)webView:(WKWebView *)webView decidePolicyForNavigationAction:(WKNavigationAction *)navigationAction decisionHandler:(void (^)(WKNavigationActionPolicy))decisionHandler;
```

#### WKUIDelegate
```objective-c
- (WKWebView *)webView:(WKWebView *)webView createWebViewWithConfiguration:(WKWebViewConfiguration *)configuration forNavigationAction:(WKNavigationAction *)navigationAction windowFeatures:(WKWindowFeatures *)windowFeatures;

// 界面弹出警告框
- (void)webView:(WKWebView *)webView runJavaScriptAlertPanelWithMessage:(NSString *)message initiatedByFrame:(void (^)())completionHandler;

// 界面弹出确认框
- (void)webView:(WKWebView *)webView runJavaScriptConfirmPanelWithMessage:(NSString *)message initiatedByFrame:(WKFrameInfo *)frame completionHandler:(void (^)(BOOL result))completionHandler;

// 界面弹出输入框
- (void)webView:(WKWebView *)webView runJavaScriptTextInputPanelWithPrompt:(NSString *)prompt defaultText:(nullable NSString *)defaultText initiatedByFrame:(WKFrameInfo *)frame completionHandler:(void (^)(NSString * __nullable result))completionHandler;
```

#### WKScriptMessageHandler
```objective-c
// 从web界面中接收到一个脚本时调用
- (void)userContentController:(WKUserContentController *)userContentController didReceiveScriptMessage:(WKScriptMessage *)message;
```






---

[<返回目录](https://weadar.github.io/index)
