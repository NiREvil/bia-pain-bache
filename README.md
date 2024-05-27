> [!CAUTION]
> BpB No TLS  
> Temporary branch


فرق این **branch** با **Main** فقط تو پیکربندی کانفیگ هستش. دقیقا در لاین `796` الی `803`  
از این لاین بخش tls و sni حذف شده تا بتونیم از پورت های بدون tls استفاده کنیم.
در حالت عادی این شکلی بود لاین 796 الی 803
```js
        vlessWsTls += 'vless' + `://${userID}@${addr}:443?encryption=none&security=tls&type=ws&host=${
            randomUpperCase(hostName)
        }&sni=${
            randomUpperCase(hostName)
        }&fp=randomized&alpn=http/1.1&path=${
            encodeURIComponent(/${getRandomPath(16)}${proxyIP ? /${btoa(proxyIP)} : ''}?ed=2560)
        }#${encodeURIComponent(remark)}\n`;
    });
```

که بعد از حذفیات و آماده شدنش برای پورت 80 شد این:
```js
vlessWsTls += 'vless' + `://${userID}@${addr}:80?encryption=none&security=none&type=ws&host=${
            randomUpperCase(hostName)
        }&path=${
            encodeURIComponent(/${getRandomPath(16)}${proxyIP ? /${btoa(proxyIP)} : ''}?ed=2560)
        }#${encodeURIComponent(remark)}\n`;
    });
```
 پیشفرش پورت 80 نوشته شده ولی از بقیه پورت های no tls کلادفلر هم میشه استفاده کرد 
> 80-8080-8880-2052-2082-2086-2095

دلیل اینکار این بود که خیلی از اینترنت ها طی چندروز اخیر به هیچ‌وجه با tls ارتباط برقرار نمیکنن و handshake رخ نمیده
این مشکل تا حدودی با اینکار برطرف میشه.



> [!NOTE]
> - همونطور که همه میدونین تو خود پروتکل وب‌سوکت رمزنگاری صورت میگیره ولی با این کار دیگه رمزنگاری اضافه بر سازمان tls رو نخواهیم داشت، این به معنی ایمن نبودن کانفیگ‌ها نیست، ب معنی ایمن بودن و رمزنگاری نسبتا ضعیفتر نسبت به کانفیگ‌های با TLS
پس مسئولیت هر رخداد فضایی با خودتون 🤍🤚🏿
> - فراموش نکنید که استفاده از پورت های بدون tls فقط با وورکر امکان پذیر هست روی pages اصلا ممکن نیست
> نکته بعدی اینه که ترجیحا یه اکانت کلادفلر جدید بسازید و وورکر روی اون ایجاد کنید، بازم فراموش نکنید وورکر محدودیت تعداد رکوئست 100 هزار روزانه داره، واسه استفاده پنج شیش نفر با دانلود سنگین کافیه، اگه کاربر بیشتر باشه باید یه دامین بخرید و اضافه کنید به اکانت تا محدودیت اعمال نشه.


راحتتره که فایل [_worker.js](https://github.com/NiREvil/bia-pain-bache/blob/noTLS/_worker.js) رو باز کرده و کپی پست بکنید توی وورکر، وگرنه با دکمه زیر هم میشه انجامش داد ولی با سلسله مراتب 😂

[![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/NiREvil/bia-pain-bache/tree/noTLS)  






----












> [!NOTE]
> BPB Panel v2.3.5
![image](https://github.com/NiREvil/bia-pain-bache/assets/126243832/c0c3e224-936f-4735-8799-d6ea09aff94b)
![image](https://github.com/NiREvil/bia-pain-bache/assets/126243832/210ccdee-e0fa-42ad-bba5-0a74f0efc93e)



### [🇮🇷Persian](README-fa.md)-[🇬🇧English](README.md)


## Introduction
This project is dedicated to developing a user panel for the [Cloudflare-workers/pages proxy script](https://github.com/yonggekkk/Cloudflare-workers-pages-vless) created by [yonggekkk](https://github.com/yonggekkk).

HUGE THANKS TO
[bia pain bache](https://github.com/bia-pain-bache) for creating these amazing panel

----

 The panel offers two deployment options:
- **Worker** deployment
- **Pages** deployment
<br>


## Features

1. **Free**: No cost involved.
2. **User-Friendly Panel:** Designed for easy navigation, configuration and usage.
3. **Support Fragment:** Provides support for fragment functionality.
4. **Block Ads. and Porn (Optional)**
5. **Bypass Iran and LAN (Optional)**
6. **Full routing rules:** Bypassing Iran, Blocking Ads, Malwares, Phishing... for Sing-box.
7. **Chain Proxy:** Capable of adding a chain proxy to fix IP.
8. **Supports Wide Range of Clients:** Offers subscription links for Xray and Sing-box core clients.
9. **Subscription Link (JSON):** Provides subscription link for JSON configs.
10. **Password-Protected Panel:** Secure your panel with password protection.
11. **Custom Cloudflare Clean IP:** Ability to use online scanner and setting up clean IP-domains.
<br>

## How to use:
- [Installation (Pages)](docs/pages_installation_fa.md)

- [Installation (Worker)](docs/worker_installation_fa.md)

- [How to use](docs/configuration_fa.md)

- [FAQ](docs/faq.md)
<br>

## Supported Clients
| Client  | Version | Fragment |
| :-------------: | :-------------: | :-------------: |
| **v2rayNG**  | 1.8.19 or higher  | :heavy_check_mark: |
| **v2rayN**  | 6.42 or higher  | :heavy_check_mark: |
| **Nekobox**  |   | :x: |
| **Sing-box**  | 1.8.10 or higher  | :x: |
| **Streisand**  |   | :heavy_check_mark: |
| **V2Box**  |   | :x: |
| **Shadowrocket**  |   | :x: |
| **Nekoray**  |   | :heavy_check_mark: |
| **Hiddify**  |   | :x: |


---

## Stargazers Over Time
[![Stargazers Over Time](https://starchart.cc/bia-pain-bache/BPB-Worker-Panel.svg?variant=adaptive)](https://starchart.cc/bia-pain-bache/BPB-Worker-Panel)

---

### Special Thanks
- CF-vless code author [3Kmfi6HP](https://github.com/3Kmfi6HP/EDtunnel)
- CF preferred IP program author [badafans](https://github.com/badafans/Cloudflare-IP-SpeedTest), [XIU2](https://github.com/XIU2/CloudflareSpeedTest)

---

For a detailed tutorial on the core script, please refer to [Yongge’s blog and video tutorials](https://ygkkk.blogspot.com/2023/07/cfworkers-vless.html).
