# راهنمای استفاده از Obsidian MD با نینی‌نیت

این راهنما به شما کمک می‌کند تا از Obsidian MD برای مدیریت محصولات و محتوای سایت نینی‌نیت استفاده کنید.

## 📁 ساختار فایل‌ها

```
niniknit.github.io/
├── _products/          # محصولات (برای Obsidian)
├── _categories/        # دسته‌بندی‌ها (برای Obsidian)
├── _posts/            # پست‌های وبلاگ (برای Obsidian)
├── _layouts/          # قالب‌های Jekyll
├── _includes/         # اجزای قابل استفاده مجدد
└── images/            # تصاویر محصولات
```

## 🛍️ اضافه کردن محصول جدید

### 1. ایجاد فایل محصول در Obsidian

1. در Obsidian، پوشه `_products` را باز کنید
2. فایل جدیدی با نام مناسب ایجاد کنید (مثال: `baby-sweater-pink.md`)
3. از قالب زیر استفاده کنید:

```markdown
---
title: نام محصول
description: توضیح کوتاه محصول
category: sweaters  # یا hats, booties, sets
price: "۱۵۰,۰۰۰"
sizes: ["0-3 ماه", "3-6 ماه", "6-12 ماه"]
colors:
  - name: "صورتی"
    code: "#FFB6C1"
    text_color: "#000"
  - name: "آبی"
    code: "#87CEEB"
    text_color: "#000"
images:
  - "/images/baby-sweater-pink-1.jpg"
  - "/images/baby-sweater-pink-2.jpg"
features:
  - "بافتنی دست‌ساز"
  - "نرم و راحت"
  - "قابل شستشو"
---

توضیحات کامل محصول در اینجا...

## ویژگی‌های خاص:
- ویژگی ۱
- ویژگی ۲

## نحوه مراقبت:
- دستورالعمل مراقبت
```

### 2. دسته‌بندی‌های موجود

- `sweaters` - پلیورها و ژاکت‌ها
- `hats` - کلاه‌ها  
- `booties` - جوراب‌ها و دستکش‌ها
- `sets` - ست‌های کامل

### 3. اضافه کردن دسته‌بندی جدید

در پوشه `_categories` فایل جدیدی ایجاد کنید:

```markdown
---
title: نام دسته‌بندی
slug: category-name
description: توضیح دسته‌بندی
layout: category
---

توضیحات کامل دسته‌بندی...
```

## 📝 نوشتن پست وبلاگ

### 1. ایجاد پست جدید

1. در پوشه `_posts` فایل جدیدی ایجاد کنید
2. نام فایل باید به فرمت `YYYY-MM-DD-title.md` باشد
3. از قالب زیر استفاده کنید:

```markdown
---
layout: post
title: "عنوان پست"
date: 2025-10-08
categories: [دسته‌بندی]
tags: [برچسب1, برچسب2]
---

محتوای پست در اینجا...

## بخش ۱
توضیحات...

## بخش ۲
توضیحات...
```

## 🖼️ مدیریت تصاویر

### 1. اضافه کردن تصاویر محصول

1. تصاویر را در پوشه `images/` قرار دهید
2. نام‌گذاری: `product-name-number.jpg`
3. در فایل محصول، مسیر تصاویر را اضافه کنید:

```yaml
images:
  - "/images/baby-sweater-1.jpg"
  - "/images/baby-sweater-2.jpg"
```

### 2. بهینه‌سازی تصاویر

- اندازه مناسب: 800x600 پیکسل
- فرمت: JPG یا PNG
- حجم: کمتر از 500KB

## 🔧 تنظیمات Obsidian

### 1. پلاگین‌های مفید

- **Templater**: برای قالب‌های خودکار
- **QuickAdd**: برای اضافه کردن سریع محصولات
- **Image Toolkit**: برای مدیریت تصاویر
- **Dataview**: برای نمایش محصولات

### 2. قالب‌های پیش‌فرض

#### قالب محصول جدید (Product Template)

```markdown
---
title: {{title}}
description: {{description}}
category: {{category}}
price: "{{price}}"
sizes: [{{sizes}}]
colors:
  - name: "{{color1}}"
    code: "{{color1_code}}"
    text_color: "#000"
images:
  - "/images/{{title_slug}}-1.jpg"
features:
  - "بافتنی دست‌ساز"
  - "نرم و راحت"
  - "قابل شستشو"
---

{{description}}

## ویژگی‌های خاص:
- ویژگی ۱
- ویژگی ۲

## نحوه مراقبت:
- دستورالعمل مراقبت
```

#### قالب پست وبلاگ (Blog Post Template)

```markdown
---
layout: post
title: "{{title}}"
date: {{date}}
categories: [{{category}}]
tags: [{{tags}}]
---

{{content}}

## بخش ۱
توضیحات...

## بخش ۲
توضیحات...
```

## 📊 نمایش محصولات در Obsidian

### 1. استفاده از Dataview

```dataview
TABLE title, category, price
FROM "_products"
SORT title ASC
```

### 2. فیلتر کردن محصولات

```dataview
TABLE title, price
FROM "_products"
WHERE category = "sweaters"
SORT price ASC
```

## 🚀 انتشار تغییرات

### 1. ذخیره و همگام‌سازی

1. فایل‌ها را در Obsidian ذخیره کنید
2. تغییرات را در Git commit کنید
3. به GitHub push کنید

### 2. بررسی سایت

1. سایت را در `http://localhost:4000` بررسی کنید
2. از Jekyll serve استفاده کنید: `bundle exec jekyll serve`

## 💡 نکات مفید

### 1. نام‌گذاری فایل‌ها

- از خط تیره (-) استفاده کنید
- از فاصله استفاده نکنید
- نام‌ها را کوتاه و واضح انتخاب کنید

### 2. مدیریت محتوا

- از برچسب‌ها برای دسته‌بندی استفاده کنید
- توضیحات را کامل و جذاب بنویسید
- تصاویر با کیفیت اضافه کنید

### 3. بهینه‌سازی SEO

- عنوان‌ها را واضح و جذاب انتخاب کنید
- توضیحات را کامل بنویسید
- از کلمات کلیدی مناسب استفاده کنید

## 🔗 لینک‌های مفید

- [مستندات Jekyll](https://jekyllrb.com/docs/)
- [راهنمای Obsidian](https://help.obsidian.md/)
- [راهنمای Markdown](https://www.markdownguide.org/)

---

**نکته**: همیشه قبل از انتشار، سایت را محلی تست کنید تا از صحت کارکرد اطمینان حاصل کنید.
