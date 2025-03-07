# ใบงานการทดลอง: พื้นฐานการจัดการรูปแบบเว็บไซต์ด้วย CSS
[](#การทดลองที่-1-ทำความรู้จักกับ-css)
## การทดลองที่ 1: ทำความรู้จักกับ CSS

### 1.1 วิธีการใช้งาน CSS
CSS สามารถใช้งานได้ 3 วิธี:

1. **Inline CSS**:
```html
<p style="color: blue; font-size: 16px;">ข้อความสีน้ำเงิน</p>
```

2. **Internal CSS**:
```html
<head>
    <style>
        p {
            color: blue;
            font-size: 16px;
        }
    </style>
</head>
```

3. **External CSS**:
```html
<head>
    <link rel="stylesheet" href="style.css">
</head>
```

### ตัวอย่างการใช้งาน: การสร้างปุ่มสไตล์ต่างๆ

```html
<!-- ไฟล์ index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>ตัวอย่างปุ่ม CSS</title>
    <!-- Internal CSS -->
    <style>
        .btn-primary {
            background-color: #007bff;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
    <!-- External CSS -->
    <link rel="stylesheet" href="css/buttons.css">
</head>
<body>
    <!-- Inline CSS -->
    <button style="background-color: #dc3545; color: white; padding: 10px 20px;">ปุ่มแบบ Inline</button>
    
    <!-- Internal CSS -->
    <button class="btn-primary">ปุ่มแบบ Internal</button>
    
    <!-- External CSS -->
    <button class="btn-success">ปุ่มแบบ External</button>
</body>
</html>
```

```css
/* สร้างไฟล์ buttons.css ในโฟลเดอร์ css */
.btn-success {
    background-color: #28a745;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}
```
[](#การทดลองที่-2-selectors-ใน-CSS)
## การทดลองที่ 2: Selectors ใน CSS
CSS Selector คือวิธีการระบุหรือเลือกองค์ประกอบ (elements) ที่เราต้องการจัดรูปแบบใน HTML โดยมีประเภทหลัก ๆ ดังนี้:

1. **Element Selector** - เลือกโดยใช้ชื่อ element
```css
p { color: red; }  /* เลือกทุก <p> elements */
h1 { color: blue; }  /* เลือกทุก <h1> elements */
```

2. **Class Selector** - เลือกโดยใช้ชื่อ class (ขึ้นต้นด้วย .)
```css
.menu { color: green; }  /* เลือก elements ที่มี class="menu" */
.highlight { background: yellow; }
```

3. **ID Selector** - เลือกโดยใช้ ID (ขึ้นต้นด้วย #)
```css
#header { background: black; }  /* เลือก element ที่มี id="header" */
#logo { width: 100px; }
```

4. **Descendant Selector** - เลือก elements ที่เป็นลูกหลาน
```css
div p { color: blue; }  /* เลือก <p> ที่อยู่ภายใน <div> */
```

5. **Child Selector** - เลือก elements ที่เป็นลูกโดยตรง (>)
```css
div > p { color: red; }  /* เลือก <p> ที่เป็นลูกโดยตรงของ <div> */
```

6. **Pseudo-class** - เลือกสถานะพิเศษ
```css
a:hover { color: red; }  /* เมื่อเมาส์ชี้ */
input:focus { border: blue; }  /* เมื่อได้รับการโฟกัส */
```

7. **Multiple Selector** - เลือกหลายอย่างพร้อมกัน
```css
h1, h2, h3 { color: purple; }
```

8. **Universal Selector** - เลือกทุก elements (*)
```css
* { margin: 0; padding: 0; }
```

9. **Attribute Selector** - เลือกตาม attribute
```css
input[type="text"] { border: 1px solid gray; }
```

10. **Adjacent Sibling Selector** - เลือกธาตุที่อยู่ถัดไป (+)
```css
h1 + p { margin-top: 20px; }
```

ความสำคัญของ Selector:
- ช่วยให้เราสามารถกำหนดสไตล์ให้กับ elements ที่ต้องการได้อย่างเฉพาะเจาะจง
- ช่วยในการจัดการและบำรุงรักษาโค้ด CSS
- ทำให้สามารถสร้างรูปแบบที่ซับซ้อนได้
- ช่วยลดการเขียนโค้ดซ้ำซ้อน
  
### 2.1 ประเภทของ Selectors
```css
/* Element Selector */
p {
    color: blue;
}

/* Class Selector */
.highlight {
    background-color: yellow;
}

/* ID Selector */
#header {
    font-size: 24px;
}

/* Descendant Selector */
div p {
    margin: 10px;
}

/* Child Selector */
div > p {
    padding: 5px;
}
```

### ตัวอย่างการใช้งาน: การสร้างเมนูนำทาง

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        /* การใช้ Element Selector */
        nav {
            background-color: #333;
            padding: 15px;
        }

        /* การใช้ Descendant Selector */
        nav ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
        }

        /* การใช้ Child Selector */
        nav > ul > li {
            margin: 0 10px;
        }

        /* การใช้ Class Selector */
        .menu-item {
            color: white;
            text-decoration: none;
            padding: 5px 10px;
        }

        /* การใช้ Pseudo-class */
        .menu-item:hover {
            background-color: #555;
            border-radius: 3px;
        }

        /* การใช้ ID Selector */
        #active {
            background-color: #007bff;
            border-radius: 3px;
        }
    </style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#" class="menu-item" id="active">หน้าแรก</a></li>
            <li><a href="#" class="menu-item">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>
</body>
</html>
```
### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. แก้ไขให้เมนูถูกเลือกที่ สินค้า
3. เปลี่ยนสีพื้นหลังของเมนู

### ผลการทดลอง
---
โค้ด html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Books</title>

    <!-- css -->
    <link rel="stylesheet" href="../../basic_css/style1.css">
</head>
<body>
    <nav id="nav">
        <img src="./images/logo.jpg" alt="logo" class="logo">
        <a href="index.html" class="button">Home</a>
        <a href="pages/about.html" class="button">About</a>
        <a href="pages/contact.html" class="button">Contact Us</a>
    </nav>
    <h1>Gallery</h1>
    <section>
        <figure>
            <a href="images/gallery/product1.png">
                <img src="images/gallery/product1.png" alt="product1" width="200"> 
            </a>
            <figcaption>
                <p>
                    <strong>TITLE:</strong>
                    DIANA & JACK
                </p>
                <p>
                    <strong>AUTHOR:</strong>
                    taipa sipipong
                </p>
                <p>
                    <strong>PUBLISHER:</strong>
                    Panya Thai
                </p>
                <p>
                    <strong>CATEGORY:</strong>
                    Fantasy
                </p>
                <p>
                    <strong>PRICE:</strong>
                    $12.99 / 420 THB
                </p>
            </figcaption>
        </figure>
        <figure>
            <a href="images/gallery/product2.png">
                <img src="images/gallery/product2.png" alt="product1" width="200"> 
            </a>
            <figcaption>
                <p>
                    <strong>TITLE:</strong>
                    CHRISTMAS
                </p>
                <p>
                    <strong>AUTHOR:</strong>
                    Prachya Aksaranon
                </p>
                <p>
                    <strong>PUBLISHER:</strong>
                    Navatras Publishing
                </p>
                <p>
                    <strong>CATEGORY:</strong>
                    CLASSICS
                </p>
                <p>
                    <strong>PRICE:</strong>
                    $12.99 / 420 THB
                </p>
            </figcaption>
        </figure>
        <figure>
            <a href="images/gallery/product3.png">
                <img src="images/gallery/product3.png" alt="product1" width="200"> 
            </a>
            <figcaption>
                <p>
                    <strong>TITLE:</strong>
                    TERE & TONY
                </p>
                <p>
                    <strong>AUTHOR:</strong>
                    Waranya Sirisuk
                </p>
                <p>
                    <strong>PUBLISHER:</strong>
                    Withee Books
                </p>
                <p>
                    <strong>CATEGORY:</strong>
                    FANTASY
                </p>
                <p>
                    <strong>PRICE:</strong>
                    $12.99 / 420 THB
                </p>
            </figcaption>
        </figure>
        <figure>
            <a href="images/gallery/product4.png">
                <img src="images/gallery/product4.png" alt="product1" width="200"> 
            </a>
            <figcaption>
                <p>
                    <strong>TITLE:</strong>
                    CELTIC TALES
                </p>
                <p>
                    <strong>AUTHOR:</strong>
                    Anawin Pipattanakit
                </p>
                <p>
                    <strong>PUBLISHER:</strong>
                    Sangdao Publishing
                </p>
                <p>
                    <strong>CATEGORY:</strong>
                    SPIRITUALITY & MINDFULNESS
                </p>
                <p>
                    <strong>PRICE:</strong>
                    $12.99 / 420 THB
                </p>
            </figcaption>
        </figure>
        <figure>
            <a href="images/gallery/product5.png">
                <img src="images/gallery/product5.png" alt="product1" width="200"> 
            </a>
            <figcaption>
                <p>
                    <strong>TITLE:</strong>
                    THE LORD OF THE KINGS
                </p>
                <p>
                    <strong>AUTHOR:</strong>
                    Pitchada Wattanakiet
                </p>
                <p>
                    <strong>PUBLISHER:</strong>
                    Jintasill Publishing
                </p>
                <p>
                    <strong>CATEGORY:</strong>
                    FANTASY
                </p>
                <p>
                    <strong>PRICE:</strong>
                    $12.99 / 420 THB
                </p>
            </figcaption>
        </figure>
        <figure>
            <a href="images/gallery/product6.png">
                <img src="images/gallery/product6.png" alt="product1" width="200"> 
            </a>
            <figcaption>
                <p>
                    <strong>TITLE:</strong>
                    SIMPLE & MINIMALIST
                </p>
                <p>
                    <strong>AUTHOR:</strong>
                    Nakarin Kulpiya
                </p>
                <p>
                    <strong>PUBLISHER:</strong>
                    Dandin Books
                </p>
                <p>
                    <strong>CATEGORY:</strong>
                    SELF-HELP
                </p>
                <p>
                    <strong>PRICE:</strong>
                    $12.99 / 420 THB
                </p>
            </figcaption>
        </figure>
        <figure>
            <a href="images/gallery/product7.png">
                <img src="images/gallery/product7.png" alt="product1" width="200"> 
            </a>
            <figcaption>
                <p>
                    <strong>TITLE:</strong>
                    MUTED COLOR POSTER
                </p>
                <p>
                    <strong>AUTHOR:</strong>
                    Supakorn Arayatham
                </p>
                <p>
                    <strong>PUBLISHER:</strong>
                    Montra Publishing
                </p>
                <p>
                    <strong>CATEGORY:</strong>
                    NON-FICTION
                </p>
                <p>
                    <strong>PRICE:</strong>
                    $12.99 / 420 THB
                </p>
            </figcaption>
        </figure>
        <figure>
            <a href="images/gallery/product8.png">
                <img src="images/gallery/product8.png" alt="product1" width="200"> 
            </a>
            <figcaption>
                <p>
                    <strong>TITLE:</strong>
                    MODERN ABSTRACT
                </p>
                <p>
                    <strong>AUTHOR:</strong>
                    Charuwan Rattanasombat
                </p>
                <p>
                    <strong>PUBLISHER:</strong>
                    Aruntat Publishing
                </p>
                <p>
                    <strong>CATEGORY:</strong>
                    BUSINESS & MINDFULNESS
                </p>
                <p>
                    <strong>PRICE:</strong>
                    $12.99 / 420 THB
                </p>
            </figcaption>
        </figure>
    </section>
    
    <a href="#nav" class="button">กลับด้านบน</a>
</body>
</html>
```
โค้ด css
```css
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');

:root {
    --color-1: linear-gradient(to right, #e01249, #c81e84, #7c26f5); 
    --roboto-font: "Roboto", serif;
    --montserrat-font: "Montserrat", serif;
}

* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

nav {
    display: flex;
    background: var(--color-1);
    height: 80px;
    font-family: var(--montserrat-font);
    font-weight: 600;
    position: sticky;
    top: 0;
}

nav .logo {
    border-radius: 9999px;
    padding: 15px;
    margin-left: 30px;
    width: 80px;
    height: 80px;
}

nav .button {
    text-decoration: none;
    font-size: 24px;
    margin: 10px 20px;
    padding: 15px;
    color: white;
}

nav .button:hover {
    border-radius: 9999px;
    padding: 15px;
    background: white;
    color: #e01249;
    cursor: pointer;
    transition: .3s;
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
gif
![css_lab1_1](https://github.com/user-attachments/assets/2c260cef-e6b9-4326-bec9-95411ad4c1f9)

---

[](#การทดลองที่-3-การจัดการสีและพื้นหลัง)
## การทดลองที่ 3: การจัดการสีและพื้นหลัง

### 3.1 การกำหนดสีและพื้นหลัง
```css
/* สีพื้นฐาน */
color: red;
color: #FF0000;
color: rgb(255, 0, 0);
color: rgba(255, 0, 0, 0.5);

/* พื้นหลัง */
background-color: #f0f0f0;
background-image: url('image.jpg');
background-size: cover;
```

### ตัวอย่างการใช้งาน: การสร้างการ์ดสินค้า

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .product-card {
            width: 300px;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            background-color: white;
        }

        .product-image {
            width: 100%;
            height: 200px;
            background-image: url('product.jpg');
            background-size: cover;
            background-position: center;
        }

        .product-info {
            padding: 15px;
        }

        .product-title {
            color: #333;
            font-size: 18px;
            margin-bottom: 10px;
        }

        .product-price {
            color: #007bff;
            font-size: 24px;
            font-weight: bold;
        }

        .product-description {
            color: #666;
            font-size: 14px;
            line-height: 1.5;
        }

        .product-button {
            display: block;
            background: linear-gradient(to right, #007bff, #0056b3);
            color: white;
            text-align: center;
            padding: 10px;
            text-decoration: none;
            margin-top: 15px;
            border-radius: 4px;
        }

        .product-button:hover {
            background: linear-gradient(to right, #0056b3, #003980);
        }
    </style>
</head>
<body>
    <div class="product-card">
        <div class="product-image"></div>
        <div class="product-info">
            <h2 class="product-title">สินค้าตัวอย่าง</h2>
            <p class="product-price">฿1,999</p>
            <p class="product-description">
                รายละเอียดสินค้าตัวอย่าง ที่มีความน่าสนใจและน่าใช้งาน
            </p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. แก้ไขให้แสดงรูปสินค้า โดยให้รูปสินค้าเก็บอยู่ในโฟลเดอร์ images
3. เพิ่มเติมให้มี card แสดงข้อมูลสินค้า 4 รูป

### ผลการทดลอง
โค้ด html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Books</title>

    <!-- css -->
    <link rel="stylesheet" href="../../basic_css/style1.css">
</head>
<body>
    <div id="top"/>
    <!-- nav -->
    <nav>
        <img src="./images/logo.jpg" alt="logo" class="logo">
        <a href="index.html" class="button">Home</a>
        <a href="pages/about.html" class="button">About</a>
        <a href="pages/contact.html" class="button">Contact Us</a>
    </nav>
    <!-- hero -->
    <section class="hero">
        <div class="hero">
            <h1 class="title">Gallery</h1>
            <p class="subtitle">Books broaden perspectives and enhance knowledge in various fields.</p>
        </div>
    </section>
    <hr>
    <!-- main -->
    <main>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product1.png">
                        <img src="images/gallery/product1.png" alt="product1" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE:</strong>
                        DIANA & JACK
                    </p>
                    <p>
                        <strong>AUTHOR:</strong>
                        taipa sipipong
                    </p>
                    <p>
                        <strong>PUBLISHER:</strong>
                        Panya Thai
                    </p>
                    <p>
                        <strong>CATEGORY:</strong>
                        Fantasy
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="button">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart">
                        <h3>Shop</h3>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product2.png">
                        <img src="images/gallery/product2.png" alt="product2" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE:</strong>
                        CHRISTMAS
                    </p>
                    <p>
                        <strong>AUTHOR:</strong>
                        Prachya Aksaranon
                    </p>
                    <p>
                        <strong>PUBLISHER:</strong>
                        Navatras Publishing
                    </p>
                    <p>
                        <strong>CATEGORY:</strong>
                        CLASSICS
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="button">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart">
                        <h3>Shop</h3>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product3.png">
                        <img src="images/gallery/product3.png" alt="product3" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE:</strong>
                        TERE & TONY
                    </p>
                    <p>
                        <strong>AUTHOR:</strong>
                        Waranya Sirisuk
                    </p>
                    <p>
                        <strong>PUBLISHER:</strong>
                        Withee Books
                    </p>
                    <p>
                        <strong>CATEGORY:</strong>
                        FANTASY
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="button">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart">
                        <h3>Shop</h3>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product4.png">
                        <img src="images/gallery/product4.png" alt="product4" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE:</strong>
                        CELTIC TALES
                    </p>
                    <p>
                        <strong>AUTHOR:</strong>
                        Anawin Pipattanakit
                    </p>
                    <p>
                        <strong>PUBLISHER:</strong>
                        Sangdao Publishing
                    </p>
                    <p>
                        <strong>CATEGORY:</strong>
                        SPIRITUALITY & MINDFULNESS
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="button">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart">
                        <h3>Shop</h3>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product5.png">
                        <img src="images/gallery/product5.png" alt="product5" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE:</strong>
                        THE LORD OF THE KINGS
                    </p>
                    <p>
                        <strong>AUTHOR:</strong>
                        Pitchada Wattanakiet
                    </p>
                    <p>
                        <strong>PUBLISHER:</strong>
                        Jintasill Publishing
                    </p>
                    <p>
                        <strong>CATEGORY:</strong>
                        FANTASY
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="button">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart">
                        <h3>Shop</h3>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product6.png">
                        <img src="images/gallery/product6.png" alt="product6" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE:</strong>
                        SIMPLE & MINIMALIST
                    </p>
                    <p>
                        <strong>AUTHOR:</strong>
                        Nakarin Kulpiya
                    </p>
                    <p>
                        <strong>PUBLISHER:</strong>
                        Dandin Books
                    </p>
                    <p>
                        <strong>CATEGORY:</strong>
                        SELF-HELP
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="button">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart">
                        <h3>Shop</h3>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product7.png">
                        <img src="images/gallery/product7.png" alt="product7" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE:</strong>
                        MUTED COLOR POSTER
                    </p>
                    <p>
                        <strong>AUTHOR:</strong>
                        Supakorn Arayatham
                    </p>
                    <p>
                        <strong>PUBLISHER:</strong>
                        Montra Publishing
                    </p>
                    <p>
                        <strong>CATEGORY:</strong>
                        NON-FICTION
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="button">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart">
                        <h3>Shop</h3>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product8.png">
                        <img src="images/gallery/product8.png" alt="product8" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE:</strong>
                        MODERN ABSTRACT
                    </p>
                    <p>
                        <strong>AUTHOR:</strong>
                        Charuwan Rattanasombat
                    </p>
                    <p>
                        <strong>PUBLISHER:</strong>
                        Aruntat Publishing
                    </p>
                    <p>
                        <strong>CATEGORY:</strong>
                        BUSINESS & MINDFULNESS
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="button">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart">
                        <h3>Shop</h3>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
    </main>
    <!-- footer -->
    <footer>
        <div class="button">
            <a href="#top">
                <img src="images/arrow-top.png" alt="arrow-top">
            </a>
        </div>
    </footer>
</body>
</html>
```
โค้ด css
```
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');

:root {
    --color-gradient-1: linear-gradient(to right, #e01249, #c81e84, #7c26f5); 
    --color-gradient-2: linear-gradient(to right, #f52095, #ea4cff, #984fff);
    --color-gradient-3: linear-gradient(to right, #20f5d9, #4c7cff, #d455d8);
    --color-gradient-4: linear-gradient(to right, #f5e616, #20f80d, #ff4f84);
    --color-pinkish-red: #d10c41;
    --color-white: #fff;
    --color-card: #f4f4f4;
    --color-tr: #b6b6b6;
    --color-th: #7a7a7a;
    --color-shadow: #8a8a8a;
    --roboto-font: "Roboto", serif;
    --montserrat-font: "Montserrat", serif;
    --h1-size: 64px;
    --h3-size: 52px;
    --a-size: 24px;
    --p-size: 18px;
}

* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    background: var(--color-white);
    height: auto;
}

/* nav */
nav {
    display: flex;
    background: var(--color-gradient-1);
    height: 80px;
    font-family: var(--montserrat-font);
    font-weight: 600;
    position: sticky;
    top: 0;
}

nav .logo {
    border-radius: 9999px;
    padding: 15px;
    margin-left: 30px;
    width: 80px;
    height: 80px;
}

nav .button {
    text-decoration: none;
    font-size: var(--a-size);
    margin: 10px 20px;
    padding: 15px;
    color: var(--color-white);
}

nav .button:hover {
    border-radius: 9999px;
    padding: 15px;
    background: var(--color-white);
    color: var(--color-pinkish-red);
    cursor: pointer;
    transition: .4s;
}

/* section */
section .hero {
    text-align: center;
    margin-bottom: 60px;
}

section .title {
    margin: 20px 40px;
    font-family: var(--roboto-font);
    font-size: var(--h1-size);
    background: var(--color-gradient-1);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

section .subtitle {
    margin: 20px 40px;
    font-family: var(--roboto-font);
    font-size: var(--p-size);
    background: var(--color-gradient-2);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

hr {
    border: none;
    border-radius: 9999px;
    height: 6px ;
    margin-left: 70px;
    width: 90%;
    background: var(--color-gradient-3);
}

/* main */
/* card */
.card {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    border-radius: 20px;
    padding: 40px 25px;
    margin-left: 650px;
    margin-top: 60px;
    width: 260px;
    height: 360px;
    gap: 10px;
    box-shadow: 10px 10px 20px 0 var(--color-shadow);
    background: var(--color-card);
    text-align: start;
    overflow: hidden;
    cursor: pointer;
}

.card:hover {
    margin: 60px 110px;
    padding-left: 50px;
    gap: 30px;
    width: 85%;
    transition: margin-left .5s ease, width .5s ease;
}

/* card left */
.card-left .img {
    display: flex;
    margin-bottom: 30px;
    text-align: center;
}

/* card center */
.card-center .passage p {
    display: grid;
    grid-template-rows: auto;
    width: 400px;
    margin: 10px 40px;
    margin-bottom: 40px;
    padding-left: 100px;
    font-size: var(--p-size);
    gap: 10px;
}

/* card right */
.card-right {
    padding-left: 20px;
}

.card-right .button p {
    margin-top: 60px;
    margin-bottom: 40px;
    margin-left: 100px;
}

.card-right img {
    height: 40px;
    width: 40px;
}

.card-right .cart {
    display: flex;
    flex-direction: row;
    border-radius: 25px;
    height: 50px;
    width: 180px;
    padding-left: 50px;
    padding-top: 4px;
    margin-left: 70px;
    background: var(--color-blue);
    background: var(--color-gradient-3);
    color: var(--color-white);
}

.card-right .cart:hover {
    transform: scale(1.2);
    cursor: pointer;
}

.card-right .cart h3 {
    padding-top: 10px;
}

/* footer */
footer {
    text-align: end;
    position: sticky;
    bottom: 0;
    z-index: 10;
}

footer img {
    border-radius: 9999px;
    background: var(--color-card);
    box-shadow: 10px 10px 30px 0 var(--color-shadow);
    margin-bottom: 30px;
    margin-right: 30px;
    width: 60px;
    height: 60px;
}

/* scrollbar */
::-webkit-scrollbar {
    width: 8px;
}

::-webkit-scrollbar-thumb {
    background-color: var(--color-th);
    border-radius: 4px;
}

::-webkit-scrollbar-track {
    background-color: var(--color-tr);
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![css_lab2_1](https://github.com/user-attachments/assets/894f3cb5-af9c-4e28-a16e-0e0573449951)
---
[](#การทดลองที่-4-การจัดการขนาดและระยะห่าง)
## การทดลองที่ 4: การจัดการขนาดและระยะห่าง

### 4.1 หน่วยวัดและ Box Model
```css
/* หน่วยวัด */
width: 100px;
width: 50%;
font-size: 1.2rem;
height: 100vh;

/* Box Model */
padding: 10px;
margin: 15px;
border: 1px solid black;
```

### ตัวอย่างการใช้งาน: การสร้างส่วนแสดงสถิติ

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .stats-container {
            display: flex;
            justify-content: space-around;
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1rem;
        }

        .stat-box {
            flex: 1;
            margin: 0 15px;
            padding: 2rem;
            text-align: center;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: #007bff;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            font-size: 1rem;
            color: #666;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .stats-container {
                flex-direction: column;
            }

            .stat-box {
                margin: 1rem 0;
            }
        }
    </style>
</head>
<body>
    <div class="stats-container">
        <div class="stat-box">
            <div class="stat-number">1,234</div>
            <div class="stat-label">ผู้ใช้งาน</div>
        </div>
        <div class="stat-box">
            <div class="stat-number">5.6K</div>
            <div class="stat-label">ยอดขาย</div>
        </div>
        <div class="stat-box">
            <div class="stat-number">98%</div>
            <div class="stat-label">ความพึงพอใจ</div>
        </div>
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่ง ขนาดต่าง ๆ ของ Box model, ขนาดและฟอนต์ตัวหนังสือ, สี


### ผลการทดลอง
โค้ด html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Books</title>

    <!-- css -->
    <link rel="stylesheet" href="../../basic_css/style1.css">
</head>
<body>
    <div id="top"/>
    <!-- nav -->
    <nav>
        <img src="./images/logo.jpg" alt="logo" class="logo">
        <a href="index.html" class="button">Home</a>
        <a href="pages/about.html" class="button">About</a>
        <a href="pages/contact.html" class="button">Contact Us</a>
    </nav>
    <!-- hero -->
    <section class="hero">
        <div class="hero">
            <h1 class="title">Gallery</h1>
            <p class="subtitle">Books broaden perspectives and enhance knowledge in various fields.</p>
        </div>
    </section>
    <hr>
    <!-- main -->
    <main>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product1.png">
                        <img src="images/gallery/product1.png" alt="product1" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        DIANA & JACK
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Taipa Sipipong
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Panya Thai
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        Fantasy
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product2.png">
                        <img src="images/gallery/product2.png" alt="product2" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        CHRISTMAS
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Prachya Aksaranon
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Navatras Publishing
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        CLASSICS
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product3.png">
                        <img src="images/gallery/product3.png" alt="product3" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        TERE & TONY
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Waranya Sirisuk
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Withee Books
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        FANTASY
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product4.png">
                        <img src="images/gallery/product4.png" alt="product4" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        CELTIC TALES
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Anawin Pipattanakit
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Sangdao Publishing
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        SPIRITUALITY & MINDFULNESS
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product5.png">
                        <img src="images/gallery/product5.png" alt="product5" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        THE LORD OF THE KINGS
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Pitchada Wattanakiet
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Jintasill Publishing
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        FANTASY
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product6.png">
                        <img src="images/gallery/product6.png" alt="product6" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        SIMPLE & MINIMALIST
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Nakarin Kulpiya
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Dandin Books
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        SELF-HELP
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product7.png">
                        <img src="images/gallery/product7.png" alt="product7" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        MUTED COLOR POSTER
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Supakorn Arayatham
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Montra Publishing
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        NON-FICTION
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product8.png">
                        <img src="images/gallery/product8.png" alt="product8" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        MODERN ABSTRACT
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Charuwan Rattanasombat
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Aruntat Publishing
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        BUSINESS & MINDFULNESS
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
    </main>
    <!-- footer -->
    <footer>
        <div class="footer-button">
            <a href="#top">
                <img src="images/arrow-top.png" alt="arrow-top">
            </a>
        </div>
    </footer>
</body>
</html>
```
โค้ด css
```css
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');

:root {
    --color-gradient-1: linear-gradient(to right, #e01249, #c81e84, #7c26f5); 
    --color-gradient-2: linear-gradient(to right, #f52095, #ea4cff, #984fff);
    --color-gradient-3: linear-gradient(to right, #20f5d9, #4c7cff, #d455d8);
    --color-pinkish-red: #d10c41;
    --color-white: #fff;
    --color-card: #f4f4f4;
    --color-tr: #b6b6b6;
    --color-th: #7a7a7a;
    --color-shadow: #8a8a8a;
    --roboto-font: "Roboto", serif;
    --montserrat-font: "Montserrat", serif;
    --h1-size: 64px;
    --a-size: 24px;
    --p-size: 18px;
    --price-size: 40px;
}

* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    background: var(--color-white);
    height: auto;
}

/* nav */
nav {
    display: flex;
    background: var(--color-gradient-1);
    height: 80px;
    font-family: var(--montserrat-font);
    font-weight: 600;
    position: sticky;
    top: 0;
}

nav .logo {
    border-radius: 9999px;
    padding: 15px;
    margin-left: 30px;
    width: 80px;
    height: 80px;
}

nav .button {
    text-decoration: none;
    font-size: var(--a-size);
    margin: 10px 20px;
    padding: 15px;
    color: var(--color-white);
}

nav .button:hover {
    border-radius: 9999px;
    padding: 15px;
    background: var(--color-white);
    color: var(--color-pinkish-red);
    cursor: pointer;
    transition: .4s;
}

/* section */
section .hero {
    text-align: center;
    margin-bottom: 60px;
}

section .title {
    margin: 20px 40px;
    font-family: var(--roboto-font);
    font-size: var(--h1-size);
    background: var(--color-gradient-1);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

section .subtitle {
    margin: 20px 40px;
    font-family: var(--roboto-font);
    font-size: var(--p-size);
    background: var(--color-gradient-2);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

hr {
    border: none;
    border-radius: 9999px;
    height: 6px ;
    margin-left: 70px;
    width: 90%;
    background: var(--color-gradient-2);
}

/* main */
/* card */
.card {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    border-radius: 20px;
    padding: 40px 25px;
    margin-left: 650px;
    margin-top: 60px;
    width: 260px;
    height: 360px;
    gap: 10px;
    box-shadow: 10px 10px 20px 0 var(--color-shadow);
    background: var(--color-card);
    text-align: start;
    overflow: hidden;
    cursor: pointer;
}

.card:hover {
    margin: 60px 110px;
    padding-left: 50px;
    gap: 30px;
    width: 85%;
    transition: margin-left .5s ease, width .5s ease;
}

/* card left */
.card-left .img {
    display: flex;
    text-align: center;
    margin-bottom: 30px;
}

/* card center */
.card-center .passage {
    display: grid;
    grid-template-rows: auto;
    width: 500px;
    margin: 10px 40px;
    padding-left: 100px;
    font-size: var(--p-size);
    font-family: var(--roboto-font);
    gap: 10px;
}

.card-center .passage p {
    margin-bottom: 40px;
}

/* card right */
.card-right {
    font-family: var(--roboto-font);
    font-size: var(--p-size);
}

.card-right .cart p {
    margin-top: 50px;
    margin-bottom: 40px;
    margin-left: 75px;
    font-family: var(--montserrat-font);
    font-size: var(--price-size);
    font-weight: 800;
}

.card-right img {
    height: 40px;
    width: 40px;
}

.card-right .cart-button {
    display: flex;
    flex-direction: row;
    border-radius: 25px;
    height: 50px;
    width: 180px;
    padding-left: 50px;
    padding-top: 4px;
    margin-left: 70px;
    background: var(--color-blue);
    background: var(--color-gradient-3);
    color: var(--color-white);
}

.card-right .cart-button:hover {
    transform: scale(1.2);
    cursor: pointer;
}

.card-right .cart-button h2 {
    padding-top: 5px;
}

/* footer */
footer {
    text-align: end;
    position: sticky;
    bottom: 0;
    z-index: 10;
}

.footer-button img {
    border-radius: 9999px;
    background: var(--color-card);
    box-shadow: 10px 10px 30px 0 var(--color-shadow);
    margin-bottom: 30px;
    margin-right: 30px;
    width: 60px;
    height: 60px;
}

/* scrollbar */
::-webkit-scrollbar {
    width: 8px;
}

::-webkit-scrollbar-thumb {
    background-color: var(--color-th);
    border-radius: 4px;
}

::-webkit-scrollbar-track {
    background-color: var(--color-tr);
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![image](https://github.com/user-attachments/assets/33140a3c-a108-4d21-afa1-f55c764f5229)
---

[](#การทดลองที่-5-การจัดการข้อความและฟอนต์)
## การทดลองที่ 5: การจัดการข้อความและฟอนต์

### 5.1 การจัดการข้อความและฟอนต์
```css
/* การจัดการข้อความ */
text-align: center;
text-decoration: none;
text-transform: uppercase;
line-height: 1.5;

/* การจัดการฟอนต์ */
font-family: 'Arial', sans-serif;
font-size: 16px;
font-weight: bold;
```

### ตัวอย่างการใช้งาน: การสร้างบทความบล็อก

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .blog-post {
            max-width: 800px;
            margin: 2rem auto;
            padding: 0 1rem;
            font-family: 'Sarabun', sans-serif;
        }

        .post-header {
            text-align: center;
            margin-bottom: 2rem;
        }

        .post-title {
            font-size: 2.5rem;
            color: #333;
            margin-bottom: 0.5rem;
            line-height: 1.2;
        }

        .post-meta {
            color: #666;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .post-content {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #444;
        }

        .post-content p {
            margin-bottom: 1.5rem;
        }

        .post-content h2 {
            font-size: 1.8rem;
            color: #333;
            margin: 2rem 0 1rem;
        }

        blockquote {
            font-style: italic;
            border-left: 4px solid #007bff;
            margin: 1.5rem 0;
            padding-left: 1rem;
            color: #555;
        }

        @media (max-width: 768px) {
            .post-title {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <article class="blog-post">
        <header class="post-header">
            <h1 class="post-title">วิธีการเขียนบทความที่น่าสนใจ</h1>
            <div class="post-meta">โพสต์เมื่อ 1 มกราคม 2025 | โดย ผู้เขียน</div>
        </header>
        
        <div class="post-content">
            <p>เนื้อหาบทความที่ดีควรมีความน่าสนใจและเป็นประโยชน์ต่อผู้อ่าน การเขียนบทความให้น่าอ่านนั้นมีหลักการสำคัญหลายประการ</p>

            <h2>1. การเลือกหัวข้อที่น่าสนใจ</h2>
            <p>หัวข้อที่ดีควรตรงกับความสนใจของกลุ่มเป้าหมาย และมีประโยชน์ต่อผู้อ่าน</p>

            <blockquote>
                "การเขียนที่ดีไม่ได้เกิดจากพรสวรรค์เพียงอย่างเดียว แต่เกิดจากการฝึกฝนอย่างสม่ำเสมอ"
            </blockquote>

            <h2>2. การจัดโครงสร้างเนื้อหา</h2>
            <p>เนื้อหาที่ดีควรมีการจัดลำดับที่เป็นระบบ เข้าใจง่าย และมีความต่อเนื่อง</p>
        </div>
    </article>
</body>
</html>
```
### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่งรูปแบบ สีและขนาด font

### ผลการทดลอง
โค้ด html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Books</title>

    <!-- css -->
    <link rel="stylesheet" href="../../basic_css/style1.css">
</head>
<body>
    <div id="top"/>
    <!-- nav -->
    <nav>
        <img src="./images/logo.jpg" alt="logo" class="logo">
        <a href="index.html" class="button">Home</a>
        <a href="pages/about.html" class="button">About</a>
        <a href="pages/contact.html" class="button">Contact Us</a>
    </nav>
    <!-- hero -->
    <section class="hero">
        <div class="hero">
            <h1 class="title">Gallery</h1>
            <p class="subtitle">Books broaden perspectives and enhance knowledge in various fields.</p>
        </div>
    </section>
    <hr>
    <!-- main -->
    <main>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product1.png">
                        <img src="images/gallery/product1.png" alt="product1" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        DIANA & JACK
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Taipa Sipipong
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Panya Thai
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        Fantasy
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product2.png">
                        <img src="images/gallery/product2.png" alt="product2" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        CHRISTMAS
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Prachya Aksaranon
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Navatras Publishing
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        CLASSICS
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product3.png">
                        <img src="images/gallery/product3.png" alt="product3" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        TERE & TONY
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Waranya Sirisuk
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Withee Books
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        FANTASY
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product4.png">
                        <img src="images/gallery/product4.png" alt="product4" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        CELTIC TALES
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Anawin Pipattanakit
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Sangdao Publishing
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        SPIRITUALITY & MINDFULNESS
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product5.png">
                        <img src="images/gallery/product5.png" alt="product5" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        THE LORD OF THE KINGS
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Pitchada Wattanakiet
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Jintasill Publishing
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        FANTASY
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product6.png">
                        <img src="images/gallery/product6.png" alt="product6" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        SIMPLE & MINIMALIST
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Nakarin Kulpiya
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Dandin Books
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        SELF-HELP
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product7.png">
                        <img src="images/gallery/product7.png" alt="product7" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        MUTED COLOR POSTER
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Supakorn Arayatham
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Montra Publishing
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        NON-FICTION
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product8.png">
                        <img src="images/gallery/product8.png" alt="product8" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        MODERN ABSTRACT
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Charuwan Rattanasombat
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Aruntat Publishing
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        BUSINESS & MINDFULNESS
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
    </main>
    <!-- footer -->
    <footer>
        <div class="footer-button">
            <a href="#top">
                <img src="images/arrow-top.png" alt="arrow-top">
            </a>
        </div>
    </footer>
</body>
</html>
```
โค้ด css
```css
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');

:root {
    --color-gradient-1: linear-gradient(to right, #bd0032, #b6046f, #5815b6, #3d0cc4); 
    --color-gradient-2: linear-gradient(to right, #550330, #5d0768, #340774);
    --color-gradient-3: linear-gradient(to right, #20f5d9, #4c7cff, #d455d8);
    --color-gradient-4: linear-gradient(to right, #0e54a3, #d72aee);
    --color-pinkish-red: #d10c41;
    --color-white: #fff;
    --color-card: #f4f4f4;
    --color-tr: #b6b6b6;
    --color-th: #7a7a7a;
    --color-shadow: #8a8a8a;
    --roboto-font: "Roboto", serif;
    --montserrat-font: "Montserrat", serif;
    --h1-size: 64px;
    --a-size: 24px;
    --p-size: 18px;
    --price-size: 40px;
}

* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    background: var(--color-white);
    height: auto;
}

/* nav */
nav {
    display: flex;
    background: var(--color-gradient-1);
    height: 80px;
    font-family: var(--montserrat-font);
    font-weight: 600;
    position: sticky;
    top: 0;
}

nav .logo {
    border-radius: 9999px;
    padding: 15px;
    margin-left: 30px;
    width: 80px;
    height: 80px;
}

nav .button {
    text-decoration: none;
    font-size: var(--a-size);
    margin: 10px 20px;
    padding: 15px;
    color: var(--color-white);
}

nav .button:hover {
    border-radius: 9999px;
    padding: 15px;
    background: var(--color-white);
    color: var(--color-pinkish-red);
    cursor: pointer;
    transition: .4s;
}

/* section */
section .hero {
    text-align: center;
    margin-bottom: 60px;
}

section .title {
    margin: 20px 40px;
    font-family: var(--roboto-font);
    font-size: var(--h1-size);
    background: var(--color-gradient-1);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

section .subtitle {
    margin: 20px 40px;
    font-family: var(--roboto-font);
    font-size: var(--p-size);
    background: var(--color-gradient-2);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

hr {
    border: none;
    border-radius: 9999px;
    height: 6px ;
    margin-left: 70px;
    width: 90%;
    background: var(--color-gradient-3);
}

/* main */
/* card */
.card {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    border-radius: 20px;
    padding: 40px 25px;
    margin-left: 650px;
    margin-top: 60px;
    width: 260px;
    height: 360px;
    gap: 10px;
    box-shadow: 10px 10px 20px 0 var(--color-shadow);
    background: var(--color-card);
    text-align: start;
    overflow: hidden;
    cursor: pointer;
}

.card:hover {
    margin: 60px 110px;
    padding-left: 50px;
    gap: 30px;
    width: 85%;
    transition: margin-left .5s ease, width .5s ease;
}

/* card left */
.card-left .img {
    display: flex;
    text-align: center;
    margin-bottom: 30px;
}

/* card center */
.card-center .passage {
    display: grid;
    grid-template-rows: auto;
    width: 500px;
    margin: 10px 40px;
    padding-left: 100px;
    font-size: var(--p-size);
    font-family: var(--roboto-font);
    gap: 10px;
}

.card-center .passage p {
    margin-bottom: 40px;
}

.card-center .passage p:hover {
    transform: scale(1.05);
    background: var(--color-gradient-4);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    transition: .4s;
}

/* card right */
.card-right {
    font-family: var(--roboto-font);
    font-size: var(--p-size);
}

.card-right .cart p {
    margin-top: 50px;
    margin-bottom: 40px;
    margin-left: 75px;
    font-family: var(--montserrat-font);
    font-size: var(--price-size);
    font-weight: 800;
}

.card-right .cart p:hover {
    transform: scale(1.05);
    background: var(--color-gradient-1);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    transition: .4s;
}

.card-right img {
    height: 40px;
    width: 40px;
}

.card-right .cart-button {
    display: flex;
    flex-direction: row;
    border-radius: 25px;
    height: 50px;
    width: 180px;
    padding-left: 50px;
    padding-top: 4px;
    margin-left: 70px;
    background: var(--color-blue);
    background: var(--color-gradient-3);
    color: var(--color-white);
}

.card-right .cart-button:hover {
    transform: scale(1.2);
    cursor: pointer;
}

.card-right .cart-button h2 {
    padding-top: 5px;
}

/* footer */
footer {
    text-align: end;
    position: sticky;
    bottom: 0;
    z-index: 10;
}

.footer-button img {
    border-radius: 9999px;
    background: var(--color-card);
    box-shadow: 10px 10px 30px 0 var(--color-shadow);
    margin-bottom: 30px;
    margin-right: 30px;
    width: 60px;
    height: 60px;
}

/* scrollbar */
::-webkit-scrollbar {
    width: 8px;
}

::-webkit-scrollbar-thumb {
    background-color: var(--color-th);
    border-radius: 4px;
}

::-webkit-scrollbar-track {
    background-color: var(--color-tr);
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
gif
![css_lab4_1](https://github.com/user-attachments/assets/057f7ada-8db0-40a3-a56c-d0a45bee54c2)
---

[](#การทดลองที่-6-Layout-และการจัดวางอิลิเมนต์)
## การทดลองที่ 6: Layout และการจัดวางอิลิเมนต์

### 6.1 การจัดวางด้วย Flexbox และ Grid

```css
/* Flexbox */
.container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

/* Grid */
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

### ตัวอย่างการใช้งาน: การสร้างหน้าแสดงสินค้าแบบ Grid

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .product-card {
            background: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .product-card:hover {
            transform: translateY(-5px);
        }

        .product-image {
            width: 100%;
            height: 200px;
            background-color: #f5f5f5;
            background-size: cover;
            background-position: center;
        }

        .product-details {
            padding: 15px;
        }

        .product-title {
            font-size: 1.1rem;
            margin: 0 0 10px 0;
            color: #333;
        }

        .product-price {
            font-size: 1.2rem;
            color: #007bff;
            font-weight: bold;
        }

        .product-action {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 15px;
        }

        .add-to-cart {
            background-color: #007bff;
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 4px;
            cursor: pointer;
        }

        .add-to-cart:hover {
            background-color: #0056b3;
        }

        @media (max-width: 768px) {
            .product-grid {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
        }
    </style>
</head>
<body>
    <div class="product-grid">
        <!-- สินค้าชิ้นที่ 1 -->
        <div class="product-card">
            <div class="product-image" style="background-image: url('product1.jpg')"></div>
            <div class="product-details">
                <h3 class="product-title">สินค้าตัวอย่างที่ 1</h3>
                <div class="product-price">฿1,299</div>
                <div class="product-action">
                    <button class="add-to-cart">เพิ่มลงตะกร้า</button>
                </div>
            </div>
        </div>

        <!-- สินค้าชิ้นที่ 2 -->
        <div class="product-card">
            <div class="product-image" style="background-image: url('product2.jpg')"></div>
            <div class="product-details">
                <h3 class="product-title">สินค้าตัวอย่างที่ 2</h3>
                <div class="product-price">฿1,499</div>
                <div class="product-action">
                    <button class="add-to-cart">เพิ่มลงตะกร้า</button>
                </div>
            </div>
        </div>

        <!-- เพิ่มสินค้าอื่นๆ ตามต้องการ -->
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่งขนาดแสดงผลสินค้าให้เล็กลง
3. เพ่ิมรูปภาพของสินค้า


### ผลการทดลอง
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Books</title>

    <!-- css -->
    <link rel="stylesheet" href="../../basic_css/style1.css">
</head>
<body>
    <div id="top"/>
    <!-- nav -->
    <nav>
        <img src="./images/logo.jpg" alt="logo" class="logo">
        <a href="index.html" class="button">Home</a>
        <a href="pages/about.html" class="button">About</a>
        <a href="pages/contact.html" class="button">Contact Us</a>
        <div class="button-login">
            <a href="#" class="login">Login</a>
            <img src="images/login.png" alt="login" class="logo-login">
        </div>
    </nav>
    <!-- hero -->
    <section class="hero">
        <div class="main">
            <h1 class="title">Gallery</h1>
            <p class="subtitle">Books broaden perspectives and enhance knowledge in various fields.</p>
        </div>
        <h1 class="hot-sale">HOT SALE</h1>
        <div class="hot">
            <div class="product">
                <img src="images/gallery/product1.png" alt="product2">
                <div class="hot-passage">
                    <h1 class="title">DIANA & JACK</h1>
                    <h1 class="price">$12.99 / 420 THB</h1>
                </div>
            </div>
        </div>
    </section>
    <hr>
    <!-- main -->
    <main>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product1.png">
                        <img src="images/gallery/product1.png" alt="product1" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        DIANA & JACK
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Taipa Sipipong
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Panya Thai
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        Fantasy
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product2.png">
                        <img src="images/gallery/product2.png" alt="product2" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        CHRISTMAS
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Prachya Aksaranon
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Navatras Publishing
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        CLASSICS
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product3.png">
                        <img src="images/gallery/product3.png" alt="product3" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        TERE & TONY
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Waranya Sirisuk
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Withee Books
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        FANTASY
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product4.png">
                        <img src="images/gallery/product4.png" alt="product4" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        CELTIC TALES
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Anawin Pipattanakit
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Sangdao Publishing
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        SPIRITUALITY & MINDFULNESS
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product5.png">
                        <img src="images/gallery/product5.png" alt="product5" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        THE LORD OF THE KINGS
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Pitchada Wattanakiet
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Jintasill Publishing
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        FANTASY
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product6.png">
                        <img src="images/gallery/product6.png" alt="product6" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        SIMPLE & MINIMALIST
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Nakarin Kulpiya
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Dandin Books
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        SELF-HELP
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product7.png">
                        <img src="images/gallery/product7.png" alt="product7" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        MUTED COLOR POSTER
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Supakorn Arayatham
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Montra Publishing
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        NON-FICTION
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
        <div class="card">
            <div class="card-left">
                <div class="img">
                    <a href="images/gallery/product8.png">
                        <img src="images/gallery/product8.png" alt="product8" width="200"> 
                    </a>
                </div>
            </div>
            <div class="card-center">
                <div class="passage">
                    <p>
                        <strong>TITLE :</strong>
                        MODERN ABSTRACT
                    </p>
                    <p>
                        <strong>AUTHOR :</strong>
                        Charuwan Rattanasombat
                    </p>
                    <p>
                        <strong>PUBLISHER :</strong>
                        Aruntat Publishing
                    </p>
                    <p>
                        <strong>CATEGORY :</strong>
                        BUSINESS & MINDFULNESS
                    </p>
                </div>
            </div>
            <div class="card-right">
                <div class="cart">
                    <p>$12.99 / 420 THB</p>
                    <div class="cart-button">
                        <h2>Shop</h2>
                        <img src="images/cart.png" alt="cart">
                    </div>
                </div>
            </div>   
        </div>
    </main>
    <!-- footer -->
    <footer>
        <div class="footer-button">
            <a href="#top">
                <img src="images/arrow-top.png" alt="arrow-top">
            </a>
        </div>
    </footer>
</body>
</html>
```
```css
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');

:root {
    --color-gradient-1: linear-gradient(to right, #bd0032, #b6046f, #5815b6, #3d0cc4); 
    --color-gradient-2: linear-gradient(to right, #550330, #5d0768, #340774);
    --color-gradient-3: linear-gradient(to right, #20f5d9, #4c7cff, #d455d8);
    --color-gradient-4: linear-gradient(to right, #0e54a3, #d72aee);
    --color-gradient-5: linear-gradient(to right, #ffe017, #d72aee);
    --color-pinkish-red: #d10c41;
    --color-white: #fff;
    --color-card: #f4f4f4;
    --color-tr: #b6b6b6;
    --color-th: #7a7a7a;
    --color-shadow: #8a8a8a;
    --roboto-font: "Roboto", serif;
    --montserrat-font: "Montserrat", serif;
    --h1-size: 64px;
    --a-size: 24px;
    --p-size: 18px;
    --price-size: 40px;
}

* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    text-decoration: none;
}

html {
    scroll-behavior: smooth;
}

body {
    background: var(--color-white);
    height: auto;
}

/* nav */
nav {
    display: flex;
    background: var(--color-gradient-1);
    height: 80px;
    font-family: var(--montserrat-font);
    font-weight: 600;
    position: sticky;
    top: 0;
}

nav .logo {
    border-radius: 9999px;
    padding: 15px;
    margin-left: 30px;
    width: 80px;
    height: 80px;
}

nav .button {
    margin: 10px 20px;
    padding: 15px;
    font-size: var(--a-size);
    color: var(--color-white);
}

nav .button:hover {
    border-radius: 9999px;
    padding: 15px;
    background: var(--color-white);
    color: var(--color-pinkish-red);
    cursor: pointer;
    transition: .4s;
}

nav .button-login {
    margin: 10px 20px;
    margin-left: 700px;
    padding: 15px;
    width: 150px;
}

nav .button-login:hover {
    border-radius: 9999px;
    padding: 15px;
    background: var(--color-gradient-5);
    cursor: pointer;
    transition: .4s, border-radius 0ms ease;
}

nav .button-login a {
    font-size: var(--a-size);
    color: var(--color-white);
}

nav .button-login .logo-login {
    position: absolute;
    margin-left: 20px;
    width: 30px;
    height: 30px;
}

/* section */
.hero .main {
    text-align: center;
    margin-bottom: 60px;
}

.hero .main .title {
    margin: 20px 40px;
    font-family: var(--roboto-font);
    font-size: var(--h1-size);
    background: var(--color-gradient-1);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.hero .main .subtitle {
    margin: 20px 40px;
    font-family: var(--roboto-font);
    font-size: var(--p-size);
    background: var(--color-gradient-2);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.hero .hot-sale {
    font-family: var(--montserrat-font);
    font-size: var(--h1-size);
    text-align: center;
    background: var(--color-gradient-5);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.hot {
    margin-top: 40px;
    margin-left: 280px;
}

.product {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
}

.hot img {
    height: 400px;
    width: 260px;
    margin-left: 350px;
}

.hot-passage {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    margin-left: 280px;
    margin-bottom: 40px;
}

.hot-passage .title {
    font-family: var(--roboto-font);
    font-size: var(--h1-size);
    margin-bottom: 20px;
}

.hot-passage .title:hover {
    transform: scale(1.05);
    background: var(--color-gradient-1);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    transition: .4s;
}

.hot-passage .price {
    font-family: var(--montserrat-font);
    font-size: var(--price-size);
    margin-left: 40px;
}

.hot-passage .price:hover {
    transform: scale(1.05);
    background: var(--color-gradient-5);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    transition: .4s;
}

hr {
    border: none;
    border-radius: 9999px;
    height: 6px ;
    margin-left: 70px;
    width: 90%;
    background: var(--color-gradient-3);
}

/* main */
/* card */
.card {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    border-radius: 20px;
    padding: 40px 25px;
    margin-left: 650px;
    margin-top: 60px;
    width: 260px;
    height: 360px;
    gap: 10px;
    box-shadow: 10px 10px 20px 0 var(--color-shadow);
    background: var(--color-card);
    text-align: start;
    overflow: hidden;
    cursor: pointer;
}

.card:hover {
    margin: 60px 110px;
    padding-left: 50px;
    gap: 30px;
    width: 85%;
    transition: margin-left .5s ease, width .5s ease;
}

/* card left */
.card-left .img {
    display: flex;
    text-align: center;
    margin-bottom: 30px;
}

/* card center */
.card-center .passage {
    display: grid;
    grid-template-rows: auto;
    width: 500px;
    margin: 10px 40px;
    padding-left: 100px;
    font-size: var(--p-size);
    font-family: var(--roboto-font);
    gap: 10px;
}

.card-center .passage p {
    margin-bottom: 40px;
}

.card-center .passage p:hover {
    transform: scale(1.05);
    background: var(--color-gradient-4);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    transition: .4s;
}

/* card right */
.card-right {
    font-family: var(--roboto-font);
    font-size: var(--p-size);
}

.card-right .cart p {
    margin-top: 50px;
    margin-bottom: 40px;
    margin-left: 75px;
    font-family: var(--montserrat-font);
    font-size: var(--price-size);
    font-weight: 800;
}

.card-right .cart p:hover {
    transform: scale(1.05);
    background: var(--color-gradient-1);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    transition: .4s;
}

.card-right img {
    height: 40px;
    width: 40px;
}

.card-right .cart-button {
    display: flex;
    flex-direction: row;
    border-radius: 25px;
    height: 50px;
    width: 180px;
    padding-left: 50px;
    padding-top: 4px;
    margin-left: 70px;
    background: var(--color-blue);
    background: var(--color-gradient-3);
    color: var(--color-white);
}

.card-right .cart-button:hover {
    transform: scale(1.2);
    cursor: pointer;
}

.card-right .cart-button h2 {
    padding-top: 5px;
}

/* footer */
footer {
    text-align: end;
    position: sticky;
    bottom: 0;
    z-index: 10;
}

.footer-button img {
    border-radius: 9999px;
    background: var(--color-card);
    box-shadow: 10px 10px 30px 0 var(--color-shadow);
    margin-bottom: 30px;
    margin-right: 30px;
    width: 60px;
    height: 60px;
}

/* scrollbar */
::-webkit-scrollbar {
    width: 8px;
}

::-webkit-scrollbar-thumb {
    background-color: var(--color-th);
    border-radius: 4px;
}

::-webkit-scrollbar-track {
    background-color: var(--color-tr);
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![css_lab5_1](https://github.com/user-attachments/assets/b4c58dd9-6495-48d8-aa0e-316fcc9f0ee3)

---

### ตัวอย่างการใช้งาน: การสร้างเลย์เอาต์ Modern Dashboard

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .dashboard {
            display: grid;
            grid-template-areas: 
                "sidebar header"
                "sidebar main";
            grid-template-columns: 250px 1fr;
            grid-template-rows: auto 1fr;
            min-height: 100vh;
        }

        .header {
            grid-area: header;
            background: white;
            padding: 1rem;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .sidebar {
            grid-area: sidebar;
            background: #2c3e50;
            color: white;
            padding: 1rem;
        }

        .main-content {
            grid-area: main;
            padding: 1rem;
            background: #f5f7fa;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .stat-card {
            background: white;
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .chart-container {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 1rem;
        }

        .chart {
            background: white;
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        @media (max-width: 768px) {
            .dashboard {
                grid-template-areas: 
                    "header"
                    "main";
                grid-template-columns: 1fr;
            }

            .sidebar {
                display: none;
            }

            .chart-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="dashboard">
        <header class="header">
            <h1>แดชบอร์ด</h1>
            <nav>
                <button>โปรไฟล์</button>
                <button>ออกจากระบบ</button>
            </nav>
        </header>

        <aside class="sidebar">
            <nav>
                <ul>
                    <li>หน้าแรก</li>
                    <li>รายงาน</li>
                    <li>การตั้งค่า</li>
                </ul>
            </nav>
        </aside>

        <main class="main-content">
            <div class="stats-grid">
                <div class="stat-card">
                    <h3>ยอดขายรวม</h3>
                    <p>฿150,000</p>
                </div>
                <div class="stat-card">
                    <h3>จำนวนออเดอร์</h3>
                    <p>1,234</p>
                </div>
                <div class="stat-card">
                    <h3>ลูกค้าใหม่</h3>
                    <p>45</p>
                </div>
            </div>

            <div class="chart-container">
                <div class="chart">
                    <h3>กราฟแสดงยอดขาย</h3>
                    <!-- เพิ่มกราฟตามต้องการ -->
                </div>
                <div class="chart">
                    <h3>สัดส่วนสินค้าขายดี</h3>
                    <!-- เพิ่มกราฟตามต้องการ -->
                </div>
            </div>
        </main>
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่งการแสดงผลต่าง ๆ ให้สวยงาม



### ผลการทดลอง
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard</title>

    <link rel="stylesheet" href="../basic_css/dashboard.css">
</head>
<body>
    <div class="dashboard">
        <header class="header">
            <h1>แดชบอร์ด</h1>
            <nav>
                <button class="button">โปรไฟล์</button>
                <button class="button">ออกจากระบบ</button>
            </nav>
        </header>
        <aside class="sidebar">
            <nav>
                <ul>
                    <li>หน้าแรก</li>
                    <li>รายงาน</li>
                    <li>การตั้งค่า</li>
                </ul>
            </nav>
        </aside>

        <main class="main-content">
            <div class="stats-grid">
                <div class="stat-card">
                    <h3>ยอดขายรวม</h3>
                    <hr class="line">
                    <p>฿150,000</p>
                </div>
                <div class="stat-card">
                    <h3>จำนวนออเดอร์</h3>
                    <hr class="line">
                    <p>1,234</p>
                </div>
                <div class="stat-card">
                    <h3>ลูกค้าใหม่</h3>
                    <hr class="line">
                    <p>45</p>
                </div>
            </div>

            <hr>

            <div class="chart-container">
                <div class="chart">
                    <h3>กราฟแสดงยอดขาย</h3>
                    <!-- เพิ่มกราฟตามต้องการ -->
                </div>
                <div class="chart">
                    <h3>สัดส่วนสินค้าขายดี</h3>
                    <!-- เพิ่มกราฟตามต้องการ -->
                </div>
            </div>
        </main>
    </div>
</body>
</html>
```
```css
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');

* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    text-decoration: none;
    font-family: var(--roboto-font);
}

:root {
    --color-gradient-1: linear-gradient(to right, #20f5d9, #4c7cff, #d455d8);
    --color-gradient-2: linear-gradient(to right, #f7eb84, #fcabff);
    --color-white: #fff;
    --color-shadow: #8a8a8a;
    --roboto-font: "Roboto", serif;
    --montserrat-font: "Montserrat", serif;
    --h1-size: 42px;
    --h2-size: 30px;
    --h3-size: 24px;
    --h4-size: 18px;
}

h3 {
    font-size: var(--h2-size);
}

p {
    font-family: var(--montserrat-font);
    font-size: var(--h3-size);
    font-weight: 700;
    margin-top: 20px;
    color: #333333;
}

hr {
    border: none;
    border-radius: 9999px;
    height: 6px ;
    margin-left: 30px;
    margin-bottom: 30px;
    width: 95%;
    background: var(--color-gradient-1);
}

.line {
    border: none;
    border-radius: 9999px;
    height: 6px ;
    margin-left: 5px;
    margin-top: 20px;
    margin-bottom: 20px;
    width: 95%;
    background: var(--color-gradient-1);
}

.dashboard {
    display: grid;
    grid-template-areas: 
        "sidebar header"
        "sidebar main";
    grid-template-columns: 250px 1fr;
    grid-template-rows: auto 1fr;
    min-height: 100vh;
}

.header {
    grid-area: header;
    background: var(--color-gradient-1);
    padding: 1rem;
    box-shadow: 10px 10px 20px 0 var(--color-shadow);
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.header h1 {
    color: var(--color-white);
    font-size: var(--h2-size);
}

.header .button {
    border-radius: 25px;
    padding: 5px 10px;
    margin-left: 10px;
    font-size: var(--h4-size);
    background: var(--color-gradient-2);
    color: black;
}

.sidebar {
    grid-area: sidebar;
    background: #2c3e50;
    color: white;
    padding: 1rem;
    font-size: var(--h1-size);
}

li {
    margin-bottom: 40px;
}

.main-content {
    grid-area: main;
    padding: 1rem;
    padding-top: 3rem;
    background: #f5f7fa;
}

.stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1rem;
    margin-bottom: 2rem;
}

.stat-card {
    background: white;
    padding: 1.5rem;
    border-radius: 8px;
    box-shadow: 10px 10px 20px 0 var(--color-shadow)
}

.chart-container {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 1rem;
}

.chart {
    background: white;
    padding: 1.5rem;
    border-radius: 8px;
    box-shadow: 10px 10px 20px 0 var(--color-shadow)
}

@media (max-width: 768px) {
    .dashboard {
        grid-template-areas: 
            "header"
            "main";
        grid-template-columns: 1fr;
    }

    .sidebar {
        display: none;
    }

    .chart-container {
        grid-template-columns: 1fr;
    }
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![image](https://github.com/user-attachments/assets/9f00933e-e1ce-4c06-90a0-8964b36f9080)
