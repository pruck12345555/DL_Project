**โมเดลตรวจจับเนื้องอกในสมองจากภาพ MRI**  

**คำอธิบาย**  
Deep learning model โดยแบ่งออกเป็น 2 โมเดลสำหรับการระบุพิ้นที่และการคัดแยกประเภทเนื้องอกในสมอง 4 คลาส ได้แก่ Meningioma, Glioma, Pituitary, No Tumor โดยใน repository นี้ประกอบไปด้วยข้อมูลฝึกสอนและทดสอบ, โค้ดการฝึกสอนของทั้งสองโมเดล, ไฟล์ weights, สคริปต์สำหรับแยก dataset เป็น train, test, validation, dependencies, และ สคริปต์สำหรับเปิด local web server เพื่อ deploy  

**วิธีติดตั้ง**  
1. git clone https://github.com/pruck12345555/DL_Project.git
2. ทำการ unrar ไฟล์ dataset โดยทำได้ 2 วิธี  
2.1. ใช้ terminal  
2.1.1. cd DL_Project/data  
2.1.2. unrar x figshare_braintumor.rar  
หรือ  
2.2. Manual  
2.2.1. คลิกเข้าไปใน directory DL_Project/data  
2.2.2. คลิกขวาที่ไฟล์ figshare_braintumor.rar แล้ว extract here  
3. ลง dependencies สำหรับ conda  
3.1. conda env create -f dl_environment.yml

**วิธี split dataset เป็น train, test, split**  
1. รันโค้ดในสคริปต์ src/splitting.ipynb  

**วิธีเปิด local server สำหรับ web-application**
1. เปิดไฟล์ DL_Project/src/webapp.ipynb ใน VS Code หรือ jupyter
2. รัน code block แรกในไฟล์ webapp.ipynb
3. เข้า url ตาม output จาก cell

**การฝึกสอน**  
1. สามารถฝึกสอน, ปรับโครงสร้าง, ปรับ hyperparameters ได้ในไฟล์ src/Classification.ipynb และ src/Segmentation.ipynb  โดย uncomment และ run cell สุดท้ายในแต่ละไฟล์เพื่อ save ผลลัพธ์แทนที่ไฟล์เดิม

**File Structure**  
1. data : ข้อมูลฝึกสอนและทดสอบ
2. models : ไฟล์ weights สำหรับ classification model และ keras model สำหรับ segmentation model
3. src : ไฟล์โค้ดทั้งหมด โดยแบ่ง Classification.ipynb, Segmentation.ipynb, splitting.ipynb, webapp.ipynb  
4. demos : การทดสอบโมเดลในสามระดับความยากได้แก่ ง่าย, กลาง, ยาก
