IDLE (Python) uygulamasının sadece kısayola tıklandığında çalışıp, python dosyalarına çift tıklandığında veya komut satırında doğrudan açılmamasının 3 temel nedeni vardır:
1. Varsayılan Birlikte Aç Programı Olmaması: Windows veya macOS, .py uzantılı dosyaları çift tıkladığınızda IDLE ile değil, Python'ın arka plan motoru (python.exe) ile çalıştırır. Kod penceresi açılmadan siyah bir komut ekranı yanıp sönüyorsa, sistem dosyayı düzenlemek yerine doğrudan "çalıştırmaya" ayarlıdır.
2. Ortam Değişkenlerinde (PATH) Olmaması: Komut satırına (CMD veya Terminal) sadece idle yazdığınızda açılmıyorsa, Python kurulurken "Add python.exe to PATH" seçeneği işaretlenmemiştir veya IDLE'ın kurulu olduğu dizin sistem tarafından tanınmıyordur.
3. IDLE'ın Aslında Bir Python Betiği Olması: IDLE kendi başına bağımsız bir .exe programı değildir. Python ile yazılmış bir script'tir (idle.pyw). Kısayollar arka planda bu scripti tetikleyecek şekilde özel hedeflerle yapılandırılmıştır.



 Python Dosya Sistemi nasıl çalışır?

Python'u kurduğunuzda dosyalar kabaca şöyle düzenlenir:

python/

├── python.exe (Windows) / bin/python3 (Linux, macOS)

├── Lib/ (lib/python3.x/)   → standart kütüphane (os, json, pathlib...)

│   └── site-packages/      → pip ile kurulan üçüncü parti paketler

├── Scripts/ (bin/)         → pip, venv gibi çalıştırılabilir araçlar

├── DLLs/ (lib-dynload/)    → C ile yazılmış uzantı modülleri

├── include/                → C uzantıları için başlık dosyaları

└── tcl/                    → tkinter için gerekenler
          
