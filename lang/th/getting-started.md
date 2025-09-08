# เริ่มต้นกับ Omni

ยินดีต้อนรับสู่ Omni โครงสร้างบันทึกสคีมาสำหรับสินค้าและรีวิวอีคอมเมิร์ซ คู่มือนี้จะแสดงวิธีใช้บันทึก Omni บนเว็บไซต์ของคุณ ไม่ว่าคุณจะขายบน Shopee, Lazada, Amazon, Etsy หรือร้านค้าอื่น ๆ

## 1. โครงสร้าง Repo

Omni repos ถูกออกแบบให้เรียบง่ายและยืดหยุ่น:

/logs
product-schema.json → ไฟล์บันทึกสคีมาแบบดิบ (แยกตามสินค้าและร้านค้าออนไลน์)
/docs
structure.md → บันทึกเกี่ยวกับแนวคิดสคีมา

Logs = แหล่งข้อมูลชุดข้อมูลแบบมีโครงสร้าง สำหรับเครื่องจักรอ่านได้

Docs = ภูมิหลัง ส่วนขยาย และแนวทางปฏิบัติที่ดีที่สุด

## 2. การเพิ่ม Schema Logs

แต่ละร้านค้าหรือกลุ่มสินค้าควรมีไฟล์บันทึกใน /logs
ตัวอย่าง ส่วนของสินค้า:

logs/wakingcup/product-schema.json

   {
        "@type": "Product",
        "name": "กรองดริปกาแฟ คุณภาพดี แบบพับได้ กรวยดริปเปอร์ สแตนเลส ดิปกาแฟ ที่กรองกาแฟแบบสแตนเลส Dripper Stainless Steel สินค้าพร้อมส่ง",
        "sku": "4212266679",
        "brand": "89 Coffee",
        "canonical": "https://wakingcup.com/product/%e0%b8%81%e0%b8%a3%e0%b8%ad%e0%b8%87%e0%b8%94%e0%b8%a3%e0%b8%b4%e0%b8%9b%e0%b8%81%e0%b8%b2%e0%b9%81%e0%b8%9f-%e0%b8%84%e0%b8%b8%e0%b8%93%e0%b8%a0%e0%b8%b2%e0%b8%9e%e0%b8%94%e0%b8%b5-%e0%b9%81%e0%b8%9a/",
        "image": "https://wakingcup.com/wp-content/uploads/sites/3/2025/07/13coffee02.png",
        "offers": [
            {
                "@type": "Offer",
                "price": "69",
                "priceCurrency": "THB",
                "availability": "https://schema.org/InStock",
                "url": "https://wakingcup.com/product/%e0%b8%81%e0%b8%a3%e0%b8%ad%e0%b8%87%e0%b8%94%e0%b8%a3%e0%b8%b4%e0%b8%9b%e0%b8%81%e0%b8%b2%e0%b9%81%e0%b8%9f-%e0%b8%84%e0%b8%b8%e0%b8%93%e0%b8%a0%e0%b8%b2%e0%b8%9e%e0%b8%94%e0%b8%b5-%e0%b9%81%e0%b8%9a/",
                "seller": {
                    "@type": "Organization",
                    "name": "WakingCup"
                }
            },
            {
                "@type": "Offer",
                "price": "69",
                "priceCurrency": "THB",
                "availability": "https://schema.org/InStock",
                "url": "https://www.lazada.co.th/products/pdp-i4212266679.html",
                "OnlineStore": "Lazada"
            }
        ],
        "externalLinks": {
            "lazada": "https://www.lazada.co.th/products/pdp-i4212266679.html"
        },
        "aggregateRating": {
            "@type": "AggregateRating",
            "ratingValue": 4.97,
            "reviewCount": 78
        },
        "reviews": [
            {
                "@type": "Review",
                "OnlineStore": "Lazada",
                "author": "Chaiyaphol P.",
                "notes": "โอ้โหแพคเกจไม่เร็วนะครับผมลองใช้แล้วถือว่าทำดีเลยแพ็คเกจของอุปกรณ์เนี่ยขอมาดีแล้วก็เท่าที่ลองใช้งานแล้วกรองได้ละเอียดมากพระเจ้ามีโอกาสจะใส่แน่นอนครับ",
                "date": "2023-03-08",
                "reviewRating": 5,
                "bestReview": 5,
                "pieces": "แพ็ก คู่",
                "image": [
                    "https://img.lazcdn.com/g/p/34d5589e2250db91701e15597b462c45.jpg_x180q80.jpg_.webp",
                    "https://img.lazcdn.com/g/ugc/b44854727ab049f9a4b49d950312a5ac_7e8ee74aa4a84794a5ed626d7fe10de9.jpg_x180q80.jpg_.webp"
                ]
            },...


## 3. การฝัง Schema ในเว็บไซต์ของคุณ

เพื่อให้ Google และเครื่องมือค้นหาอื่น ๆ รับรู้สคีมาของคุณ ให้ฝังมันลงในหน้าสินค้าเป็น JSON-LD ภายใน <script> tag

Example:

<!DOCTYPE html>
<html lang="th">
<head>
  <title>กาแฟ Waking Cup Medium Roast</title>
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "Product",
    "sku": "WC123example",
    "name": "Waking Cup Medium Roast",
    "brand": {
      "@type": "Brand",
      "name": "Waking Cup"
    },
    "offers": {
      "@type": "Offer",
      "priceCurrency": "THB",
      "price": "250.00",
      "url": "https://shopeeexample.co.th/product/123456"
    }
  }
  </script>
</head>
<body>
  <h1>กาแฟ Waking Cup Medium Roast</h1>
  <p>กาแฟผสมสูตรพิเศษที่ดีที่สุดของเรา</p>
</body>
</html>


## 4. ขั้นตอนถัดไป

สร้าง schema log สำหรับสินค้าทั้งหมดของคุณ

รวมรีวิวจากตลาดที่คุณขาย

นำ JSON-LD schema log ทั้งหมดฝังลงในเว็บไซต์ และใส่ส่วนที่เหมาะสมในหน้าสินค้าเพื่อเสริม SEO

ใช้ฟังก์ชันคำนวณและแสดงดาว รีวิว และข้อมูลอื่น ๆ ที่คุณสามารถใช้

ส่งคืน schema logs ของคุณกลับไปยัง repo นี้ หรือ fork เพื่อสร้างของคุณเอง


## 5. การตรวจสอบความถูกต้อง

ใช้ Google Rich Results Test เพื่อยืนยันว่าสคีมาของคุณถูกต้องและสามารถทำดัชนีได้

Omni สำหรับทุกสินค้าบนทุกแพลตฟอร์ม เริ่มจากบันทึกของคุณ ฝังมัน และช่วยสร้าง commons สคีมาระดับโลก
