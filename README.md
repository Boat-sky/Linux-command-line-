# Linux command line
### รีบูตเครื่อง   
```
sudo reboot
```   
หรือ   
```
init 6
```   
### ปิดเครื่อง   
```
sudo shutdown now
```   
หรือ   
```
init 0
```   
### วิธีแปลงไฟล์.sh จากสีเทาให้เป็นสีเขียว
1. เข้าไปใน directory ที่มีไฟล์นั้นอยู่
2. chmod 777 (ชื่อไฟล์นั้น)

### วิธี bash ไฟล์
bash (ชื่อ sh ไฟล์)

### เข้าถึง root   
```
sudo root
```
เมื่อเข้าใน root แล้วไม่ต้องใช้คำสั่ง sudo เวลาสั่งการ   

### วิธีสร้าง env (ของ conda)
1. conda -n (env name) python=(เวอร์ชั่นที่ต้องการ)
2. conda activate (env name)
3. conda deactivate

### วิธีสร้าง env (ของ virtualenv)   
1. virtualenv (ชื่อ env)   
2. sourcce (ชื่อ env)/bin/activate   
3. deactivate   
4. sudo rm -rf (ชื่อ env)

### คำสั่งเรียกใช้งาน android studio
```
cd Downloads/android-studio/bin
./studio.sh
```

### เช็คการเข้า internet (ในที่นี้เข้าไปใน sanook)   
```
ping sanook
```

### ดูโค๊ตทั้งหมดที่พิพ์ก่อนหน้า
```
history
```
### ดูเวอร์ชั่น python
```
conda python -V
```
### ดู env ทั้งหมดที่มี
```
conda info --envs
```

### ถอนการติดตั้ง anaconda3
```
rm -rf anaconda3
```
### ดูรายชื่อแพ็กเกจที่ติดตั้งบนเครื่องของเรา
```
apt list --installed
```

### วิธีดูเวอร์ชั่น driver การ์จอ
ไปที่ driver manager

### ดูที่อยู่ปัจจุบัน
```
pwd
```
### ดูที่อยู่ไฟล์ที่อยู่บนหน้าจอ
ลากไฟล์นั้นมา แล้ววางบน command line จะได้ที่อยู่ไฟล์นั้นที่มี '' ครอบอยู่
### แสดงรายชื่อไฟล์ในในโฟล์เดอร์นั้นพร้อมรายละเอียด
```
ls -l
```
เช่น  `-rw-rw-r-- 1 boat boat     112 Jan 11 21:34  Command`   
```
- (ถ้าเป็นโฟเดอร์จะเป็น d) แต่ถ้าเป็นขีด จะเป็นไฟล์   
rw-(rwx) u = owner/user   
rw-(rwx) g = gruop
r--(rwx) o = other
```
โดย
```
r = read  = 4
w = write = 2
x = execute(รันโปรแกรม) =1
ถ้าเป้น - แสดงว่าทำไม่ได้ = 0
```
ดังนั้นจึงสามารถบอกมาเป็นตัวเลขก็ได้ เช่น 754(rwxr-xr--) ทั้งหมดนี้เรียกว่า permission
```
boat(ตัวที่ 1) คือ ชื่อเจ้าของ(user)
boat(ตัวที่ 2) คือ ชื่อกรุ๊ป (group)
```
**ถ้าไฟล์เป็นสีเขียว แสดงว่ารันได้**
### แก้ไข permission ของไฟล์
```
chmod เลขpermission3หลัก ชื่อไฟล์
sudo chmod เลขpermission3หลัก ชื่อไฟล์
```
### เพิ่ม permission ของไฟล์ ตามสถานะที่กำหนด
```
chmod สัญลักษณ์สถานะ(เช่น u) + สัญลักษณ์permission(เช่น x) ชื่อไฟล์
```
### ลด permission ของไฟล์ ตามสถานะที่กำหนด
```
chmod สัญลักษณ์สถานะ(เช่น u) - สัญลักษณ์permission(เช่น x) ชื่อไฟล์
```
### เปลี่ยนสถานะของไฟล์จากส่วนบุคคลเป็นกรุ๊ป (เช่น ในเครื่องนี้ชื่อเจ้าของคือ boat จะกลายเป็น root)
```
chown ชื่อเจ้าของ:root ชื่อไฟล์
```

### แสดงไฟล์ในโฟลเดอร์พร้อมข้อมูล (คำจำแสดงเป็น bytes)
```
ls -l
```
### แสดงไฟล์ในโฟลเดอร์พร้อมข้อมูล (คำจำแสดงเป็น K หรือ M bytes)
```
ls -lh
```

### แสดงไฟล์โดยเรียงตามลำดับเวลา (ใหม่ไปเก่า)
```
ls- lht
```

### แสดงไฟล์โดยเรียงตามลำดับเวลา (เก่าไปใหม่)
```
ls- lhtr
```

### แสดง hidden files ด้วย
```
ls -a
```

### แสดงเฉพาะชื่อไฟล์
```
ls-1
```
### แสดงรายชื่อไฟล์ในโฟลเดอร์โดยหาถึงไฟล์ที่อยู่ในสุด
```
ll หรือ ls -al
```
### ลบ hidden file (แต่ไม่สามารถลบ . หรือ .. ออกได้)
```
rm .ชื่อไฟล์
```
### ลบคำสั่งเก่าที่เคยพิมพ์ไปทั้งหมด (ctrl+l เป็นการลบแบบหลอก)
```
clear หรือ ctrl+l
```
### สร้างโฟลเดอร์ว่างขึ้นมา
```
mkdir ชื่อโฟลเดอร์
```
### ลบโฟลเดอร์ที่กำหนด
``` 
rmdir ชื่อโฟลเดอร์
```
### ลบโฟลเดอร์ถึงแม้ว่าจะมีไฟล์อยู่ด้านใน
```
rm -r ชื่อโฟลเดอร์
```
### ลบ hidden โฟลเดอร์
```
rm -rf .ชื่อโฟลเดอร์
```
### แสดงข้อความในไฟล์นั้น
```
cat ชื่อไฟล์
```
### แสดงข้อความในไฟล์นั้น (แสดงเลขบรรทัดของไฟล์ด้วย)
```
cat -n ชื่อไฟล์
```
### แสดงข้อความ 10 บรรทัดสุดท้ายของไฟล์นั้น
```
tail ชื่อไฟล์
```
### แสดงข้อความ 4 บรรทัดสุดท้ายของไฟล์นั้น
```
tail -4 ชื่อไฟล์
```
### แสดงข้อความ 10 บรรทัดแรกของไฟล์นั้น
```
head ชื่อไฟล์
```
### วิธีใช้ nano
1. nano ชื่อไฟล์
แก้ไขข้อความในไฟล์นั้น  (ถ้าสร้างไฟล์ใหม่แล้วแก้ไขเลย ก็ใส่ชื่อไฟล์ใหม่ไปแทนก็ได้)
2. ถ้าต้องการ save แล้วออก ให้กดปุ่ม ctrl+x
3. กด y เพื่อ save 
4. หลังจากนั้น โปแกรมจะถามว่าให้ save เป็นชื่อไฟล์นี้เดิมมั้ย  ถ้าใช่ก็กด enter ไปเลย (หากต้องการเปลี่ยนชื่อไฟล์ก็พิมพ์ชื่อใหม่ไปเลย)
touch ชื่อไฟล์
สร้างไฟล์ใหม่
### วิธีใข้ vi
1. vi
2. ถ้าจะออกกกด `shift` + `:`
3. ถ้าต้องการ save กด `wq`
4. ถ้าไม่ต้องการ save กด `q` หรือ `q!`
### สร้างไฟล์ใหม่โดยคัดลองเนื้อหาจากไฟล์เดิม
```
cp ไฟล์เดิม ไฟล์ใหม่
```
### คัดลองไฟล์เดิม โดยให้ไฟล์ใหม่ออกมาจากที่อยู่ของไฟล์เดิม 1 ขั้น
```
cp ไฟล์เดิม ../ไฟล์ใหม่
```
### คัดลองไฟล์เดิมโดยให้ไปอยู่ใน dir ที่กำหนด
```
cp ไฟล์เดิม ที่อยู่ไฟล์ใหม่/
```
### คัดลอกชื่อไฟลืทั้งหมดที่มีคำขึ้นต้นตามที่เราพิมพ์ 
```
cp คำขึ้นต้นชื่อไฟล์*
```
### คัดลองไฟล์ทั้งหมดใน โฟลเดอร์ นั้น แล้ววางลงใน โฟลเอร์ใหม่ ที่อยู่ใน dir เดียวกัน
```
cp -r* ../โฟลเดอร์ ใหม่/
```
```
sudo cp ที่อยู่ไฟล์เดิม ที่อยู่ไฟล์ใหม่
```
```
sudo cp -r ที่อยู่โฟลเดอร์เดิม ที่อยู่โฟลเดอร์ใหม่
```
### ถอยหลังกัลไป1ขั้น
```
cd ..
```
### ถอยหลังกัลไป2ขั้น
```
cd ../..
```
### หา dir ที่ชื่อเป็นตัวอักษรด้านหน้าที่เราพิม์
```
cd / ตัวอักษรด้านหน้า + กดแท็บ2ครั้ง
```
### ย้ายไฟล์เดิม โดยให้ไฟล์ใหม่ออกมาจากที่อยู่ของไฟล์เดิม 1 ขั้น
```
mv ไฟล์เดิม ../ไฟล์ใหม่
```
### เปลี่ยนชื่อไฟล์
```
mv ไฟล์เดิม ไฟล์ใหม่
```
### ลบไฟล์(ไม่สามารถลบโฟลเดอรืได้)
```
rm ชื่อไฟล์
```
### ลบไฟล์ทั้งหมดในโฟลเดอร์นั้น
```
rm -dr ชื่อโฟลเอร์
```
### ลบโฟลเดอร์
```
rm -d ขื่อโฟลเอร์
```
### พิมพ์ข้อความลงบนหน้าจอ
```
echo ข้อความ
```
### เก็บ out put ของคำสั่งที่พิมพ์ลง command ลงในไฟล์ที่กำหนด (ถ้ามีข้อมูลในไฟล์นั้นอยู่แล้ว ข้อมูลเก่าจะถูกลบไป แล้วใส่ข้อมูลใหม่แทน)
```
คำสั่ง > ชื่อไฟล์.txt
```
### เก็บ out put ของคำสั่งที่พิมพ์ลง command ลงในไฟล์ที่กำหนด (ถ้ามีข้อมูลในไฟล์นั้นอยู่แล้ว จะใส่ข้อมูลใหม่ต่อท้ายข้อมูลเดิม)
```
คำสั่ง >> ชื่อไฟล์.txt
```
### บันทึกข้อความทที่แสดงบน command (เมื่อเลิกบันทึกให้พิมพ์ exit)
```
script 
```
### ดูคู่มือวิธีการใช้งานคำสั่งนั้น
```
man คำสั่ง
```
### ดูวิธีการใช้งานคำสั่งนั้น (ให้ข้อมูลน้อยกว่า man)
```
คำสั่ง -h หรือ ตำสั่ง --help
```
### เพื่อดูว่ามีพื้นที่ไฟล์ ใช้ไปเท่าไหร่ เหลืออีกเ่ทาไหร่ (ค่าจริงที่ใช้ได้)(ถ้าเป็น df -h, df -lh ก็จะแสดงค่าแบบ human read)
```
df
```
### เพื่อดูว่ามีพื้นที่ไฟล์ ใช้ไปเท่าไหร่ เหลืออีกเ่ทาไหร่ (ค่าตามสเปก)
```
df -H
```
### เช็คขนาดไฟล์ /โฟลเดอร์
du ชื่อไฟล์/โฟลเดอร์

### ค้นหาตำแหน่งคำที่ต้องการหาในๆฟล์นั้น (จะแสดงทุกอหน้าที่มีคำนั้นออกมา)
```
grep คำที่ต้องการค้นหา ชื่อไฟล์
```
### เปลี่ยนรหสัผ่านใหม่
```
passwd
```
กรณีเราเป็น root
```
passwd root
```
ถ้าเป็น user ที่มี sudo
```
sudo passwd root
```
### ดูว่ามี user ไหนล็อกออนอยู่บ้าง
```
who
```
### ดูว่าเราล็อกออนอยู่ใน user ไหน
```
whoami
```
### หาดูว่ามีโปรแกรมนี้อยู่ให้ติดตั้งจริงมั้ย
```
sudo apt search ^ชื่อโปรแกรม
```
### หาดูว่ามีโปรแกรมที่มีคำที่เราใส่ไปอยู่ให้ติดตั้งจริงมั้ย
```
sudo apt search ชื่อโปรแกรม
```
### ติดตั้งแพ็กเกต
```
dpkg ชื่อเพ็กเกต
```
### แสดงแพ็กเกตที่ติดตั้งแล้วในเครื่อง
```
dpkg --get-selections
```
### กรองรายการแพ็กเกต โดยแสดงเฉพาะแพ็กเกตที่มีคำที่เรากำลังค้นหา
```
dpkg --get-selections | grep คำที่ต้องการค้นหา
````
### ลิสต์ process ออกมาทั้งหมด (ถ้าต้องการกรองก็ใส่ | grep ไป)
```
ps ax
```
### process ที่ทำอยู่นะปัจจุบัน
```
top
```
### ดูบริการในเครื่อง (ของ syetem d)
```
systemctl 
```
### ดูสถานะของบริการมี่ต้องการ
```
sudo systemctl status ชื่อบริการ
```
### สั่งเปิดบริการที่ต้องการ
```
sudo systemctl start ชื่อบริการ
```
### สั่งปิดบริการที่ต้องการ
```
sudo systemctl stop ชื่อบริการ
```
### รีสตาร์(ปิดแล้วเิดใหม่) บริการ
```
sudo systemctl restart ชื่อบริการ
```
### โหลดการัปเดตบริการนั้นใหม่อีกครั้ง
```
sudo systemctl reload ชื่อบริการ
```
### ดูบริการในเครื่อง (ของ syetem v)
```
service
```
### ดูสถานะของบริการมี่ต้องการ
```
service ชื่อบริการ status
```
### ส่งปิดบริการที่ต้องการ
```
service ชื่อบริการ stop
```
### ดูว่าเครื่องดเรามี network caed อะไรบ้าง id อะไร
```
ip addre หรือ ip address หรือ ip a
```
### ดูว่าเครื่องดเรามี network caed อะไรบ้าง id อะไร  หรือดู ip adress ของเครื่องเรา
```
ifconfig
```
```
curl ifconfig.me
```
### ดูเลข ip adress ของเครื่อง
```
ip route
```
### ดูสถานะของเลข ip นั้น (จะตรวจสอบจนกว่าเราจะสั่งหยุด)
```
ping เลขip adress 
```
### ดูสถานะของเลข ip นั้น (จะตรวจสอบจนกว่าครบจำนวนที่เรากำหนด)
```
ping เลขip adress -cจำนวนครั้งที่ต้องการให้ตรวจสอบ
```
### เช็คสถานะของการเชื่อมต่อ
```
netstat
```
### ดูหนายเลขบริการของเว็บไซต์นั้น เช่น google.com
```
nslookup ชื่อเว็บไซต์
```
### แก้ไขข้อมูล text ในไฟล์
```
nano ชื่อไฟล์
```
ถ้าต้องการบันทึกให้ `Ctl+o`  จากนั้นจะให้ confirm ชื่อ file และกด `enter`
`Ctl+k` เพื่อตัดบรรทัดที่ต้องการ และ ` Ctl+u` เพื่อวาง
` Ctl+w` เพื่อค้นหาคำต้องการโดยจะแสดงคำแรกสุดที่หาเจอ (กรณีที่เจอคำที่เราต้องการค้นหามากกว่า 1 จุด)   
 ---
### ตรวจสอบข้อมูลการ์ดจอ
```
nvidia-smi 
```
---
### ดูการทำงานของ ram ในเครื่อง
```
htop
```
สามารถเลื่อนแถบไปยังกระบวนการที่ต้องการแล้วกด `f9` เพื่อ kill ได้   
กด `f3` เพื่อหาคำสั่งที่ต้องการ   
กด `f10` เพื่อออกจากหน้านี้ หรือ `esc` ก็ได้

---
### สร้าง screen เพื่อแยกกระบวนการทำงาน
```
screen -S ชื่อscreen
```
---
### เข้าใช้งาน screen ที่เราเคยสร้างขึ้นไว้
```
screen -r screen
```
---
### ตรวจสอบรายชื่อ screen ที่เรามีอยู่
```
screen -ls
```
---
### ทำลาย screen
```
screen -S ชื่อscreen -X quit
```
```
screen -X -S ชื่อscreen quit
```
### ตรวจพื้นที่เก็บในโฟลเดอร์
```
du -h -s ชื่อโฟลเดอร์
```
### เช็คพื้นที่เก็บ   
```
df -h
```
### ดาวน์โหลดข้อมูลจากเครื่องหนึ่งไปยังอีกเครื่องหนึ่ง (สั่งในเครื่องที่เราต้องการนำข้อมูลลง)  
```
scp เครื่องที่มีข้อมูล ที่อยู่ของโฟลเดอร์ที่เราจะเก็บในเครื่องเรา   
```
เช่น   
```
scp student2020_nuttaset@LSTGPU:/home/student2020_nuttaset/Translation Downloads
```
### อัพโหลดข้อมูลจากเครื่องหนึ่งไปยงอีกเครื่องหนึ่ง (สั่งในเครื่องที่มีข้อมูลที่ต้องการอัพโหลด)
```
scp เครื่องที่มีข้อมูล ที่อยู่ของโฟลเดอร์ที่เราอัพโหลดไปยังเครื่องอื่ร
```
เช่น   
```
scp KCN_WORKING/LSTcorpus/MT/All_Language_Corpus.xlsx student2020_nuttaset@10.99.5.197:fairseq
```
### อัพโหลดข้อมูลขึ้นไปบน EC2 ของ AWS (ให้สั่งในเครื่อง server ของเรา)
ตามตัวอย่างเป็นกรณีที่ไฟล์ .pem (ได้มาตอนสร้าง EC2) มีชื่อว่า amazon.pem ซึ่งเก็บไว้ในโฟลเดอร์ Desktop  และต้องการโหลข้อมูลที่ชื่อว่า MS115.txt ซึ่งอยู่หน้า Desktop ส่งไปยังเครื่อง server ที่มีชื่อว่า ubuntu@ec2-54-166-128-20.compute-1.amazonaws.com ในโฟลเดอร์ data   
สามารถดูเพิ่มเติมได้ที่ [link นี้](https://angus.readthedocs.io/en/2014/amazon/transfer-files-between-instance.html)
```
scp -i ~/Desktop/amazon.pem ~/Desktop/MS115.txt  ubuntu@ec2-54-166-128-20.compute-1.amazonaws.com:~/data/
```
### เพิ่ม user ในเครื่อง พร้อมให้สิทธิ์ sudo
```
sudo adduser foo sudo
```
การณีเราเป็น root
```
sudo adduser foo
```
### Set Up SSH Keys
[link](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-20-04#step-3-%E2%80%94-authenticating-to-your-ubuntu-server-using-ssh-keys)
### ปลดล็อก zip ไฟล์
```
sudo unzip ชื่อzipไฟล์
```
### นำไฟล์ หรือโฟลเดอร์รวมเป็น zip ไฟล์
```
zip -r ชื่อzipไฟล์(ที่จะสร้าง) ไฟล์1 ไฟล์2 โฟลเดอรื
```
ดูเพิ่มเติมได้ที่ [ลิงค์นี้](https://itsfoss.com/linux-zip-folder/#:~:text=Zip%20a%20folder%20in%20Ubuntu%20Linux%20Using%20GUI&text=Go%20to%20the%20folder%20where,a%20single%20file%20as%20well.)
