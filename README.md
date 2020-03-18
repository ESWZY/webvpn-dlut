# webvpn-dlut

```webvpn.dlut.edu.cn```是DUT的WebVPN，提供了从校外访问校园网环境资源的接口，可供访问校内资源。

但是登录后，由于链接为加密状态，仅能访问该系统门户所提供的站点。

正巧最近的课程涉及到该链接编制方式，用Python实现加密链接与普通链接的转换方式。

经查，该系统为```网瑞达科技```的资源访问控制系统（WebVPN），并使用了```wrdvpnisthebest!```作为key和iv。

可能所有使用该系统的WebVPN都可使用同种方式实现链接转换，可供一试。

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
```pip install pycryptodome```

并直接运行“webvpn.py” 可以得到“xueshu.baidu.com”的密文、“e7e056d2253161546b468aa395”对应的明文、一个知网论文网页的webvpn网址和一个webvpn网址对应的原先的网址。

