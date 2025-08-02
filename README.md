# 🎨 База данни за оцветители на пластмаса и полимери

![Pantone](https://upload.wikimedia.org/wikipedia/commons/2/28/Pantone_logo.svg)
![RAL](https://upload.wikimedia.org/wikipedia/commons/thumb/1/1a/RAL_Colours_logo.svg/320px-RAL_Colours_logo.svg.png)

> 💡 Професионална база данни със структурирана информация за индустриални цветови системи — **Pantone** и **RAL**, представени в RGB, LAB и спектрален формат.

---

## 📌 Какво съдържа базата данни?

Тази база данни в SQLite формат обединява цветова информация от различни стандарти, подходяща за:

- 👨‍🎨 Графични и индустриални дизайнери  
- 🏭 Производствени процеси с контрол на цвета  
- 🧠 Машинно обучение и визуални алгоритми  
- 🖥️ Софтуер за съвпадение, поддръжка и препоръки на цветове  

---

## 🗂️ Таблици в базата данни

| Таблица                    | Съдържание                                                            |
|----------------------------|-----------------------------------------------------------------------|
| `PANTONE`                  | Основни Pantone цветове с RGB и LAB стойности                        |
| `Pantone_Coated`, `LAB`    | Вариации с LAB и покритие                                            |
| `Pantone_Solid_Coated`     | Спектрални данни за покрити Pantone цветове                         |
| `Pantone_Solid_Uncoated`   | Спектрални данни за непокрити Pantone цветове                       |
| `RAL_Design`               | Цветове от серията RAL Design с цветови компоненти и характеристики |
| `RAL_Klasic`               | Класическа RAL палитра с кодове и RGB стойности                     |

---

## 🧪 Примерни стойности

```text
| PANTONENAME | RED | GREEN | BLUE | L   | A   | B   |
|-------------|-----|--------|------|-----|-----|-----|
| PANTONE 485 | 218 |  41   |  28  | 45  | 61  | 45  |
| PANTONE 300 |  0  | 114   | 206  | 53  | 12  | -49 |
````

```text
| RALCODE | RALNAME     | RED | GREEN | BLUE | L   | A   | B   |
|---------|-------------|-----|--------|------|-----|-----|-----|
| 3020    | Traffic Red | 204 |  6    | 5    | 45  | 70  | 50  |
```

---

## 🛠️ Пример за използване с Python

```python
import sqlite3

conn = sqlite3.connect("Plastic Colorant Database.db")
cursor = conn.cursor()

# Пример: Извличане на всички червени тонове от Pantone
cursor.execute("SELECT PANTONENAME, RED, GREEN, BLUE FROM PANTONE WHERE RED > 200;")
results = cursor.fetchall()

for row in results:
    print(row)

conn.close()
```

---

## 🌈 Визуализация

Можете да използвате RGB стойностите за генериране на реални цветови мостри:

```html
<div style="background-color: rgb(218,41,28); width: 100px; height: 30px;">PANTONE 485</div>
<div style="background-color: rgb(0,114,206); width: 100px; height: 30px;">PANTONE 300</div>
<table>
  <tr>
    <td style="background-color: rgb(218,41,28); width: 120px; height: 40px; text-align: center; color: white;">PANTONE 485</td>
    <td style="background-color: rgb(0,114,206); width: 120px; height: 40px; text-align: center; color: white;">PANTONE 300</td>
    <td style="background-color: rgb(204,6,5); width: 120px; height: 40px; text-align: center; color: white;">RAL 3020</td>
    <td style="background-color: rgb(255,94,0); width: 120px; height: 40px; text-align: center;">RAL 2008</td>
    <td style="background-color: rgb(0,161,228); width: 120px; height: 40px; text-align: center;">RAL 5015</td>
    <td style="background-color: rgb(87,166,57); width: 120px; height: 40px; text-align: center;">RAL 6018</td>
  </tr>
</table>

```

---

## 📎 Връзки и ресурси

* 🔗 [Официален сайт на Pantone](https://www.pantone.com/)
* 🔗 [RAL цветова система](https://www.ralcolor.com/)
* ℹ️ [CIELAB в Уикипедия](https://bg.wikipedia.org/wiki/CIELAB)

---

## 📄 Лиценз

Този проект е предоставен за образователни и изследователски цели. Ако имате нужда от файла за търговска употреба на цветовата BD и стандарти, моля, консултирайте се със създателя на BD. **Ако има неправомерна комерсиална употреба ще бъде засечена!!!**

---

```

📌 **Как да го използваш:**  
1. Копирай текста по-горе.  
2. Създай файл с име `README.md` в твоя проект.  
3. Постави съдържанието вътре и запази.  

