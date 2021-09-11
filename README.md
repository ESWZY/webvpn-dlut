# webvpn-dlut

```webvpn.dlut.edu.cn```是DUT的WebVPN，提供了从校外访问校园网环境资源的接口，可供访问校内资源。

但是登录后，由于链接为加密状态，仅能访问该系统门户所提供的站点。

正巧最近的课程涉及到该链接编制方式，用Python实现加密链接与普通链接的转换方式。

经查，该系统为[网瑞达科技](https://www.wrdtech.com/content/content.php?p=2_30_203)的资源访问控制系统（WebVPN），并使用了```wrdvpnisthebest!```作为key和iv。

加密方法：*AES-128-CFB*

# 代码结构
源代码为Python文件：“webvpn.py”

代码分为四个函数：

```python
        getCiphertext(plaintext, key = key_, cfb_iv = iv_, size = 128) #利用明文生成密文
        getPlaintext(ciphertext, key = key_, cfb_iv = iv_, size = 128) #利用密文得到明文
        getVPNUrl(url)        #从普通的url转换成webvpn的url
        getOrdinaryUrl(url)   #从webvpn的url反推回普通的url
```

# 运行方式

如果缺少相关Python库，在命令行执行
```pip install -r requirements.txt```

并直接运行 ```python webvpn.py``` 

可以得到一个知网论文网页的webvpn网址和一个webvpn网址对应的原先的网址。

# 适用性

理论上来说，可以应用到所有使用该系统的WebVPN上。在此提供一种移植的思路：

将

```python
institution = 'webvpn.dlut.edu.cn'
```

改为

```python
institution = 'webvpn.xxx.edu.cn'
```

即可切换为XXX的WebVPN。GL

# 参见

[webvpn4dut](https://github.com/cjhahaha/webvpn4dut)：JavaScript「实现」的WebVPN链接转换。

[dlut-survival-tools](https://github.com/BeautyYuYanli/dlut-survival-tools)：与大连理工大学相关的工具收集。
