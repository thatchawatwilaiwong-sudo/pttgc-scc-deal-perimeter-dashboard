# PTTGC x SCC/SCGC Deal Perimeter Interactive Dashboard

Interactive dashboard สำหรับใช้ประกอบการนำเสนอ preliminary due diligence ของโครงการ JV ระหว่าง PTTGC และ SCC/SCGC ในธุรกิจ petrochemical olefins และ polyolefins

ข้อมูลใน dashboard เป็น analyst proxy จากโมเดล Excel, ข้อมูลสาธารณะ เช่น 56-1 / One Report และไฟล์ SCGC FY2025 PDF ที่ใช้ปรับฐานข้อมูลฝั่ง SCC/SCGC ให้เป็น SCGC segment disclosure โดยตรง จึงควรใช้เป็น discussion pack สำหรับ RM / credit / management ก่อน และควร validate เพิ่มจาก data room หรือข้อมูลจากบริษัทก่อนใช้ตัดสินใจด้าน credit approval

## วิธีเปิดใช้งาน

เปิดไฟล์ `index.html` ด้วย browser ได้ทันที ไม่ต้องติดตั้งโปรแกรมเพิ่ม และไม่ต้องมี backend

ถ้าต้องการเปิดผ่าน local server:

```bash
python3 -m http.server 8080
```

จากนั้นเข้า URL:

```text
http://localhost:8080/index.html
```

## วิธีใช้งานหลัก

1. เลือก scenario จากกล่อง `Select scenario` ด้านบนขวา
2. Dashboard ทุกหน้าจะเปลี่ยนตัวเลขและคำอธิบายตาม scenario ที่เลือก
3. ใช้เมนูด้านซ้ายเพื่อสลับหน้า เช่น Overview, Value Chain, JV Dashboard, Opportunity, Asset Bridge และ RM Heatmap
4. ใช้หน้า Overview เพื่อเริ่มเล่า story ให้หัวหน้าเห็นภาพรวมก่อน แล้วค่อย drill down ไปที่ Value Chain, JV Dashboard และ Opportunity

## คำอธิบาย Scenario

- `Scenario A: Narrow olefins JV`  
  Perimeter แคบ เน้น olefins/base chemicals เป็นหลัก โดยใช้ Map Ta Phut Olefins จาก SCGC Note 18 เป็น proxy ฝั่ง SCGC ผลกระทบต่อ parent asset ต่ำกว่า scenario อื่น แต่ยังมี financing opportunity จาก working capital, trade finance และ hedging

- `Scenario B: Base integrated PE/PP JV`  
  Base case ที่มีโอกาสสูงสุด ครอบคลุม olefins + PE/PP polymers โดยใช้ SCGC Olefins Chain in Thailand จาก Note 19 เป็นฐานฝั่ง SCGC เหมาะสำหรับเสนอ full banking package

- `Scenario C: Expanded perimeter`  
  Perimeter กว้างขึ้น โดยเพิ่ม SCGC Vinyl Chain เข้าไปในฐาน SCGC มีโอกาส financing สูงสุด แต่ credit risk และ execution risk สูงที่สุดเช่นกัน

- `Scenario D: No transaction after DD`  
  ไม่มี asset transfer โดยตรง แต่ยังใช้ analysis เพื่อทำ treasury optimization, monitoring และเตรียมความพร้อมหากดีลกลับมาใหม่

## คำอธิบายแต่ละหน้า

### Overview

หน้าเริ่มต้นสำหรับสรุปภาพรวม scenario ที่เลือก แสดง:

- JV Revenue
- JV EBITDA
- PTTGC asset reduction
- SCC asset reduction
- กราฟรายได้ / EBITDA / asset proxy ของ JV
- กราฟผลกระทบ asset reduction ของ parent
- ตารางเปรียบเทียบทุก scenario

เหมาะสำหรับใช้เปิดการนำเสนอ เพื่อให้เห็นว่าดีลนี้มีขนาดเท่าไรและกระทบ PTTGC/SCC มากน้อยแค่ไหน

### Value Chain

แสดง petrochemical value chain ตั้งแต่ feedstock, refining/gas separation, base chemicals, intermediates, polymers, converters และ end-use

จุดสำคัญ:

- สี PTTGC และ SCC/SCGC แสดงตำแหน่ง asset ของแต่ละบริษัทใน value chain
- สีม่วงแสดงส่วนของ value chain ที่คาดว่า asset จะถูกนำไปรวมใน JV ตาม scenario ที่เลือก
- ใช้เพื่ออธิบายว่า JV จะอยู่ตรงไหนของ value chain และ perimeter กว้างหรือแคบเพียงใด

### JV Dashboard

หน้า dashboard เฉพาะตัว JV ตาม scenario ที่เลือก แสดง:

- Revenue ของ JV
- EBITDA ของ JV
- Asset size ของ JV
- EBITDA margin
- Asset source ว่ามาจาก PTTGC เท่าไร และ SCC/SCGC เท่าไร
- Revenue contribution ของแต่ละฝ่าย
- Position ของ JV ใน petrochemical value chain

เหมาะสำหรับตอบคำถามผู้บริหารว่า ถ้า JV เกิดขึ้นจริง entity ใหม่นี้จะมีขนาดธุรกิจเท่าไร ยืนอยู่ตรงไหนของอุตสาหกรรม และ asset ที่ใส่เข้ามามาจากใคร

### Opportunity

สรุป financial opportunity ในมุม Relationship Manager ตาม scenario ที่เลือก โดยแต่ละ opportunity จะระบุ:

- โอกาสทางการเงินที่ธนาคารสนับสนุนได้
- Product ที่เสนอได้ เช่น working capital, LC/TR, trade finance, FXDE, bridge loan, term loan, guarantee, cash management, receivables finance
- คำอธิบายว่าทำไม product นั้นเกี่ยวข้องกับ scenario
- Key risk ที่ RM / credit team ต้องระวัง

เหมาะสำหรับใช้คุยกับ Head of RM ว่าธนาคารควรเข้าไปจับ opportunity ส่วนไหน และต้องควบคุม risk อะไรประกอบ

### Asset Bridge

แสดง before / transfer / after ของ total assets ของ PTTGC และ SCC ตาม scenario ที่เลือก

ใช้เพื่อวิเคราะห์:

- Parent asset base ลดลงเท่าไร
- Asset ที่ transfer เข้า JV มีขนาดเท่าไร
- PTTGC และ SCC เหลือ asset หลัง transfer เท่าไร
- ผลกระทบเชิง balance sheet ที่อาจนำไปสู่ covenant, rating หรือ lender communication issue

### RM Heatmap

แสดง heatmap เปรียบเทียบ scenario ในมุม RM และ credit โดยให้คะแนน 1-5 ในหัวข้อ:

- Revenue scale
- EBITDA quality
- Asset transfer
- Parent credit pressure
- Financing opportunity

เหมาะสำหรับใช้เป็น executive summary ว่า scenario ไหนมี opportunity สูง แต่มี risk สูงตามไปด้วย

## Suggested Storyline สำหรับนำเสนอหัวหน้า

1. เริ่มที่หน้า `Overview` เพื่ออธิบาย scenario และขนาดของ JV
2. ไปที่หน้า `Value Chain` เพื่อชี้ว่า asset ที่อาจถูกโอนไป JV อยู่ตรงไหนของ petrochemical chain
3. ไปที่หน้า `JV Dashboard` เพื่อสรุปว่า JV จะมี revenue, EBITDA และ asset size เท่าไร
4. ไปที่หน้า `Asset Bridge` เพื่ออธิบายผลกระทบต่อ PTTGC และ SCC หลัง asset transfer
5. ปิดท้ายที่หน้า `Opportunity` และ `RM Heatmap` เพื่อสรุป product ที่ธนาคารควรเสนอ พร้อม risk ที่ต้อง monitor

## How to publish on GitHub Pages

1. Create a GitHub repository.
2. Upload `index.html` to the repository root.
3. Go to Settings > Pages.
4. Select branch `main` and folder `/root`.
5. Open the GitHub Pages URL after deployment.

## Notes

- No backend required.
- No external JavaScript library required.
- Scenario dropdown updates KPI cards, tables, charts and opportunity cards in the browser.
- Values are analyst proxies based on the Excel model and public 56-1 / One Report data.
- SCC/SCGC values were refreshed using the newly provided SCGC FY2025 PDF: consolidated SCGC revenue/EBITDA/assets plus Note 18 and Note 19 segment disclosures.
- Footer credit is shown as `Developed by Thatchawat.w`.
