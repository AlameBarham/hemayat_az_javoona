<div dir="rtl" align="right">

## پروژه: تشخیص ارقام دست‌نویس (MNIST)

این مخزن شامل نوت‌بوک `Mnist.ipynb` برای آموزش یک شبکهٔ عصبی ساده روی دیتاست MNIST است؛ هدف، طبقه‌بندی ارقام ۰ تا ۹ می‌باشد.

### امکانات
- بارگذاری و پیش‌پردازش داده‌های MNIST
- تعریف مدل MLP ساده (قابل ارتقاء به CNN)
- آموزش با `CrossEntropyLoss` و بهینه‌ساز Adam/AdamW
- ارزیابی روی دادهٔ تست و گزارش دقت

### پیش‌نیازها
- Python 3.10 یا جدیدتر (آزمایش‌شده با Python 3.12)
- PyTorch
- NumPy، Matplotlib
- (اختیاری) scikit-learn برای گزارش معیارها

نصب سریع (Windows/PowerShell):

```bash
python -m venv .venv
.\.venv\Scripts\activate
pip install --upgrade pip
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu
pip install numpy matplotlib scikit-learn jupyter
```

> اگر GPU دارید، دستور نصب متناسب با CUDA را از وب‌سایت PyTorch جایگزین کنید.

### اجرا
1) محیط مجازی را فعال کنید و وابستگی‌ها را نصب کنید.
2) Jupyter را اجرا کنید و نوت‌بوک را باز کنید:

```bash
jupyter notebook
```

3) نوت‌بوک `Mnist.ipynb` را باز کرده و سلول‌ها را به‌ترتیب اجرا کنید.

### ساختار پروژه
```
Mnist(8, 8)/
├─ Mnist.ipynb        # نوت‌بوک اصلی آموزش/ارزیابی
├─ README.md          # این فایل
└─ (خروجی‌ها در صورت ذخیره)
```

### نکات مدل
- خروجی نهایی اندازهٔ ۱۰ (تعداد کلاس‌ها) است؛ از `nn.CrossEntropyLoss` استفاده می‌شود.
- برای بهبود عملکرد:
  - لایه‌های بیشتر/پهن‌تر، `BatchNorm1d`، و `Dropout` متوسط
  - بهینه‌ساز `AdamW` با `weight_decay`
  - زمان‌بند یادگیری (LR Scheduler) و Early Stopping
  - ارتقاء به CNN با ورودی `N×1×28×28`

### نتایج نمونه
- دقت معمول یک MLP ساده روی MNIST حدود ۹۵٪ ± است.
- با یک CNN سبک، رسیدن به ۹۸–۹۹٪ رایج است.

### لایسنس
این پروژه تحت مجوز MIT منتشر شده است.

### مشارکت
پیشنهادها و Pull Requestها خوش‌آمدند.

</div>
