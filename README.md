# SubCDN

SubCDN هي أداة بسيطة تستخدم للعثور على نطاقات المجالات الفرعية (subdomains) لموقع الويب الذي تريد فحصه. تقوم الأداة بالاتصال بخادم crt.sh للحصول على قائمة بجميع نطاقات المجالات الفرعية المسجلة للموقع، ثم تقوم بفحص كل نطاق فرعي للتحقق من وجود CDN مثل Cloudflare أو Akamai.

## كيفية استخدام SubCDN

يمكنك استخدام SubCDN بسهولة باستخدام الأسطر الأوامر في الوحدة النمطية. يجب عليك تحديد المجال الذي تريد فحصه باستخدام الخيار -D، ويمكنك تعيين عدد الخيوط المستخدمة في الفحص باستخدام الخيار -t. يمكنك استخدام الأمر التالي لتشغيل SubCDN:


python MrBOOND.py -D example.com -t 20


هذا الأمر سيقوم بفحص جميع نطاقات المجالات الفرعية لـ example.com باستخدام 20 موضوعًا.

## متطلبات التشغيل

- Python 3.6 أو أحدث
- المكتبات الموجودة في ملف requirements.txt يجب تثبيتها باستخدام الأمر pip install -r requirements.txt
 
لتثبيت الأداة في Termux  اتبع الاوامر التالية :


pkg update && pkg upgrade -y

pkg install python 

git clone https://github.com/MrBOOND/SubCDN

cd SubCDN

pip install -r requirements.txt

python MrBOOND -D example.com -t 20

## المكتبات المستخدمة

- argparse: لتحليل الخيارات الممررة في الأمر.
- csv: للكتابة في ملف CSV.
- json: لتحليل استجابات API من crt.sh.
- os: للتحقق من وجود ملف CSV.
- requests: للحصول على استجابات HTTP من crt.sh.
- concurrent.futures.ThreadPoolExecutor: لإنشاء خيوط متعددة لتسريع الفحص.
- rich.console: للطباعة بألوان مختلفة في الوحدة النمطية.



## المؤلف

تم تطوير الأداة بواسطة MrBOOND 
