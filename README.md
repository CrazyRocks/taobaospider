# 1. ���л���
1. python 2.7 
2. Scrapy 1.4.0

## 1.2 ���������

#### 1. ȷ������python������

```python

$python
Python 2.7.12 (v2.7.12:d33e0cf91556, Jun 27 2016, 15:24:40) [MSC v.1500 64 bit (AMD64)] on win32
>>>

```

#### 2. ��װpip

��������������Ҳ����

windows:���https://pypi.python.org/pypi/pip ����pip-x.y.z.tar.gz (md5, pgp)

��ѹ������ļ���ִ�У�`python setup.py install`

����ֱ������exe�ļ����а�װ�����ص�ַΪ��http://www.lfd.uci.edu/~gohlke/pythonlibs/#pip

#### 3.��װlxml

lxml��һ��ʹ�� Python ��д�Ŀ⣬����Ѹ�١����ش��� XML��ѡ���Ӧ��Python�汾��װ��

��װ���`pip install lxml`

��֤�Ƿ�װ�ɹ���`>>>import lxml`

#### 4.��װzope.interface����װ���
`pip install zope.interface`
 
#### 5.��װTwisted

Twisted����Pythonʵ�ֵĻ����¼����������������ܣ���װ��� 

`pip install twisted` 

#### 6.��װpyOpenSSL

pyOpenSSL��Python��OpenSSL�ӿڣ���װ���

`pip install pyopenssl`

#### 7.��װwin32py ��windows��Ҫ��

�ṩwin32api����� http://sourceforge.net/projects/pywin32/files/pywin32/ ����

#### 8.��װScrapy

`pip install scrapy`

����scrapy���뻷������

#### 9.�����Ƿ�scrapy����:

`scrapy bench`

��װ���

---

# 2. ����Ŀ������

####  ���ػ��¡����Ŀ������Ŀ¼

Ŀ¼�ṹ(��Ҫ)��

```
taobaospider(or your folder)
	|
	|-scrapy.cfg
	|-.settings
	|-result
	|-taobaospider
		   |
		   |-__init__.py
		   |-items.py
		   |-middlewares.py
		   |-pipelines.py
		   |-settings.py
		   |-spiders
		       |
		       |-__init__.py
		       |-taobao.py
		       |-taobaodata.py
		       

```

## 2.1 ��Ŀ1����ȡ�Ա���ҳ��Ʒ����

#### 1. �޸�pipelines.py

```python
...
class TaobaospiderPipeline(object):
    def __init__(self):
        self.file = codecs.open('class.json', 'wb', encoding='utf-8')
...
```

#### 2. ����

��`.setting`ͬ��Ŀ¼�����У�

`scrapy crawl taobao`

#### 3. �����

����`class.json`�ļ����������£�

```
{"class2": ["���޷�Ů", "ë������Ů", "ë��Ů", "��֯��Ů", "�޷�Ů", "����ȹ",  "����Ůװ", "����Ůװ", "����Ůװ", "T��Ůװ", "����Ůװ", "����ȹ", "��װŮ", "�����Ů", "�п�Ů", "Ƥ��Ů", "����װ","��ɴ���"], "class1": "Ůװ"}
{"class2": ["������װ", "�п���װ", "������װ", "T����װ", "�������װ", "ţ��������װ", "������װ", "��װ��", "������װ", "Ƥ����װ", "��֯����װ", "�ش�����װ", "���п���װ", "ţ�п���װ", "�˶�����װ", "�ŷֿ���װ", "�����װ", "���޷���װ", "������", "��������װ"], "class1": "��װ"}
{"class2": ["��ů����", "˿��˯��", "�ڿ�Ů", "����", "�ڿ���", "����˯��", "ɺ����˯��", "����˯��", "��Ͳ��", "����", "����˯��", "���", "��ů����", "˯��", "��ʿ˯��", "������", "������װ", "��׿�", "����˯��", "˯ȹŮ��", "��£����", "��ʿ����", "����Ů", "��ͨ˯��"], "class1": "����"}
...
```
