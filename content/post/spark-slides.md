+++
categories = []
date = "2016-01-31T11:01:35+03:30"
description = ""
keywords = []
title = "spark slides"
draft = true
+++

# اسپارک چیست؟
* سیستم پردازش خوشه‌ای همه‌منظوره است.
* ای‌پی‌آی سطح بالا در زبان‌های جاوا، اسکالا، پایتون و آر ارائه می‌دهد.
* پشتیبانی از زبان R از نسخهٔ ۱٫۴
* فعّال‌ترین پروژهٔ آزاد در زمینهٔ پردازش کلان داده

# تاریخچه اسپارک
* مپ‌ردیوس در سال ۲۰۰۲ در گوگل
* هدوپ در سال ۲۰۰۶ در یاهو
* مقالهٔ اسپارک در سال ۲۰۱۰ آزمایشگاه AMPLab برکلی (متی زاهاریا)
* ایدهٔ هایو روی اسپارک و اس‌کیو‌ال روی اسپارک (شارک) که بعدها Spark SQL نامیده شد.
* نسخهٔ ۱٫۰ اسپارک در سال ۲۰۱۴

# نقاط ضعف هدوپ
* تنها مناسب برای پردازش دسته‌ای
* سرعت پایین
* سرعت پایین هدوپ برای پردازش‌های یادگیری ماشین
* هدوپ بین هر بار map و ردیوس نیاز به جابه‌جایی داده از/به دیسک/رم دارد.

# اسپارک
* پردازش تعاملی و تکراری
* الگوریتم‌های تکراری مثل ماشین لرنینگ
* پردازش در حافظه
* بازگشت‌پذیری خطا
* سرعت صد برابر مپ‌ردیوس هدوپ در حافظه و ده‌برابر روی دیسک
* ای‌پی‌آی یکپارچه برای پردازش جریانی و ...
* بیشتر از ۸۰ عملگر را پشتیبانی می‌کند.
* مناسب برای کوئری‌های ادهاک

# کامپوننت‌های اسپارک
* Spark SQL
* Spark MLib
* Spark GraphX
* Spark Streaming


# RDD
* Resilient Distributed Dataset
* Action: return value
* Transformations: return pointer to nre RDD
* Properties:
 - Immutable
 - Distributed
 - Lazily evaluated
 - Cacheable


# Partitions
- تمامی داده‌های ورودی، میانی، خروجی به صورت پارتیش دیده می‌شود.
- پارتیشن‌ها جزء اصلی و مهم پردازش موازی هستند.
- آر‌دی‌دی مجموعه‌ای از پارتشن‌هاست
- تمام پارتیشن‌ها غیر قابل تغییر هستند.
- هر ترنسفورمیشنی پارتیشن جدید ایجاد می‌‌کند.
- به صورت پیشفرض پارتیشن‌بندی توسط الگوریتم HashPartitioner انجام می‌شه اما میشه از الگوریتم دلخواه خودمون استفاده کنیم.


# Dependencies
* هر آر‌دی‌دی نیازمند آردی‌دی‌ای به نام والدش هست.
* والد اولین آردی‌دی Nil هست.
* قبل از پردازش مقدار هر آر‌دی‌دی اول آردی‌دی والد پردازش می‌شود.

# Transformations
* map, flatMap, filter, mapPartition, mapPartitionWithIndex, sample, union, distinct, groupByKey, reduceByKey, sortBeyKey, join, cogroup, pipe, ...

# Actions
reduce, collect, count, first, take, takeSample, takeOrdered, countByKey, ...

# Dataset
تبدیل آبجکت جی‌وی‌ام به Dataset Row
