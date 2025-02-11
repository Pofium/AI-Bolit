Сканер AI-BOLIT предназначен для проверки сайта на вирусы и вредоносное программное обеспечение. Его можно использовать в качестве профилактической меры для регулярной проверки сайта на вирусы, а также для поиска хакерских скриптов, бэкдоров, фишинговых страниц, вставок вредоносного кода, дорвеев, ссылочного спама и других вредоносных элементов в файлах.

Сканер может запускать проверку непосредственно на хостинге (рекомендуется запускать сканер через командную строку по SSH), а также на локальном компьютере под любой операционной системой (Windows, MacOS X, *nix). AI-BOLIT Scanner использует собственную базу данных вредоносных программ, а также специальный эвристический алгоритм для обнаружения новых (еще неизвестных) вредоносных фрагментов. В случае обнаружения опасных файлов он формирует отчет со списком файлов в формате HTML или текстовом формате.

Сканер имеет два режима работы: "нормальный" и "параноидальный".

Для диагностики заражения сайта достаточно проверить файлы в "нормальном" режиме. Он дает мало ложных срабатываний и подходит для оценки заражения сайта или факта компрометации. Для тщательной проверки сайта на вирусы и хакерские скрипты, а также для формирования отчета для лечения сайта, необходимо проверить файлы в "параноидальном" режиме. Этот отчет включает не только известные вредоносные фрагменты или хакерские скрипты, но и подозрительные фрагменты, которые следует тщательно проанализировать, так как они потенциально могут быть вредоносными.

Иногда одни и те же участки кода могут использоваться как в хакерских скриптах, так и в скриптах легитимных CMS. Поскольку невозможно автоматически определить, является ли фрагмент вредоносным на 100%, такой файл будет указан в отчете, и вам следует вручную проверить, опасен ли он.

Если у вас возникли вопросы по отчету, вы всегда можете отправить его на анализ по адресу ai@revisium.com (в .zip архиве с паролем).

Полная проверка (рекомендуется):
Скопируйте все содержимое папки /ai-bolit/ в корневую папку сайта.

Запустите командную строку сервера через SSH.

Выполните следующую команду:

bash
Copy
php ai-bolit.php
Для запуска сканера в "параноидальном" режиме используйте аргументы:

bash
Copy
php ai-bolit.php --mode=1 - нормальный режим
php ai-bolit.php --mode=2 - параноидальный режим
Дождитесь завершения формирования отчета.

Скопируйте файл AI-BOLIT-REPORT-<дата>-<время>.html с сервера на ваш локальный компьютер и откройте его в браузере.

Простая инструкция (Моя рабочая среда: "cat /etc/redhat-release" >>>> "CentOS Linux release 7.7.1908 (Core)")

bash
Copy
$ wget https://github.com/KashifHK123/AI-Bolit/raw/master/ai-bolit/AIBOLIT-WHITELIST.db && wget https://github.com/KashifHK123/AI-Bolit/raw/master/ai-bolit/ai-bolit.php
$ php ai-bolit.php
Если вы видите "Segmentation fault", это вызвано расширением PHP-Opcache. Чтобы исправить это, выполните команду:

bash
Copy
$ php -n -d extension=/usr/lib64/php/modules/opcache.so -q ai-bolit.php
или

bash
Copy
$ php -n -d extension=/usr/lib64/php/modules/opcache.so -q ai-bolit.php /some/path/to/scan
Если вы не знаете, как анализировать отчет, или вам нужно удалить вредоносный код или защитить ваш сайт от хакеров, напишите нам на ai@revisium.com.

Revisium - лечение и защита сайтов
https://revisium.com/en/home/
audit@revisium.com

AI-BOLIT scanner is designed to scan the site for viruses and malware. It can be used as a preventive measure to regularly check the site for the viruses, and to find the hacker shells, backdoors, phishing pages, malware insertions, doorway pages, link spam and other malware pieces in the files.

Scanner can run scanning directly on the hosting (recommended start the scanner from the command line via SSH), as well as on the local computer under any operating system (Windows, MacOS X, *nix). AI-BOLIT Scanner using proprietary malware database as well as a special heuristic detection algorith to detect new (not yet known) malicious fragments. In case of detection of dangerous files it generates a report with a list of files in html or text format.

The scanner has two operational modes: "normal" and "paranoid".

For the diagnosis of the website infection it is enough to check the files in the "normal" mode. He gives few false positives and is suitable for assessing the infection site or fact of compromise. In order to thoroughly check out the site for viruses and hacker scripts, as well as generate a report for the treatment site, you need to check the files in the "paranoid" mode. This report does not just known malware fragments or hacker's scripts, but also suspicious fragments that should be analyzed carefully, as they could potentially be harmful.

Sometimes, the same sections of code can be used as a hacker scripts and script of legitimate CMS. Since it is impossible to automatically determine whether the malicious snippet is for 100%. This file will be listed on the report, and you should manually check if the file is dangerous.

If you have any questions regarding the report, you can always send it for analysis to ai@revisium.com (in .zip archive with the password).


Full scan (recommended):
--------------------------------

1. copy all content of /ai-bolit/ folder into the root folder of web site

2. run server command line though ssh

3. execute the following command

   php ai-bolit.php

   In order to run scanner in "paranoid" mode use arguments

   php ai-bolit.php --mode=1 - normal mode 
   php ai-bolit.php --mode=2 - paranoid mode

4. wait until the report is generated

5. copy file AI-BOLIT-REPORT-<date>-<time>.html from server to your local PC and open it in a browser

---
Easy Instruction ( My Working envoirment is "cat /etc/redhat-release" >>>> "CentOS Linux release 7.7.1908 (Core)" )

$ wget https://github.com/KashifHK123/AI-Bolit/raw/master/ai-bolit/AIBOLIT-WHITELIST.db && wget https://github.com/KashifHK123/AI-Bolit/raw/master/ai-bolit/ai-bolit.php
$ php ai-bolit.php

if see " Segmentation fault " it's cause is PHP-Opcache Extention for fix it run this command 
$ php -n -d extension=/usr/lib64/php/modules/opcache.so -q ai-bolit.php
or
$ php -n -d extension=/usr/lib64/php/modules/opcache.so -q ai-bolit.php /some/path/to/scan

---

If you don't know how to analyze the report, or you need to remove malicious code or protect your website from hackers, email us ai@revisium.com. 

---

Revisium - website cured and secured
https://revisium.com/en/home/
audit@revisium.com
