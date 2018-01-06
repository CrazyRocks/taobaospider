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

(�򿪶�Ӧ��ע�͹ر�ͬ������ע�ͼ���)

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

(˵�������е���`taobao.py`�ļ�)

#### 3. �����

����`class.json`�ļ����������£�

```json
{"class2": ["���޷�Ů", "ë������Ů", "ë��Ů", "��֯��Ů", "�޷�Ů", "����ȹ",  "����Ůװ", "����Ůװ", "����Ůװ", "T��Ůװ", "����Ůװ", "����ȹ", "��װŮ", "�����Ů", "�п�Ů", "Ƥ��Ů", "����װ","��ɴ���"], "class1": "Ůװ"}
{"class2": ["������װ", "�п���װ", "������װ", "T����װ", "�������װ", "ţ��������װ", "������װ", "��װ��", "������װ", "Ƥ����װ", "��֯����װ", "�ش�����װ", "���п���װ", "ţ�п���װ", "�˶�����װ", "�ŷֿ���װ", "�����װ", "���޷���װ", "������", "��������װ"], "class1": "��װ"}
{"class2": ["��ů����", "˿��˯��", "�ڿ�Ů", "����", "�ڿ���", "����˯��", "ɺ����˯��", "����˯��", "��Ͳ��", "����", "����˯��", "���", "��ů����", "˯��", "��ʿ˯��", "������", "������װ", "��׿�", "����˯��", "˯ȹŮ��", "��£����", "��ʿ����", "����Ů", "��ͨ˯��"], "class1": "����"}
...
```

## 2.2 ��Ŀ2����ȡ���������µ���Ʒ

#### 1. �޸�pipelines.py

(�򿪶�Ӧ��ע�͹ر�ͬ������ע�ͼ���)

```python
class TaobaospiderPipeline(object):
    def __init__(self):
        #self.file = codecs.open('class.json', 'wb', encoding='utf-8')
        self.file = codecs.open('yourname.json', 'wb', encoding='utf-8')
```

#### 2. ����

��`.setting`ͬ��Ŀ¼�����У�

`scrapy crawl taobaodata`

(˵�������е���`taobaodata.py`�ļ�)

#### 3. �����

�����н��濴��������Ϣ��

```
...
{'class1': '\xe5\xa5\xb3\xe8\xa3\x85',
 'class2': '\xe6\xaf\x9b\xe8\xa1\xa3\xe5\xa5\xb3',
 'price': u'89.00',
 'sales': 13000.0,
 'store': u'<',
 'title': u'\u534a\u9ad8\u9886\u52a0\u539a\u751c\u7f8e\u6253\u5e95\u5957\u5934\u
97e9\u7248\u5bbd\u677e\u6bdb\u8863'}
...
```
����`yourname.json`�ļ����������£�

```json
{"title": "�ﶬ���������������ݼӺ���֯��", "price": "49.00", "sales": 5557.0, "class2": "ë��Ů", "store": "<", "class1": "Ůװ"}
{"title": "�ﶬ���ɰ������ͷѧ������Ӻ�ë��", "price": "88.00", "sales": 8771.0, "class2": "ë��Ů", "store": "", "class1": "Ůװ"}
...
```

####  ����˵��

����Ŀ�ı������Ѿ�ȫ��������result�ļ�����

---
