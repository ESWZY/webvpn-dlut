# webvpn-dlut

```webvpn.dlut.edu.cn```��DUT��WebVPN���ṩ�˴�У�����У԰��������Դ�Ľӿڣ��ɹ�����У����Դ��

���ǵ�¼����������Ϊ����״̬�����ܷ��ʸ�ϵͳ�Ż����ṩ��վ�㡣

��������Ŀγ��漰�������ӱ��Ʒ�ʽ����Pythonʵ�ּ�����������ͨ���ӵ�ת����ʽ��

���飬��ϵͳΪ[�����Ƽ�](https://www.wrdtech.com/content/content.php?p=2_30_203)����Դ���ʿ���ϵͳ��WebVPN������ʹ����```wrdvpnisthebest!```��Ϊkey��iv��

���ܷ�����*AES-128-CFB*

# ����ṹ
Դ����ΪPython�ļ�����webvpn.py��

�����Ϊ�ĸ�������

```python
        getCiphertext(plaintext, key = key_, cfb_iv = iv_, size = 128) #����������������
        getPlaintext(ciphertext, key = key_, cfb_iv = iv_, size = 128) #�������ĵõ�����
        getVPNUrl(url)        #����ͨ��urlת����webvpn��url
        getOrdinaryUrl(url)   #��webvpn��url���ƻ���ͨ��url
```

# ���з�ʽ

���ȱ�����Python�⣬��������ִ��
```pip install -r requirements.txt```

��ֱ������ ```python webvpn.py``` 

���Եõ�һ��֪��������ҳ��webvpn��ַ��һ��webvpn��ַ��Ӧ��ԭ�ȵ���ַ��

# ������

��������˵������Ӧ�õ�����ʹ�ø�ϵͳ��WebVPN�ϡ��ڴ��ṩһ����ֲ��˼·��

��

```python
institution = 'webvpn.dlut.edu.cn'
```

��Ϊ

```python
institution = 'webvpn.xxx.edu.cn'
```

�����л�ΪXXX��WebVPN��GL