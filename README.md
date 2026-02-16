Transformer from Scratch: Rumi Poetry Generator

### معرفی پروژه (Project Overview)
این پروژه بر روی پیاده‌سازی عمیق و از پایه (From Scratch) معماری ترانسفورمرها (Transformers) تمرکز دارد. هدف اصلی، درک دقیق و پیاده‌سازی الگوریتم‌های زیرساختی هوش مصنوعی بدون استفاده از کتابخانه‌های سطح بالا یا مدل‌های از پیش آماده بوده است.

 
ویژگی‌های کلیدی این پیاده‌سازی:

معماری خالص: تمامی اجزا، از جمله مکانیسم توجه (Self-Attention)، لایه‌های نرمال‌سازی و بلاک‌های ترانسفورمر، بدون استفاده از کتابخانه‌های آماده و با PyTorch خالص کدنویسی شده‌اند.

توکنایزر منعطف (Char & BPE): این پروژه از دو نوع توکنایزر پشتیبانی می‌کند:

Character-level: برای آموزش سریع و پایه‌ای.

BPE (Byte Pair Encoding): پیاده‌سازی دستی الگوریتم BPE مشابه GPT برای فشرده‌سازی بهتر توکن‌ها.

پیش‌پردازش اختصاصی فارسی: شامل ماژول پاک‌سازی متن برای یکسان‌سازی کاراکترهای فارسی/عربی، حذف اعراب و نرمال‌سازی متن جهت بهبود کیفیت خروجی مدل روی اشعار کلاسیک.

منابع: الهام گرفته از مقاله "Attention Is All You Need" و آموزش‌های Andrej Karpathy.

متن پیشنهادی اصلاح شده (English)
بخش انگلیسی شما (Architecture) دقیق است، اما بخش مربوط به Tokenizer در لیست ویژگی‌ها نیاز به اصلاح دارد.

Revised Key Features Section:

Pure Implementation: All components, including Self-Attention mechanisms, LayerNorm, and Transformer blocks, are coded from scratch using raw PyTorch.

Flexible Tokenizer: The model includes manual implementations for two tokenization strategies:

Character-level: For baseline performance and simplicity.

BPE (Byte Pair Encoding): An implementation similar to GPT's tokenizer for efficient sub-word processing.

Persian Text Preprocessing: Includes a custom pipeline to normalize Persian characters (unifying Yeh/Keph), remove diacritics, and handle RTL formatting specifically tailored for Rumi's poetry.
