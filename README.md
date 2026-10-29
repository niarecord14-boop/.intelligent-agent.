# NIA Records — เว็บใช้งานนอก Claude (Firebase)

ไฟล์ในชุดนี้
- index.html          ตัวเว็บ (เปิดใน Claude ได้เหมือนเดิม และใช้ Firebase เมื่ออยู่นอก Claude)
- firebase-config.js  ไฟล์เดียวที่ต้องแก้: ค่า Firebase + อีเมลเจ้าของระบบ
- firestore.rules     กฎฐานข้อมูล (วางใน Firebase)

ขั้นตอนตั้งค่า (ฟรี ใช้แพ็กเกจ Spark)
1. console.firebase.google.com → Add project
2. Build → Authentication → Get started → เปิด 2 วิธี: Anonymous และ Google
   และที่ Settings → Authorized domains เพิ่มโดเมน github.io (หรือโดเมนที่ใช้)
3. Build → Firestore Database → Create database → วางเนื้อหา firestore.rules ที่แท็บ Rules แล้ว Publish
4. Project settings → Your apps → Web (</>) → คัดลอก firebaseConfig มาใส่ firebase-config.js
   และใส่อีเมล Google ของเจ้าของใน NIA_OWNER_EMAILS
5. อัปไฟล์ทั้ง 3 (ยกเว้น README) ขึ้น GitHub แล้วเปิด Settings → Pages (branch main, / root)
6. เปิดเว็บ → กดปุ่มมุมซ้ายล่าง "เจ้าของระบบ · เข้าสู่ระบบด้วย Google" → จะเห็นแผงเจ้าของระบบ
   สร้างบัญชีแอดมินคนแรก แล้วส่งลิงก์ให้คนอื่นสมัครได้

ข้อจำกัด
- การซ่อนข้อมูล/ล็อกบัญชีทำที่หน้าจอ ไม่ใช่ที่ฐานข้อมูล: คนที่มีความรู้เปิดเครื่องมือนักพัฒนาอ่านข้อมูลได้
- รหัสประจำตัวถูกเก็บในฐานข้อมูลตามที่ออกแบบไว้ ห้ามใช้ข้อมูลหรือรหัสจริงที่สำคัญ
- ข้อมูลเดิมที่ทดลองใน Claude ไม่ถูกย้ายมา (ฐานข้อมูลใหม่เริ่มว่าง)
