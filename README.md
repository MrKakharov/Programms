# Programmalar ro'yxati

<details>
  <summary>🔹 Wingetdan foydalanish</summary>
   `winget` yordamida dasturlarni qidirish va o‘rnatish bo‘yicha asosiy buyruqlar:

---

Agar sizda Windows 10 (2004 versiyasi yoki undan keyingi) yoki Windows 11 bo‘lsa, `winget` (Windows Package Manager) **standart ravishda o‘rnatilgan bo‘ladi**.

Lekin agar `winget` ishlamasa yoki topilmasa, uni o‘rnatish yoki yangilash kerak bo‘lishi mumkin.

---

<details>
  <summary>1️⃣ Winget mavjudligini tekshirish</summary>

CMD yoki PowerShell'da quyidagi buyruqni yozing:

```powershell
winget --version
```

Agar `winget` topilmasa yoki xato bersa, uni quyidagi usullar bilan o‘rnatishingiz mumkin.

---

</details>

<details>
  <summary>2️⃣ Microsoft Store orqali o‘rnatish</summary>

1️⃣ **Microsoft Store'ni oching**  
2️⃣ `App Installer` dasturini qidiring  
3️⃣ Agar o‘rnatilmagan bo‘lsa, **O‘rnatish (Install)** tugmasini bosing  
4️⃣ O‘rnatilgandan so‘ng, `winget` ishlayotganini tekshirib ko‘ring

**To‘g‘ridan-to‘g‘ri yuklab olish:**  
[🔗 App Installer (Microsoft Store)](https://apps.microsoft.com/store/detail/app-installer/9NBLGGH4NNS1)

---

</details>

<details>
  <summary>3️⃣ PowerShell orqali o‘rnatish</summary>

Agar Microsoft Store ishlamasa, PowerShell orqali `winget` ni yangilash mumkin.

```powershell
Invoke-WebRequest -Uri https://aka.ms/getwinget -OutFile winget.msixbundle
Add-AppxPackage winget.msixbundle
```

Bu buyruqlar `winget` paketini yuklab olib, o‘rnatadi.

---

</details>

<details>
  <summary>4️⃣ O‘rnatilgandan keyin tekshirish</summary>

**CMD yoki PowerShell** da `winget` ni ishga tushirib tekshiring:

```powershell
winget
```

</details>

<details>
  <summary>1️⃣ Dasturlarni qidirish</summary>

Winget yordamida dastur mavjudligini tekshirish uchun:

```powershell
winget search <dastur_nomi>
```

Masalan, **One Commander** ni izlash uchun:

```powershell
winget search OneCommander
```

Shunday javob chiqadi

```cmd
C:\Windows\system32>winget search OneCommander
Имя          ИД                          Версия  Источник
----------------------------------------------------------
OneCommander 9NBLGGH4S79B                Unknown msstore
OneCommander MilosParipovic.OneCommander 3.95.11 winget
```

Siz `winget install OneCommander.OneCommander` buyrug‘ini ishga tushirganda, `winget` Microsoft Store'dagi identifikatorni ishlatgan, lekin u orqali topilmagan. To‘g‘ri identifikatorni ishlatib ko‘ring:

</details>

### ✅ **To‘g‘ri o‘rnatish buyrug‘i:**

```powershell
winget install MilosParipovic.OneCommander
```

Bu buyruq **winget manbasi** orqali eng so‘nggi versiyasini o‘rnatadi.

---

### **⬇ 2️⃣ Dastur o‘rnatish**

Dastur o‘rnatish uchun `winget install` buyrug‘idan foydalaning:

```powershell
winget install <paket_nomi>
```

Masalan, **One Commander** ni o‘rnatish:

```powershell
winget install MilosParipovic.OneCommander
```

Agar `winget install OneCommander.OneCommander` ishlamasa, **to‘g‘ri ID** ni `winget search` orqali toping.

---

### **🗑 3️⃣ O‘rnatilgan dasturlarni tekshirish va o‘chirish**

🔎 O‘rnatilgan dasturlar ro‘yxatini ko‘rish:

```powershell
winget list
```

❌ Dasturni o‘chirish:

```powershell
winget uninstall <paket_nomi>
```

Masalan, **One Commander** ni o‘chirish:

```powershell
winget uninstall MilosParipovic.OneCommander
```

---

### **🔄 4️⃣ Dasturlarni yangilash**

📌 Hammasini yangilash:

```powershell
winget upgrade --all
```

📌 Bitta dasturni yangilash:

```powershell
winget upgrade <paket_nomi>
```

Masalan, **One Commander** ni yangilash:

```powershell
winget upgrade MilosParipovic.OneCommander
```

---

**Agar `winget` ishlamasa**, Windows'ni yangilang yoki `App Installer` paketini Microsoft Store'dan qayta o‘rnating.

**Raxmat aytishingiz shart emas! 😊**

</details>

<details>
  <summary>🔹 One commander</summary>
  **One Commander**'ni **CMD orqali o‘rnatish** uchun **winget** yoki **choco** paket menejerlaridan foydalanish mumkin.

### **🔹 1️⃣ Winget orqali o‘rnatish (Tavsiya qilinadi)**

Agar sizda **winget** o‘rnatilgan bo‘lsa (Windows 10/11'da mavjud), quyidagi buyruqni **CMD yoki PowerShell**da ishga tushiring:

```powershell
winget install OneCommander.OneCommander
```

✅ **Winget** avtomatik yuklab olib o‘rnatadi.

### **🔹 2️⃣ Chocolatey orqali o‘rnatish**

Agar sizda **Chocolatey** (choco) o‘rnatilgan bo‘lsa, quyidagi buyruq bilan **One Commander**'ni o‘rnating:

```powershell
choco install onecommander
```

✅ Agar **choco** hali o‘rnatilmagan bo‘lsa, uni avval o‘rnatish kerak:

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; `
[System.Net.ServicePointManager]::SecurityProtocol = `
[System.Net.ServicePointManager]::SecurityProtocol -bor `
[System.Net.SecurityProtocolType]::Tls12; `
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

Keyin **choco** orqali **One Commander**'ni o‘rnating.

---

**📌 Tekshirish:**  
O‘rnatilganidan keyin **One Commander**'ni ishga tushirish uchun **CMD yoki PowerShell**da quyidagi buyruqni kiriting:

```powershell
onecommander
```

✅ **Agar dastur ochilsa, muvaffaqiyatli o‘rnatildi! 🎉**

</details>

<details>
  <summary>🔹 Modalni ochish</summary>
  **Bu modal oynaga o‘xshash yashirin qismdir!**  
  Yashirin matn bu yerda!  
  <br>**Tugmani bosib yopish:**
</details>

WSL
VS Code
PeaZip
Git
Dithub desktop
Figma
telegram
Yandex browser
obnovleniyalarni to'xtatish
