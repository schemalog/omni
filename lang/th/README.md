#Omni

Omni คือโครงสร้าง schema log แบบเปิด สำหรับข้อมูลสินค้าและรีวิวในอีคอมเมิร์ซ ช่วยให้สามารถนำเสนอข้อมูลสินค้าและความคิดเห็นจากลูกค้าในหลายแพลตฟอร์ม (Shopee, Lazada, Amazon, Etsy, GumRoad ฯลฯ) ได้ในรูปแบบที่เครื่องอ่านเข้าใจได้

Omni ถูกพัฒนาต้นแบบครั้งแรกกับ Waking Cup Coffee แต่โครงสร้างนี้ออกแบบมาเพื่อรองรับสินค้าใด ๆ ในร้านค้าใด ๆ ทั่วโลก

ทำไมต้องใช้ Omni?

ข้อมูลสินค้ากระจัดกระจายอยู่ในหลายแพลตฟอร์ม รีวิวถูกเก็บแยกอยู่ในแต่ละระบบ Omni ช่วยแก้ปัญหาด้วย:

Unified product schema: กำหนดข้อมูลสินค้าเพียงครั้งเดียว แล้วนำไปอ้างอิงได้ทุกแพลตฟอร์ม

Cross-platform reviews: รวมคะแนนและรีวิวจากหลาย ๆ มาร์เก็ตเพลส

SEO & AI benefits: ฝัง JSON-LD schema เพื่อให้แสดง rich snippets (เช่น ดาว รีวิว) และทำให้ข้อมูลถูกค้นหาได้ง่าย เหมือนกับการส่งสัญญาณให้ crawler มาค้นพบ

Scalability: ใช้ได้ทั้งร้านเล็ก ๆ ไปจนถึงแคตตาล็อกขนาดใหญ่

คุณสมบัติ

📦 รายการสินค้า พร้อมรหัส SKU
⭐ การรวมรีวิวจากหลายแพลตฟอร์ม (Shopee, Lazada, Amazon ฯลฯ)
🌐 พร้อมใช้งานในรูปแบบ JSON-LD สำหรับฝังในเว็บไซต์
🔗 โครงสร้างที่ขยายได้ — เชื่อมต่อสินค้า รีวิว หมวดหมู่ หรือแม้แต่แคตตาล็อกขายส่ง

Example
Product Entry
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

Review Aggregation
        "aggregateRating": {
            "@type": "AggregateRating",
            "ratingValue": 4.97,
            "reviewCount": 78,
            "source": ["Shopee", "Lazada"]
        },
}

วิธีใช้งาน

ฝัง JSON-LD schema ของ Omni ลงในหน้าสินค้า เพื่อเพิ่มประสิทธิภาพ SEO

เก็บ schema logs ที่รวมข้อมูลสินค้า + รีวิว ทั้งหมดไว้ในที่เดียว

ขยายการใช้งานได้หลายแพลตฟอร์ม: รวมแคตตาล็อกไว้ตรงกลาง แต่ให้แต่ละร้านยังคงขายในระบบของตัวเอง

Roadmap

เผยแพร่ reference implementation (Waking Cup)

สคริปต์ตัวอย่างสำหรับรวมข้อมูลรีวิว

แนวทางสำหรับขยายไปสู่ wholesale และ marketplace

เวอร์ชันภาษาไทย (สำหรับผู้ขายบน Lazada/Shopee ในไทย)

การมีส่วนร่วม (Contributing)

อยากเพิ่ม schema log ของร้านคุณ? แค่ fork repo นี้ เพิ่มข้อมูล แล้วส่ง PR มา Omni ถูกออกแบบมาเพื่อเติบโตเป็น global schema commons สำหรับอีคอมเมิร์ซ

License

MIT License — ฟรีสำหรับทุกคนที่จะใช้ ขยาย หรือฝัง
