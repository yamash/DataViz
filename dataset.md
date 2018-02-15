---
layout: page
title: About our data
<!--subtitle: Why you'd want to go on a date with me-->
---
Our data was extracted from the <a href="https://www.epo.org/index.html"> European Patent Office (EPO)</a>.The EPO offers on its web site several free services, including Espacenet and Open Patent Services (OPS) for searching within more than 90 million patent documents from around the world and from the 19th century right up to today. We used their tool PATSTAT Online to query their database and export structured data.
```sql
SELECT A.appln_id, A.appln_abstract, B.appln_filling_year  
FROM tls203_appln_abstr as A, tls201_appln as B  
WHERE (A.appln_id = B.appln_id AND B.appln_auth = 'CH' AND A.appln_abstract_lg = 'en')
```
We chose patents whose abstract had been filled (`appln_auth`) in Switzerland and whose language is english.