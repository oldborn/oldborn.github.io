---
layout: post
title: <span>Logstash JDBC</span>
description: <br>a JDBC Output Plugin
img: /img/logstash_icon.jpg
---

Last year we (in EVAM) migrated our whole log system to elasticsearch, while doing that we added lots of visualization capabilities to the core product as well. Since our customers generally do not want to lose their comfort zone (logs in their beloved relational databases) we had to maintain the previous log structure.
So we decided to rely on <a href="https://github.com/theangryangel/logstash-output-jdbc" target="_blank">logstash jdbc output plugin</a> of `theangryangel`. Unfortunately, we did not get the through-put we were aiming for. After very long JMX Console sessions we realized that this plugin was not batching the logs correctly, so naturally, we decided to implement a new output plugin. Since we all had a Java background, the project Logstash JDBC Output Plugin (Java) was born.
<br><br>
I managed to persuade my supervisor to make this plugin opensource. Although, it is not well structured or documented, or tested... I think it might help a fellow developer.
By using Java, we easily managed to persist ~20K logs per second while the ruby plugin could not pass 8K.
<br><br>
Here is the github link if you want to look into it: <a href="https://github.com/oldborn/logstash_jdbc_output_plugin" target="_blank">https://github.com/oldborn/logstash_jdbc_output_plugin</a>.