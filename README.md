# webvpn-dlut

`webvpn.dlut.edu.cn`是 DUT 的 WebVPN，提供了从校外访问校园网环境资源的接口，可供访问校内资源。

但是登录后，由于链接为加密状态，仅能访问该系统门户所提供的站点。

正巧最近的课程涉及到该链接编制方式，用 Python 实现加密链接与普通链接的转换方式。

经查，该系统为[网瑞达科技](https://www.wrdtech.com/content/content.php?p=2_30_203)的资源访问控制系统（WebVPN），并使用了`Wxzxvpn2023key@$`（原为`wrdvpnisthebest!`）作为 key 和 iv。

加密方法：*AES-128-CFB*

## 部署

安装依赖库：

```bash
pip install -r requirements.txt
```

## 使用

通过`--encode`（可简写为`-e`）参数将普通网址转换为通过 WebVPN 访问的网址：

```bash
python webvpn.py --encode <url>
```

通过`--decode`（可简写为`-d`）参数将通过 WebVPN 访问的网址转换为普通网址：

```bash
python webvpn.py --decode <url>
```

可选参数：
- `--key`：指定加解密的 key。
- `--iv`：指定加解密的 iv。
- `--institution`（可简写为`-i`）：指定 WebVPN 系统的域名（仅`encode`模式生效，默认即`webvpn.dlut.edu.cn`）。

## 代码结构

源代码为 Python 文件：`webvpn.py`

代码分为四个函数：

```python
getCiphertext(plaintext, key, cfb_iv, size = 128)       # 利用明文生成密文
getPlaintext(ciphertext, key, cfb_iv, size = 128)       # 利用密文得到明文
getVPNUrl(url)          # 将普通网址转换为通过 WebVPN 访问的网址
getOrdinaryUrl(url)     # 将通过 WebVPN 访问的网址转换为普通网址
```

## 参见

[webvpn4dut](https://github.com/cjhahaha/webvpn4dut)：JavaScript「实现」的 WebVPN 链接转换。

[dlut-survival-tools](https://github.com/BeautyYuYanli/dlut-survival-tools)：与大连理工大学相关的工具收集。
