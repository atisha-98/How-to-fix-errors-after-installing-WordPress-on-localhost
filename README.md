# How-to-fix-errors-after-installing-WordPress-on-localhost

رفع خطای object not found در لوکال هاست زمپ

این خطا زمانی رخ میدهد که در دایرکتوری پوشه‌ای که وردپرس در آن نصب شده اشتباهی صورت گرفته باشد. این مورد معمولا در صورت تغییر پوشه‌ای که وردپرس روی آن نصب شده است رخ میدهد و برای رفع این مشکل باید نام پوشه را به همون نام قبلی تغییر دهید. اما در صورتی که نام این پوشه را بخاطر تغییر آدرس سایت در لوکال هاست تغییر دادید جای هیچ نگرانی وجود ندارد و کافی است تا داخل دیتابیس یعنی درست در قسمتی که شامل جدول مربوط به تنظیمات وردپرس میشود نام پوشه جدیدی که قصد دارید وارد کنید تا در .دیتابیس ذخیره شده و امکان دسترسی به سایت در حالت لوکال با آدرس جدید برایتان فراهم گردد.



رفع خطای You don’t have permission to access در زمپ

این خطا به دلیل عدم امکان اجازه دسترسی به آی‌پی در phpmyadmin است و برای رفع آن ابتدا به مسیر c:\wamp\alias\phpmyadmin.conf مراجعه کنید و سپس فایلی که با عنوان phpmyadmin.conf می‌باشد را با استفاده از یک نرم‌افزار ویرایشگر متن همچون نوت‌پد باز کنید خواهید دید که کدهای زیر در آن قرار دارد.



1 Alias /phpmyadmin "c:/wamp/apps/phpmyadmin3.1.3.1/" #

2 to give access to phpmyadmin from outside #

3 replace the lines # # 

4 Order Deny,Allow # 

5 Deny from all #    

6 Allow from 127.0.0.1 # # by # #       

7 Order Allow,Deny #   Allow from all #    

8 Options Indexes FollowSymLinks MultiViews    

9 AllowOverride all  

10 Order Deny,Allow    

11 Deny from all

12 Allow from 127.0.0.1


همونطوری که میبینید در خط یکی به آخر عبارت Deny from all قرار دارد که کافی است با تغییر دادن آن خط به Allow from all  فایل را ذخیره کنید، حال یک بار با کلیک بر روی دکمه Quit زمپ را خاموش کرده و مجددا با اجرا و کلیک بر روی دکمه‌های start که در مقابل آپاچی و mysql قرار دارد آن را اجرا کرده و به سایت خود مراجعه کنید، اگر باز  هم با چنین خطایی مواجه شدید این بار خط آخر که شامل Allow from 127.0.0.1 را حذف کنید و مجددا تست کنید. در صورتی که باز هم مشکل پابرجا بود این بار مجددا فایل  phpmyadmin.conf را باز کرده و عبارت Allow from all را به Allow from 127.0.0.1 ::1 تغییر بدین و فایل را ذخیره کنید، به عبارت دیگه خروجی کامل کدهای موجود در این فایل باید به صورت زیر در شود.


1 Alias /phpmyadmin "c:/wamp/apps/phpmyadmin3.1.3.1/" #

2 to give access to phpmyadmin from outside #

3 replace the lines # # 

4 Order Deny,Allow # 

5 Deny from all #    

6 Allow from 127.0.0.1 # # by # #       

7 Order Allow,Deny #   Allow from all #    

8 Options Indexes FollowSymLinks MultiViews    

9 AllowOverride all  

10 Order Deny,Allow    

11 Order Deny,Allow

12 Allow from 127.0.0.1 ::1


پس از ذخیره فایل مورد نظر مجددا زمپ را غیرفعال کرده و اجرا کنید تا مشکل رفع شود.
















