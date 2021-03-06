
`WeChatSDK`其他语言接口文档。

## Python

发布`Python`版本的接口，具体使用见`src/WeChatSDKPy/sdk.py`。

```
//需管理员运行python
wxsdk = WXSDK()
print(wxsdk.WXOpenWechat())
input("wait for...")
print(wxsdk.WXIsWechatAlive())
print(wxsdk.WXIsWechatSDKOk())
print(wxsdk.WXInitialize())
input("wait for...")
print(wxsdk.WXSendTextMsg("wxid_n11111", "This is a python sdk test msg"))
```

## Java

发布`Java`版本的接口，具体使用见`src/WeChatSDKJava/WeChatSDK.java`和`TestJavaSDK.java`。

由于`Java`接口使用了`jna`，所以需要下载[jna.jar](http://repo1.maven.org/maven2/net/java/dev/jna/jna/5.2.0/jna-5.2.0.jar)，具体编译方法请查找`Java`相关文章。

```
//需管理员运行java
public class TestJavaSDK {
    public static void main(String[] argv) throws Exception {
        System.out.println("hello java WechatSDK");

        int pid = WeChatSDK.sdk.WXOpenWechat();
        if(pid <= 0) {
            System.out.println("hello java WechatSDK");
            return;
        }

        System.out.println("pid: " + pid);

        System.out.println("wait for...");
        System.in.read();

        System.out.println(WeChatSDK.sdk.WXIsWechatAlive(pid));
        System.out.println(WeChatSDK.sdk.WXIsWechatSDKOk(pid));
        System.out.println(WeChatSDK.sdk.WXInitialize(pid));
        System.out.println("wait for...");
        System.in.read();
        System.out.println(WeChatSDK.sdk.WXSendTextMsg(pid, new WString("wxid_11111"), new WString("This is a java sdk test msg")));
        System.in.read();
    }
}
```

