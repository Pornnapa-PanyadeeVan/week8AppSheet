# Step1 : Google Sheet Structure

ระบบใช้ Google Sheets จำนวน 4 Sheet

```text
Tables
Menu
Orders
Order_Details
```

## 1. Sheet: `Tables`

| Column        | Description                     | Example |
| ------------- | ------------------------------- | ------- |
| `Table_ID`    | รหัสโต๊ะ                        | T01     |
| `Table_Name`  | ชื่อโต๊ะ                        | โต๊ะ 1  |
| `Capacity`    | จำนวนที่นั่ง                    | 4       |
| `Table_Status` | สถานะโต๊ะ 0 = ว่าง, 1 = ไม่ว่าง | 0       |

ตัวอย่างข้อมูล

| Table_ID | Table_Name | Capacity | Table_Status |
| -------- | ---------- | -------: | ----------: |
| T01      | โต๊ะ 1     |        4 |           0 |
| T02      | โต๊ะ 2     |        4 |           0 |
| T03      | โต๊ะ 3     |        6 |           0 |
| T04      | โต๊ะ 4     |        2 |           0 |

---

## 2. Sheet: `Menu`

| Column         | Description   | Example     |
| -------------- | ------------- | ----------- |
| `Menu_ID`      | รหัสเมนู      | M001        |
| `Name_th`    | ชื่อเมนูไทย      | ข้าวซอยไก่  |
| `Name_en`    | ชื่อเมนูอังกฤษ      | Khao Soi Chicken  |
| `Category`     | ประเภทเมนู    | Food        |
| `Price`        | ราคา          | 55          |
| `Is_Active` | สถานะพร้อมขาย 0 = ไม่พร้อม, 1 = พร้อม | 1        |
| `Image`        | รูปภาพเมนู    | menu001.jpg |

ตัวอย่างข้อมูล

| Menu_ID | Menu_Name    | Category | Price | Is_Available | Image |
| ------- | ------------ | -------- | ----: | ------------ | ----- |
| M001    | ข้าวซอยไก่   | Food     |    55 | 1         |       |
| M002    | ข้าวซอยเนื้อ | Food     |    65 | 1      |       |
| M003    | ข้าวซอยเจ    | Food     |    55 | 1        |       |
| M004    | ชาเย็น       | Drink    |    25 | 1       |       |

---

## 3. Sheet: `Orders`

| Column           | Description       | Example          |
| ---------------- | ----------------- | ---------------- |
| `Order_ID`       | รหัส Order        | ORD001           |
| `Order_DateTime` | วันที่และเวลาสั่ง | 31/08/2026 18:30 |
| `Table_ID`       | รหัสโต๊ะ          | T01              |
| `Order_Status`   | สถานะ Order       | NEW              |
| `Total_Amount`   | ยอดรวม Order      | 135              |
| `Paid_DateTime`   | วันที่และเวลาจ่ายเงิน      | 31/08/2026 19:30 |

ตัวอย่างข้อมูล

| Order_ID | Order_DateTime   | Table_ID | Order_Status | Total_Amount | Total_Amount |
| -------- | ---------------- | -------- | ------------ | -----------: | -----------: |
| ORD001   | 31/08/2026 18:30 | T01      | NEW          |          135 |              |

สถานะ Order ที่ใช้

```text
NEW
COOKING
READY
SERVED
```

---

## 4. Sheet: `Order_Details`

| Column       | Description   | Example   |
| ------------ | ------------- | --------- |
| `Detail_ID`  | รหัสรายการ    | D001      |
| `Order_ID`   | รหัส Order    | ORD001    |
| `Menu_ID`    | รหัสเมนู      | M001      |
| `Quantity`   | จำนวน         | 2         |
| `Unit_Price` | ราคาต่อหน่วย  | 55        |
| `Total    ` | ราคารวมรายการ | 110       |
| `Note`       | หมายเหตุ      | ไม่ใส่หอม |

ตัวอย่างข้อมูล

| Detail_ID | Order_ID | Menu_ID | Quantity | Unit_Price |    Total   | Note     |
| --------- | -------- | ------- | -------: | ---------: | ---------: | -------- |
| D001      | ORD001   | M001    |        2 |         55 |        110 |          |
| D002      | ORD001   | M004    |        1 |         25 |         25 | หวานน้อย |

---

## Google Sheet Structure

```text
Google Sheets
│
├── Tables
│   ├── Table_ID
│   ├── Table_Name
│   ├── Capacity
│   └── Is_Occupied
│
├── Menu
│   ├── Menu_ID
│   ├── Menu_Name
│   ├── Category
│   ├── Price
│   ├── Is_Available
│   └── Image
│
├── Orders
│   ├── Order_ID
│   ├── Order_DateTime
│   ├── Table_ID
│   ├── Order_Status
│   └── Total_Amount
│
└── Order_Details
    ├── Detail_ID
    ├── Order_ID
    ├── Menu_ID
    ├── Quantity
    ├── Unit_Price
    ├── Line_Total
    └── Note
```
