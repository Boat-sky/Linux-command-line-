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
### ดูปฏิทิน
```
cal
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
วิธีนี้จะสร้าง env แล้วเก็บ folder env ตัวนี้ไว้ใน path ที่เรารันคำสั่งนี้   
นอกจากนี้ยังสามารถใช้คำสั่ง
```
python3 -m venv ~/ชื่อvenv
```
เพื่อสร้าง env ที่เป็น python3 เก็บไว้ในหน้า home   
2. sourcce (ชื่อ env)/bin/activate   
หรือ   
```
source ~/ชื่อenv/bin/activate
```
สำหรับ env ที่เก็บไว้ที่หน้า home
3. deactivate   
4. sudo rm -rf (ชื่อ env)   
ดูเพิ่มเติมได้ที่ [ลิงค์นี้](https://www.techcoil.com/blog/how-to-use-python-3-virtual-environments-to-run-python-3-applications-on-your-raspberry-pi/)

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
ระบบไฟล์ใน linux
![root_img](https://i.imgur.com/Iv9ypzW.png)
### ควบคุมเครื่องในฐานะ root
```
sudo su
```
หรือ
```
sudo -s
```
### ออกจากฐานนะ root
```
exit
```
หรือ
```
su ชื่อuserของเรา
```
เช่น
```
su boat
```
### เช็คว่ามีใคร login เครื่องเราอยู่บ้าง
```
users
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
rw-(rwx) u = owner/user  (3 ตัวแรก) 
rw-(rwx) g = gruop       (3 ตัวชุดที่สอง)
r--(rwx) o = other       (3 ตัวชุดสุดท้าย)
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

### แสดงไฟล์ในโฟลเดอร์พร้อมข้อมูล (ความจำแสดงเป็น bytes)
```
ls -l
```
```
ll
```
### แสดงไฟล์ในโฟลเดอร์พร้อมข้อมูล (ความจำแสดงเป็น K หรือ M bytes)
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
### แสดงจำนวนไฟล์ที่อยู่ใน folder
```
ls ชื่อโฟลเดอร์ | wc -l
```
### แสดงรายละเอียดสิ่งที่อยู่ใน dir นั้น
```
file ชื่อสิ่งที่เราต้องการดูรายระเอียด
```
เช่น
```
(base) boat@boat-pc:~/Downloads$ file cute.jpg
cute.jpg: JPEG image data, progressive, precision 8, 960x540, components 3

(base) boat@boat-pc:~/Downloads$ file CV.docx
CV.docx: Microsoft Word 2007+

(base) boat@boat-pc:~/Downloads$ file scaner
scaner: directory
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
### แสดงข้อความในไฟล์นั้น (แบบขึ้นหน้าใหม่ และสามาถลื่นขึ้นลง ดูแต่ละส่วนได้)
เหมาะกับกรณีที่ข้อความในไฟล์นั้นยาวมากๆ
```
less ชื่อไฟล์
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
### แสดงข้อความ 5 บรรทัดแรกของไฟล์นั้น
```
head -n 5 ชื่อไฟล์
```
### แสดงผลของคำสั่งออกมาเต็มหน้าจอ
```
watch คำสั่ง
```
### หาไฟล์ทั้งหมดทุกที่จากคำค้นหา
```
locate คำค้นหา(เช่นชื่อไฟล์ โฟลเดอร์)
```
### อัปเดต database
```
sudo updatedb
```
### หาที่อยู่ไฟล์โปรแกรมที่เราติดตั้ง
```
which ชื่อโปรแกรม
```
เช่น (แต่ถ้าไม่มีโปรแกรมชื่อนั้น จะไม่ขึ้นอะไรเลย)
```
(base) boat@boat-pc:~$ which discord
/usr/bin/discord
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
1. vi ตามด้วยชื่อไฟล์ เช่น
```
vi test.txt
```
โดยถ้าไม่มีชื่อไฟล์นี้อยู่ vim จะสร้างไฟล์ใหม่ชื่อนี้ให้
2. ถ้าต้องการแก้ไขกดปุ่ม i ตรงด้านล่างจะปรากฏข้อความ `-- INSERT--`   
3. เมื่อแก้ไขเสร็จแล้วกดปุ่ม `esc` เพื่อออกจากโหมดแก้ไข      
4. กด `:w` แล้วกด `enter` เพื่อบันทึกสิ่งที่แก้ไขไป      
5. กด `:q` แล้วกด `enter` เพื่อออกจากหน้านี้   
หากต้องการออกจากหน้า โดยไม่บันทึกสิ่งที่แก้ไข สามารถกดปุ่ม `:q!`   
และหากต้องการที่จะบันทึก และออกในคำสั่งเดียวกัน สามาถกดปุ่ม `:wq`   
หากเราอยู่ใน normal mode (ไม่ได้กดปุ้่ม `i` เพื่อเข้าไปแก้ไขที) สามรถใช้คำสั่งได้ต่อไปนี้
1. ลบ/ตัด บรรทัดนั้นโดยการไปที่บรรทัดนั้นแล้วกดปุ่ม `d` สองครั้ง
2. หากต้องการวางบรรทัดใหม่ด้านล่สงบรรทัดที่กำหนด ไปที่บรรทัดนั้นแล้วกดปุ่ม `p` เพื่อวาง
3.undo สิ่งที่ทำโดยการกดปุ่ม `u`
4. ขึ้นไปบรรทัดบนสุดของไฟล์ กดปุ่ม `g` สองครั้ง
5. ลงไปบรรทัดล่างสุดของไฟล์ กดปุ่ม `shift` ค้างไว้ แล้วกดปุ่ม `g` สองครั้ง
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
### คัดลองไฟล์ทั้งหมดใน โฟลเดอร์ นั้น แล้ววางลงใน โฟลเอร์ใหม่ ที่อยู่ใน dir ก่อนหน้า
```
cp -r โฟลเดอร์เก่า/* ../โฟลเดอร์ ใหม่/
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
### ย้ายไป dir ใหม่ โดยบันทึก dir ที่เคยอยู่ก่อนหน้านี้
```
pushd dirใหม่ที่ต้องการไป
```
เราสามารถกลับไป dir ล่าสุดก่อนหน้านี้ได้โดย ได้โดย
```
pushd
```
### ย้ายไป dir เดิมที่เคยเข้ามาก่อนหน้านี้
```
popd
```
เมื่อใช้คำสั่งนี้ จะเครื่องจะพิมพ์ประวัติการเข้า dir อื่นก่อนหน้านี้ที่เรายังไม่ได้กลับไปอีกด้วย   
โดย pushd และ popd จะใช้งานร่วมกัน เช่น
```
(base) boat@boat-pc:~/Downloads$ pushd /etc
/etc ~/Downloads

(base) boat@boat-pc:/etc$ pushd /bin
/bin /etc ~/Downloads

(base) boat@boat-pc:/bin$ pushd
/etc /bin ~/Downloads

(base) boat@boat-pc:/etc$ popd
/bin ~/Downloads

(base) boat@boat-pc:/bin$ popd
~/Downloads

(base) boat@boat-pc:~/Downloads$ 
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
### ดูว่าคำสั่งนี้ไว้ใช้ทำอะไร
```
whatis คำสั่ง
```
### ดูคู่มือวิธีการใช้งานคำสั่งนั้น
```
man คำสั่ง
```
### ดูวิธีการใช้งานคำสั่งนั้น (ให้ข้อมูลน้อยกว่า man)
```
คำสั่ง -h 
```
หรือ
```
ตำสั่ง --help
```
### หาคำสั่งอื่นที่เกี่ยวห้องกับคำสั่งนี้ หรือคำค้นหานี้
```
apropos คำสั่งหรือคำค้นหา
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
### ปิดโปรแกรมที่กำลังรันในเครื่อง
```
killall ชื่อโปรแกรม
```
เช่น
```
killall firefox
```
### ลิสต์ process ออกมาทั้งหมด (ถ้าต้องการกรองก็ใส่ | grep ไป)
จะแสดงทรัพยากร  CPU และ RAM ที่ถูกใช้ไปเป็นราย process
```
ps ax
```
### process ที่ทำอยู่นะปัจจุบัน
```
sudo ps -a
```
หรือ
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
### ดู uid ของเรา
```
id
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
### ออกจากหน้า screen ที่อยู่
```
exit
```
หรือกด `Ctrl+a+X `   
ดูเพิ่มเติมได้ที่ [ที่นี่](https://linuxize.com/post/how-to-use-linux-screen/)
### ตรวจพื้นที่เก็บในโฟลเดอร์
```
du -h -s ชื่อโฟลเดอร์
```
### เช็คพื้นที่เก็บ   
```
df -h
```
### ดาวน์โหลดข้อมูลจากเครื่องหนึ่งไปยังอีกเครื่องหนึ่ง (สั่งในเครื่องที่เราต้องการนำข้อมูลลง)  
ชื่อเครื่องที่แท้จริงอาจไม่ใช่ชื่อที่ปรากฏบน command line แต่เป็นชื่อทีเราใช้ตอนเข้า ssh
```
scp option เครื่องที่มีข้อมูล ที่อยู่ของโฟลเดอร์ที่เราจะเก็บในเครื่องเรา   
```
เช่น
```
scp student2020_nuttaset@LSTGPU:/home/student2020_nuttaset/Test.txt Downloads/test
```
```
scp student2020_nuttaset@LSTGPU:/home/student2020_nuttaset/Translation Downloads
```
ในกรณีที่เป็น folder ให้ใส่ -r นำหน้าด้วย (บางทีก็ต้องใส่ หรือไม่ต้องใส่ แล้วแต่เครื่อง) เช่น
```
scp -r student2020_nuttaset@LSTGPU:/home/student2020_nuttaset/Translation Downloads
```
ถ้าเราต้องการให้โหลดข้อมูลลงใน path ทีเราอยู่ สามมารถใส่ . ต่อท้าย path ของเครื่องต้นทางได้ เช่น
```
scp nkuapani@tara.nstda.or.th:~/Thanks.txt .
```
ถ้าต้องการนำไปลงใน path ก่อนหน้า(1 step) ให้ใส่ .. ตามด้วย path ที่ต้อการใส่
```
scp nkuapani@tara.nstda.or.th:~/Thanks.txt ../My_files/
```
หรือจะเปลี่ยนชื่อไฟล์ที่จะเอามาลง ก็ใส่ชื่อใหม่ไปใน path ท้ายสุดเช่น
```
scp nkuapani@tara.nstda.or.th:~/Thanks.txt Love.txt
```
### อัพโหลดข้อมูลจากเครื่องหนึ่งไปยงอีกเครื่องหนึ่ง (สั่งในเครื่องที่มีข้อมูลที่ต้องการอัพโหลด)
```
scp เครื่องที่มีข้อมูล ที่อยู่ของโฟลเดอร์ที่เราอัพโหลดไปยังเครื่องอื่ร
```
เช่น   
```
scp KCN_WORKING/LSTcorpus/MT/All_Language_Corpus.xlsx student2020_nuttaset@10.99.5.197:fairseq
```
```
scp Hello.txt nkuapani@tara.nstda.or.th:~
```
### อัพโหลดข้อมูลขึ้นไปบน EC2 ของ AWS (ให้สั่งในเครื่อง server ของเรา)
ตามตัวอย่างเป็นกรณีที่ไฟล์ .pem (ได้มาตอนสร้าง EC2) มีชื่อว่า amazon.pem ซึ่งเก็บไว้ในโฟลเดอร์ Desktop  และต้องการโหลข้อมูลที่ชื่อว่า MS115.txt ซึ่งอยู่หน้า Desktop ส่งไปยังเครื่อง server ที่มีชื่อว่า ubuntu@ec2-54-166-128-20.compute-1.amazonaws.com ในโฟลเดอร์ data   
สามารถดูเพิ่มเติมได้ที่ [link นี้](https://angus.readthedocs.io/en/2014/amazon/transfer-files-between-instance.html)
```
scp -i ~/Desktop/amazon.pem ~/Desktop/MS115.txt  ubuntu@ec2-54-166-128-20.compute-1.amazonaws.com:~/data/
```
### อัพข้อมูลส่งไปที่ raspberry pi
```
scp have_mask/Go.txt pi@เลขipของบอร์ด:/home/pi/Desktop/face-mask-decotr/have_mask
```
วิธีเช็คเลข ip สามารถทำได้ด้วยคำสั่ง
```
ifconfig
```
ถ้าต่อ wifi ip จะอยู่ในส่วน
```
wlp5s0
```
แต่ถ้าต่อสาย LAN จะอยู่ในส่วน
```
eth0 
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
### เปิดไฟล์ .gz
```
gunzip file.gz
```
หรือ
```
gzip -d file.gz
```
### เปิดไฟล์ .tar.gz
```
tar -zxvf file.tar.gz
```
### เปิดไฟล์ .tar
```
tar -xvf file_name.tar
```
### เปิดไฟล์ .rpm
```
sudo alien file_name.rpm
```
### เปิดไฟล์ .rar
```
sudo apt-get install unrar
```
ย้ายไฟล์ rar นั้นมาในโฟลเดอร์ใหม่ก่อน ไม่งั้นไฟล์ใน .rar จะไปปนกับไฟล์เดิม
```
unrar e tecmint.rar
```
### สร้าง Python Virtual Environment 
ติดตั้งโมดูล `virtualenv` ถ้าหากใช้ python3 สามารถติดตั้งโดยใช้คำสั่ง
```
pip3 install virtualenv
```
เช็คที่อยู่ของไฟล์ python3 binary ในเวอร์ชั่นที่ต้องการ (สมมมติใช้ python3.8)   
โดยทั่วไปไฟล์นั้นจะอยู่ใร bath
```
/usr/bin/python3.8
```
ถ้าหากหาไฟล์ pyhton3 binary ในเวอร์ชั่นที่ต้องการเจอแล้ว สามารถสร้าง env ด้วยคำสั่ง
```
virtualenv -p /usr/bin/python3.8 ชื่อenvที่ต้องการตั้ง
```
ถ้าต้องการเรียกใช้ก็รันคำสั่ง
```
source ชื่อenv/bin/activate
```
สามารถเช็คว่าตอนนี้ไฟล์ python3 binary ที่เราใช้อยู่มาจากไหน ด้วยคำสั่ง
```
which python
```
ถ้าต้องการออกจาก env นั้น ก็ใช้คำสั่ง
```
deactivate
```
ถ้าต้องการลบ env ก็ใช้คำสั่ง
```
rm -rf ชื่อenv
```
### ดูสถานะ CPU ในเครื่อง
```
mpstat
```
### ดูสถานะของ CPU รายตัว
```
mpstat -P ALL
```
### ถ้าต้องการดูเฉพาะหมายเลข CPU ที่กำหนด
สามารถใส่หมายเลข CPU แทนคำว่า ALL ได้ เช่นต้องการดูเฉพาะ CPU หมายเลข 0
```
mpstat -P 0
```
### แสดงสถานะของ CPU ต่อเนื่องทุกๆกี่วิที่กำหนด และตามจำนวนที่กำหนด
เช่นให้แสดงสถานะ CPU ทุกตัว 4 ครั้ง (จะปรากฏชุดที่ 5 ออกมาด้วย แสดงค่าเฉลี่ยของทั้ง 4 ครั้ง) แต่ละครั้งห่างกัน 2 วินาที
```
mpstat -P ALL -u 2 4
```
### หยุดการทำงานของ process ปัจจุบันผ่าน keyboard (ไม่ใช่การยกเลิก)   
`Ctrl+Z`
### เปลี่ยนการทำงานแบบธรรมดาที่กำลัง run อยู่ ให้กลายเป็น background process1. 
1. กด `Ctrl+Z` เพื่อหยุดการทำงานชั่วครามวก่อน   
2. รันคำสั่ง
```
bg
```
สามารถเช้คคำสั่งที่รันแบบ background process ได้ด้วยคำสั่ง
```
jobs
```
จะมีเครื่องหมาย + ตามหลังหมายเลขของ process ที่เกิดขึ้นใหม่ และ - แทน process ที่สั่งไว้ก่อนหน้า
### รันคำสั่งแบบ background process
เติมเครื่องหมาย `&` ต่อท้ายตำสั่งที่จะรัน เช่น ต้องการรันไฟล์ train_model.py แบบ background process
```
pytohn train_model.py &
```
### สั่งรันให้ทำงานอยู่แม้ปิด terminal
รันแบบ background process ก่อน โดยการเติม `&` ต่อด้านหลังคำสั่ง หลังจากนั้นรันคำสั่ง `disown  -h  %1`   
เช่นรันไฟล์ train_model.py ใช้คำสั่ง
```
pytohn train_model.py &
disown  -h  %1
```
หรือสามารถเติม `nohup` ไว้ด้านหน้าคำสั่งตั้งแต่แรกเลยก็ได้ จะได้
```
nohup python train_model.py &
```
สามารถดูเพิ่มเติมได้ที่ [ลิงค์](https://www.tecmint.com/run-linux-command-process-in-background-detach-process/#:~:text=How%20to%20Start%20a%20Linux,background%20jobs%20by%20typing%20jobs%20.)
### การใช้คำสั่ง snap
ติดตั้ง package โดย package เหล่านี้จะอยู่ใน โฟลเดอร์ snap
```
sudo snap install ชื่อpackage
```
ดูรายการ package ทั้งหมดที่สามารถติดตั้งได้
```
sudo snap find
```
ดูรายชื่อ package ที่ติดตั้งโดยใช้ snap ในเครื่องเรา
```
sudo snap list
```
 ดู list ของ logged actions
 ```
 sudo snap changes
 ```
 อัปเกรด package เป็นเวอร์ชั่นล่าสุด
 ```
 sudo snap refresh ชื่อpackage
 ```
 ถอนการติดตั้ง package
 ```
 sudo snap remove ชื่อpackage
 ```
### list device ทั้งหมดที่ต่อกับ usb ของเรา
ควรใช้คำสั่งนี้ก่อนเสียบ และหลังเสียบ usb เพื่อดูว่า  device อะไรเพิ่มขึ้น จะได้รู้ว่า devide นั้นชื่อว่าอะไร
```
lsusb
```
หากต้องการ reset การเชื่อมต่อ usb ดูได้ที่ [ลิงค์นี้](https://askubuntu.com/questions/645/how-do-you-reset-a-usb-device-from-the-command-line)
### โหลดข่้อมูลจาก google drive ลงเครื่อง (ช่วยให้เร็วขึ้น)
```
./gdown.pl 'gdrive file url' ['desired file name'] 
```
เช่น
```
./gdown.pl https://drive.google.com/file/d/0B1L_hFrWJfRhLUJZdXdSdTdfSWs/edit axolotl.mp4 
```
ดูเพิ่มเติมได้ที่ [link](https://github.com/circulosmeos/gdown.pl/tree/with-resume)
### ตั้งรหัสผ่าน jupyter notebook
```
jupyter notebook password
```
### เช็ค host name ของเครื่องเรา (ชื่อเครื่อง)
```
hostname
```
### เปลี่ยนชื่อเครื่องของเรา
เปลี่ยนชื่อ host name
```
sudo nano /etc/hostname
```
เปลี่ยนชื่อใน hosts
```
sudo nano /etc/hosts
```
รีบูทเครื่อง
```
sudo reboot
```
ดูเพิ่มเติมได้ที่ [link](https://www.cyberciti.biz/faq/ubuntu-change-hostname-command/)
### แปลง png เป็น jpg
ติดตั้งโปรแกรม
```
sudo apt-get install imagemagick
```
แปลงรูปภาพที่ต้องการ
```
convert ubuntuhandbook.png ubuntuhandbook.jpg
```
ดูเพิ่มเติมที่ [ลิงค์นี้](https://ubuntuhandbook.org/index.php/2013/07/how-to-convert-png-to-jpg-on-ubuntu-via-command/)
