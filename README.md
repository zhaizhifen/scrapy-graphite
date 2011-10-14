Description
===========
Output scrapy statistics to carbon/graphite

<img src="http://github.com/noplay/scrapy-graphite/blob/master/img/folder.png?raw=true"/>

Install
=======
   pip install "ScrapyGraphite"

Configure your settings.py:
----------------------------

```python
    STATS_CLASS = 'scrapygraphite.GraphiteStatsCollector'
    GRAPHITE_HOST = "localhost"
    GRAPHITE_PORT = 2003
```


Configure graphite:
-------------------

In graphite you need to add in your storage-aggregation.conf:

```ini
[scrapy_min]
pattern = ^scrapy\..*\.min$
xFilesFactor = 0.1
aggregationMethod = min

[scrapy_max]
pattern = ^scrapy\..*\.max$
xFilesFactor = 0.1
aggregationMethod = max

[scrapy_sum]
pattern = ^scrapy\..*\.sum$
xFilesFactor = 0.1
aggregationMethod = sum
```

And in aggregation-rules.conf  (look in storage-schemas.conf to see the minimum retention)

```ini
```

Changelog
=========

0.1:

 * Initial version


Thanks
========

* Scrapy: http://scrapy.org
* Galena: https://github.com/20minutes/galena
* Graphite: http://graphite.wikidot.com/

Licence
=======
Copyright 2011 Julien Duponchelle

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
