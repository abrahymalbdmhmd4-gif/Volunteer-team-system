#  Myameen Student Evaluation Bot (MSEB)

## Overview

This repository contains the n8n workflow configuration for the **Myameen Student Evaluation Bot (MSEB)**. This automated Telegram bot is designed to manage and track volunteer and student task submissions. It interacts with users step-by-step to gather task details and logs the finalized reports directly into a Google Spreadsheet.

## Features

* **Telegram Integration:** Triggers on regular messages and callback queries (inline keyboards) from Telegram.


* **User Authentication:** Cross-references the user's Telegram Chat ID with a registered list in Google Sheets ("سجل المعرفات - IDs") to ensure they are an authorized team member. Unauthorized users receive an automated apology message.


* **Multi-Stage Data Collection:** Guides volunteers through a structured 4-stage inquiry process:
* **Task Status:** Asks if the task is done or not done.


* **Task Type:** Collects the role/mission type (e.g., Drafting, Proofreading, Design, Video Production, Scientific Editing).


* **Lecture Number:** Allows the selection of the relevant lecture number (from 1 to 20).


* **Delay Check:** Asks if there was a delay of more than two days in submitting the task to the next volunteer.




* **Dynamic UI State:** Uses HTTP requests to the Telegram API to edit message reply markups, removing buttons once the user makes a selection.


* **Session Management:** Utilizes custom JavaScript nodes to track active user sessions, handle stage progression, prevent duplicate clicks, and enforce a 2-hour session timeout.


* **Automated Logging:** Appends the collected data (Student Name, Telegram ID, Task Type, Delay, Task Status, and Lecture Number) into the designated Google Sheet.



## Prerequisites

To run this workflow successfully in your n8n instance, you will need:

* **Telegram Credentials:** Configured Telegram API credentials named `Myameen_bot`.


* **Google Sheets Credentials:** Configured Google Sheets OAuth2 API credentials named `Google Sheets account`.


* **Google Sheets Document:** Access to the master Google Sheet used for tracking user IDs and logging evaluation results.



## Installation & Deployment

1. Download the `Myameen Student Evaluation Bot (MSEB) (1).json` file.


2. Open your n8n workspace and create a new workflow.
3. Click on the options menu in the top right corner and select **Import from File**.
4. Upload the downloaded JSON file.
5. Reconnect the Telegram and Google Sheets nodes to your local credentials.
6. Activate the workflow.

---

<div dir="rtl">

#   بوت التقييم | ميامين (MSEB)

## نظرة عامة
يحتوي هذا الملف على إعدادات مسار العمل لبرنامج `n8n` الخاص ببوت `Myameen Student Evaluation Bot`. تم تصميم هذا البوت الآلي على منصة التلغرام لإدارة وتتبع تسليم مهام المتطوعين والطلاب. يتفاعل البوت مع المستخدمين خطوة بخطوة لجمع تفاصيل المهام، ثم يقوم بتسجيل التقارير النهائية مباشرة في جداول بيانات جوجل (`Google Sheets`).

## الميزات الأساسية
* **التكامل مع التلغرام:** يتم تفعيل المسار عند تلقي رسائل عادية أو أحداث استجابة (`Callback Queries`) من الأزرار التفاعلية في التلغرام.
* **المصادقة والتحقق:** يقوم بمطابقة معرف المحادثة (`Chat ID`) الخاص بالمستخدم مع قائمة مسجلة في شيت جوجل ("سجل المعرفات - IDs") للتأكد من أنه متطوع معتمد في الفريق. يتلقى المستخدمون غير المصرح لهم رسالة اعتذار تلقائية.
* **جمع البيانات متعدد المراحل:** يوجه المتطوعين عبر عملية استعلام منظمة مكونة من 4 مراحل:
  * **حالة المهمة:** يسأل عما إذا كانت المهمة قد "تمت بنجاح" أو "لم تتم بعد".
  * **نوع المهمة:** يجمع نوع المهمة أو الدور (مثل: كتابة مسودة، تدقيق، تصميم، منتج فيديوهات، مدقق علمي، إلخ).
  * **رقم المحاضرة:** يتيح اختيار رقم المحاضرة المعنية (من 1 إلى 20).
  * **التحقق من التأخير:** يسأل عما إذا كان هناك تأخير تجاوز اليومين في تسليم المهمة للمتطوع التالي.
* **تحديث واجهة المستخدم ديناميكياً:** يستخدم طلبات `HTTP` إلى واجهة برمجة تطبيقات التلغرام (`Telegram API`) لتعديل الرسائل وإخفاء الأزرار بمجرد قيام المستخدم بالاختيار.
* **إدارة الجلسات:** يعتمد على عُقد مبرمجة بلغة `JavaScript` لتتبع الجلسات النشطة للمستخدمين، إدارة التقدم في المراحل، منع النقرات المكررة، وتطبيق مهلة زمنية للجلسة مدتها ساعتين.
* **التسجيل التلقائي:** يقوم بإضافة البيانات المجمعة (اسم الطالب، معرف التلغرام، المهمة، حالة التأخير، حالة المهمة، ورقم المحاضرة) كصفوف جديدة في شيت جوجل المخصص.

## المتطلبات المسبقة
لتشغيل مسار العمل هذا بنجاح في بيئة `n8n` الخاصة بك، ستحتاج إلى:
* **بيانات اعتماد التلغرام:** إعداد بيانات اتصال `Telegram API` باسم `Myameen_bot`.
* **بيانات اعتماد جداول جوجل:** إعداد بيانات اتصال `Google Sheets OAuth2 API` باسم `Google Sheets account`.
* **مستندات جوجل شيت:** صلاحية الوصول إلى جداول بيانات جوجل الأساسية المستخدمة لتتبع معرفات المستخدمين وتسجيل نتائج التقييم.

## التثبيت والتشغيل
1. قم بتنزيل ملف `Myameen Student Evaluation Bot (MSEB) (1).json`.
2. افتح مساحة عمل `n8n` الخاصة بك وقم بإنشاء مسار عمل (`Workflow`) جديد.
3. انقر على قائمة الخيارات في الزاوية العلوية اليمنى واختر `Import from File`.
4. ارفع ملف `JSON` الذي قمت بتنزيله.
5. أعد ربط عُقد التلغرام وجداول جوجل (`Google Sheets`) ببيانات الاعتماد الخاصة بحساباتك.
6. قم بتفعيل مسار العمل عن طريق تفعيل خيار `Activate` للبدء بالاستخدام.

</div>