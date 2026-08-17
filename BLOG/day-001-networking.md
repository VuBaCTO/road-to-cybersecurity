# 🛡️ Day 001 — Networking Fundamentals

## 🇦🇿 Azərbaycan

Bu gün kibertəhlükəsizlik yolunda ilk dərsimə başladım.

Mövzumuz **networking** idi. Açığı, IP, TCP, UDP, DNS kimi sözləri əvvəllər də görmüşdüm, amma hamısının bir-biri ilə necə əlaqəli olduğunu tam başa düşmürdüm.

Ona görə bu gün nəzəriyyədən çox praktikaya keçdim.

Windows-da bir neçə maraqlı komanda yoxladım:

* `ipconfig`
* `nslookup`
* `ping`
* `netstat -ano`

Məsələn, `ipconfig` ilə kompüterimin şəbəkədəki IP ünvanını gördüm.

`nslookup google.com` yazanda isə maraqlı bir şey baş verdi: kompüter DNS vasitəsilə `google.com` üçün IP ünvanını tapdı.

`ping` ilə Google-a sorğu göndərdim və cavabın neçə millisanəyə gəldiyini gördüm.

Amma ən maraqlısı **`netstat -ano`** oldu.

Bu komanda mənə kompüterimin hansı IP-lərlə və hansı portlarla əlaqə saxladığını göstərdi.

Məsələn:

```text
192.168.0.198:49840 → 3.208.102.59:443
```

Əvvəlcə bu mənə qarışıq göründü. Sonra başa düşdüm:

**Mənim kompüterim → mənim portum → uzaqdakı server → onun portu.**

`443` isə adətən HTTPS üçün istifadə olunur.

Daha maraqlısı odur ki, `netstat` həmin bağlantının **PID**-ini də göstərir. PID vasitəsilə həmin bağlantıdan hansı prosesin istifadə etdiyini tapmaq mümkündür.

Məsələn:

```cmd
tasklist /FI "PID eq 6808"
```

Burada artıq networking ilə proseslər bir-birinə bağlanır.

Və bu məqam mənə cybersecurity-nin niyə maraqlı olduğunu bir daha göstərdi.

Məsələn, kompüterdə şübhəli bir proses xarici IP-lərlə davamlı əlaqə yaradırsa, `netstat` ilkin araşdırma üçün çox faydalı ola bilər.

Əlbəttə, naməlum IP görmək avtomatik olaraq "virus tapdım" demək deyil. 😄 Sadəcə araşdırmağa dəyər bir siqnaldır.

### TCP vs UDP

Bu gün TCP və UDP-ni də təkrarladım.

Sadə desək:

**TCP:**
"Göndərdim → çatdın? → yox? Bir də göndərim."

**UDP:**
"Al, məlumat budur. Çatdısa yaxşı, çatmadısa həyat davam edir." 😂

TCP etibarlılığa, UDP isə daha çox sürət və aşağı gecikməyə üstünlük verir.

Buna görə real vaxtlı oyunlar, səsli əlaqə və bəzi yayım sistemlərində UDP çox istifadə olunur.

### Bu gün nə öyrəndim?

Ən vacibi odur ki, artıq networking mənə sadəcə əzbərlənəcək terminlər kimi görünmür.

Artıq bunu belə təsəvvür edə bilirəm:

**IP → Port → Connection → Process**

Bu hələ başlanğıcdır.

**Day 001 tamamlandı. 🛡️**

---

## 🇬🇧 English

Today I started my first cybersecurity lesson.

The topic was **networking**.

I had already seen terms like IP, TCP, UDP and DNS before, but I didn't really understand how they all connected to each other.

So instead of only reading theory, I decided to actually play around with my own Windows system.

I used:

* `ipconfig`
* `nslookup`
* `ping`
* `netstat -ano`

The most interesting one was definitely `netstat`.

It showed me which IP addresses and ports my computer was communicating with.

For example:

```text
192.168.0.198:49840 → 3.208.102.59:443
```

At first this looked like complete nonsense.

Then it clicked:

**My computer → my port → remote server → its port.**

Port `443` is commonly used for HTTPS.

Even more interestingly, `netstat` can show the **PID** of the process using a connection.

I can then use that PID to find the actual process:

```cmd
tasklist /FI "PID eq 6808"
```

That means I can go from:

**Network connection → PID → Process**

And that's where networking starts becoming really interesting from a cybersecurity perspective.

I also reviewed TCP vs UDP.

In simple terms:

**TCP:**
"I sent it. Did you get it? No? I'll send it again."

**UDP:**
"Here's the data. Hopefully you got it." 😂

TCP focuses more on reliability, while UDP is useful when speed and low latency matter more.

### Today's takeaway

Networking is starting to make more sense to me now.

Instead of seeing random technical terms, I can start thinking:

**IP → Port → Connection → Process**

And this is only Day 001.

**Day 001 complete. 🛡️**
