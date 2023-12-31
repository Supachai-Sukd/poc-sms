# Example Send SMS
นี้เป็นอย่างตัวการส่ง SMS ด้วย API 

### Requirement:
- คุณต้องเป็นสมาชิกของ ThaibulkSMS ก่อน จึงจะส่ง SMS ได้ [สมาชิก ThaibulkSMS](https://account.thaibulksms.com/register/)
- สร้าง Key กับ Secret ได้ที่ [ThaibulkSMS API Console](https://member.thaibulksms.com/setting/api)
- ขั้นการสร้าง Key กับ Secret เพื่อนําไปใช้กับ API สําหรับส่ง SMS API ศึกษาได้จากลิงค์นี้ [เรียนรู้เพิ่มเติม](https://www.thaibulksms.com/developer/)

## วิธีตั้งค่า
สร้างไฟล์ .env ก่อน
```dosini
API_KEY=
API_SECRET=
```
ทำการลง package ก่อน
```
npm install
```
Run app
```
npm run start

Example app listening at http://localhost:3000
```

## วิธีทดสอบ
ส่งข้อความไปยังหมายเลขโทรศัพท์ปลายทาง

```bash

curl \
-H 'Content-Type: application/x-www-form-urlencoded' \
-X POST \
--data-urlencode 'phone_number=+668xxxxxxxx' \
--data-urlencode 'message=Hello Thaibulksms api' \
http://localhost:3000/send-sms


# phone_number สามารถส่งได้ทั้งรูปแบบ +668xxxxxxxx หรือ 08xxxxxxxx

# Response { remaining_credit: 9, total_use_credit: 1, credit_type: 'standard', phone_number_list: [ { number: '+668xxxxxxxx', message_id: '19mJUdnjrU28BqeqQP83gC', used_credit: 1 } ], bad_phone_number_list: [] }

```

