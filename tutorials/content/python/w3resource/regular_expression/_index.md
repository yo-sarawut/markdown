+++
title = "Python: Regular Expression"
weight = 1
+++
> Reference : https://www.w3resource.com/python/python-regular-expression.php



A regular expression (or RE) specifies a set of strings that matches it; the functions in this module let you check if a particular string matches a given regular expression (or if a given regular expression matches a particular string, which comes down to the same thing).

**Contents:**

-   [Compare HTML tags](https://www.w3resource.com/python/python-regular-expression.php#re1)
-   [re.findall() match string](https://www.w3resource.com/python/python-regular-expression.php#re2)
-   [Group Comparison](https://www.w3resource.com/python/python-regular-expression.php#re3)
-   [Non capturing group](https://www.w3resource.com/python/python-regular-expression.php#re4)
-   [Back Reference](https://www.w3resource.com/python/python-regular-expression.php#re5)
-   [Named Grouping (?P<name>)](https://www.w3resource.com/python/python-regular-expression.php#re6)
-   [Substitute String](https://www.w3resource.com/python/python-regular-expression.php#re7)
-   [Look around](https://www.w3resource.com/python/python-regular-expression.php#re8)
-   [Match common username or password](https://www.w3resource.com/python/python-regular-expression.php#re9)
-   [Match hex color value](https://www.w3resource.com/python/python-regular-expression.php#re10)
-   [Match email](https://www.w3resource.com/python/python-regular-expression.php#re11)
-   [Match URL](https://www.w3resource.com/python/python-regular-expression.php#re12)
-   [Match IP address](https://www.w3resource.com/python/python-regular-expression.php#re13)
-   [Match Mac address](https://www.w3resource.com/python/python-regular-expression.php#re14)
-   [Lexer](https://www.w3resource.com/python/python-regular-expression.php#re15)
-   [Python Regular Expression - Exercises, Practice, Solution](https://www.w3resource.com/python-exercises/re/index.php)

The following table provides a list and description of the special pattern matching characters that can be used in regular expressions.



Matches only at the end of the string.

### **Compare HTML tags :**


| tag type |format |example |
|:----------:|:----------|:----------|
| open tag |<[^/>][^>]*> |`<a>, <table>` |
| close tag |</[^>]+> |`</p>, </a>` |
| self close |<[^/>]+/> |`<br />` |
| all tag |<[^>]+> |`<br />, <a>` |

```python
# open tag
>>> import re
>>> re.search('<[^/>][^>]*>', '<table>') != None
True
>>> import re
>>> re.search('<[^/>][^>]*>', '<a href="#label">') != None
True
>>> import re
>>> re.search('<[^/>][^>]*>', '<img src="/img">') != None
True
>>> import re
>>> re.search('<[^/>][^>]*>', '</table>') != None
False

# close tag
>>> import re
>>> re.search('</[^>]+>', '</table>') != None
True

# self close
>>> import re
>>> re.search('<[^/>]+/>', '<br />') != None
True

```



### **re.findall() match string :**

```python
# split all string
>>> import re
>>> source = "split all string"
>>> re.findall('[\w]+', source)
['split', 'all', 'string']

# parsing python.org website
>>> import urllib
>>> import re
>>> x = urllib.urlopen('https://www.w3resource.org')
>>> html = x.read()
>>> x.close()
>>> print("open tags")
open tags
>>> re.findall('<[^/>][^>]*>', html)[0:2]
['<!doctype html>', '<!-[if lt IE 7]>']
>>> print("close tags")
close tags
>>> re.findall('</[^>]+>', html)[0:2]
['</script>', '</title>']
>>> print("self-closing tags")
```



### **Group Comparison :**

```python
# (...) group a regular expression
>>> import re
>>> mon = re.search(r'(\d{4})-(\d{2})-(\d{2})', '2018-09-01')
>>> mon
<_sre.SRE_Match object at 0x019A72F0>
>>> mon.groups()
('2018', '09', '01')
>>> mon.group()
'2018-09-01')
>>> mon.group(1)
'2018'
>>> mon.group(2)
'09'
>>> mon.group(3)
'01'

# Nesting groups
>>> import re
>>> mon = re.search(r'(((\d{4})-\d{2})-\d{2})', '2018-09-01')
>>> mon.groups()
('2018-09-01', '2018-09', '2018')
>>> mon.group()
'2018-09-01'
>>> mon.group(1)
'2018-09-01'
>>> mon.group(2)
'2018-09'
>>> mon.group(3)
'2018'

```



### **Non capturing group :**

```python
# non capturing group
>>> import re
>>> url = 'http://w3resource.com/'
>>> mon = re.search('(?:http|ftp)://([^/\r\n]+)(/[^\r\n]*)?', url)
>>> mon.groups()
('w3resource.com', '/')

# capturing group
>>> import re
>>> mon = re.search('(http|ftp)://([^/\r\n]+)(/[^\r\n]*)?', url)
>>> mon.groups()
('http', 'w3resource.com', '/')
```



### **Back Reference :**

```python
# compare 'xx', 'yy'
>>> import re
>>> re.search(r'([a-z])\1$','xx') != None
True
>>> import re
>>> re.search(r'([a-z])\1$','yy') != None
True
>>> import re
>>> re.search(r'([a-z])\1$','xy') != None
False

# compare open tag and close tag
>>> import re
>>> pattern = r'<([^>]+)>[\s\S]*?</\1>'
>>> re.search(pattern, '<bold> test </bold>') != None
True
>>> re.search(pattern, '<h1> test </h1>') != None
True
>>> re.search(pattern, '<bold> test </h1>') != None
False
```



### **Named Grouping (?P<name>) :**

```python
# group reference ``(?P<name>...)``
>>> import re
>>> pattern = '(?P<year>\d{4})-(?P<month>\d{2})-(?P<day>\d{2})'
>>> mon = re.search(pattern, '2018-09-01')
>>> mon.group('year')
'2018'
>>> mon.group('month')
'09'
>>> mon.group('day')
'01'

# back reference ``(?P=name)``
>>> import re
>>> re.search('^(?P<char>[a-z])(?P=char)','aa')
<_sre.SRE_Match object at 0x01A08660>
```



### **Substitute String :**

```python
# basic substitute
>>> import re
>>> res = "4x5y6z"
>>> re.sub(r'[a-z]',' ', res)
'4 5 6 '

# substitute with group reference
>>> import re
>>> date = r'2018-09-01'
>>> re.sub(r'(\d{4})-(\d{2})-(\d{2})',r'\2/\3/\1/',date)
'09/01/2018/'

# camelcase to underscore
>>> def convert(s):
...     res = re.sub(r'(.)([A-Z][a-z]+)',r'\1_\2', s)
...     return re.sub(r'([a-z])([A-Z])',r'\1_\2', res).lower()
...
>>> convert('SentenceCase')
'sentence_case'
>>> convert('SentenceSentenceCase')
'sentence_sentence_case'
>>> convert('SampleExampleHTTPServer')
'sample_example_http_server'
```


### **Look around :**


| notation |compare direction |
|:----------:|:----------|
| (?<=...) |right to left |
| (?=...) |left to right |
| (?!<...) |right to left |
| (?!...) |left to right |

```python
# basic
>>> import re
>>> re.sub('(?=\d{3})', ' ', '56789')
' 5 6 789'
>>> re.sub('(?!\d{3})', ' ', '56789')
'567 8 9 '
>>> re.sub('(?<=\d{3})', ' ', '56789')
'567 8 9 '
>>> re.sub('(?<!\d{3})', ' ', '56789')
' 5 6 789'
```



### **Match common username or password :**

```python
>>> import re
>>> re.match('^[a-zA-Z0-9-_]{3,16}$', 'Foo') is not None
True
>>> re.match('^\w|[-_]{3,16}$', 'Foo') is not None
True
```


### **Match hex color value :**

```python
>>> import re
>>> re.match('^#?([a-f0-9]{6}|[a-f0-9]{3})$', '#ff0000')
<_sre.SRE_Match object at 0x019E7720>
>>> re.match('^#?([a-f0-9]{6}|[a-f0-9]{3})$', '#000000')
<_sre.SRE_Match object at 0x019E77A0>

```


### **Match email :**

```python
>>> import re
>>> re.match('^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$',
	 'citi.world@example.com')
<_sre.SRE_Match object; span=(0, 22), match='citi.world@example.com'>

# or

>>> import re
>>> example = re.compile(r'''^([a-zA-Z0-9._%-]+@
[a-zA-Z0-9.-]+
\.[a-zA-Z]{2,4})*$''', re.X)
>>> example.match('citi.world@example.citi.com')
<_sre.SRE_Match object; span=(0, 27), match='citi.world@example.citi.com'>
>>> example.match('citi%world@example.citi.com')
<_sre.SRE_Match object; span=(0, 27), match='citi%world@example.citi.com'>

```


### **Match URL :**

```python
>>> import re
>>> example = re.compile(r'''^(https?:\/\/)? # match http or https
...             ([\da-z\.-]+)            # match domain
...             \.([a-z\.]{2,6})         # match domain
...             ([\/\w \.-]*)\/?$        # match api or file
...             ''', re.X)
>>> example.match('www.yahoo.com')
<_sre.SRE_Match object; span=(0, 13), match='www.yahoo.com'>
>>> example.match('http://www.example')
<_sre.SRE_Match object; span=(0, 18), match='http://www.example'>
>>> example.match('http://www.example/w3r.html')
<_sre.SRE_Match object; span=(0, 27), match='http://www.example/w3r.html'>
>>> example.match('http://www.example/w3r!.html')
>>> example
re.compile('^(https?:\\/\\/)?\n([\\da-z\\.-]+)\n\\.([a-z\\.]{2,6})\n([\\/\\w \\.-]*)\\/?$\n', re.VERBOSE)

```


### **Match IP address :**


| notation |description |
|:----------|:----------|
| [1]?[0-9][0-9] |Match 0-199 pattern |
| 2[0-4][0-9] |Match 200-249 pattern |
| 25[0-5] |Match 251-255 pattern |
| (?:...) |Don't capture group |

```python
>>> import re
>>> example = re.compile(r'''^(?:(?:25[0-5]
... |2[0-4][0-9]
... |[1]?[0-9][0-9]?)\.){3}
... (?:25[0-5]
... |2[0-4][0-9]
... |[1]?[0-9][0-9]?)$''', re.X)
>>> example.match('192.168.1.1')
<_sre.SRE_Match object at 0x0134A608>
>>> example.match('255.255.255.0')
<_sre.SRE_Match object at 0x01938678>
>>> example.match('172.17.0.5')
<_sre.SRE_Match object at 0x0134A608>
>>> example.match('256.0.0.0') is None
True
```



### **Match Mac address :**

```python
>>> import random
>>> mac = [random.randint(0x00, 0x6b),
... random.randint(0x00, 0x6b),
... random.randint(0x00, 0x6b),
... random.randint(0x00, 0x6b),
... random.randint(0x00, 0x6b),
... random.randint(0x00, 0x6b)]
>>> mac = ':'.join(map(lambda x: "%02x" % x, mac))
>>> mac
'05:38:64:60:55:63'
>>> import re
>>> example = re.compile(r'''[0-9a-f]{2}([:])
... [0-9a-f]{2}
... (\1[0-9a-f]{2}){4}$''', re.X)
>>> example.match(mac) is not None
True

```


### **Lexer :**

```python
>>> import re
>>> from collections import namedtuple
>>> tokens = [r'(?P<NUMBER>\d+)',
	  r'(?P<PLUS>\+)',
	  r'(?P<MINUS>-)',
	  r'(?P<TIMES>\*)',
	  r'(?P<DIVIDE>/)',
	  r'(?P<WS>\s+)']
>>> lex = re.compile('|'.join(tokens))
>>> Token = namedtuple('Token', ['type', 'value'])
>>> def tokenize(text):
	scan = lex.scanner(text)
	return (Token(m.lastgroup, m.group())
		for m in iter(scan.match, None) if m.lastgroup != 'WS')

>>> for _t in tokenize('9 + 5 * 2 - 7'):
	print(_t)

	
Token(type='NUMBER', value='9')
Token(type='PLUS', value='+')
Token(type='NUMBER', value='5')
Token(type='TIMES', value='*')
Token(type='NUMBER', value='2')
Token(type='MINUS', value='-')
Token(type='NUMBER', value='7')
>>> tokens
# ['(?P<NUMBER>\\d+)', '(?P<PLUS>\\+)', '(?P<MINUS>-)', '(?P<TIMES>\\*)', '(?P<DIVIDE>/)', '(?P<WS>\\s+)']

```


