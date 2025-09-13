# 🗄️ Mini Disk Management Project on AWS EC2 (Ubuntu)

This project demonstrates how to manage storage on an **AWS EC2 Ubuntu instance** by creating, attaching, formatting, and mounting a new **EBS volume**.

---

## 📌 Steps

### **1. Create a New EBS Volume**
1. Go to **AWS Management Console → EC2 → Volumes**.
2. Click **Create Volume**:
   - **Size:** 10 GiB  
   - **AZ:** Same as your EC2 instance (e.g., `ap-south-1a`)  
   - **Volume Type:** General Purpose SSD (gp3)  
3. Click **Create Volume**.

---

### **2. Attach Volume to EC2**
1. Select the created volume.  
2. Click **Actions → Attach Volume**.  
3. Select your EC2 instance.  
4. Device name: `/dev/sdf` (will show as `/dev/xvdf` in Ubuntu).  
5. Click **Attach**.

---

### **3. Connect to EC2**
```bash
ssh -i my-key.pem ubuntu@<public-ip>

---

## 4. Verify Attached Volumes
Check if the new volume is attached properly:
```bash
lsblk
````

✅ Expected output:

```
NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
xvda    202:0    0    8G  0 disk
└─xvda1 202:1    0    8G  0 part /
xvdf    202:80   0   10G  0 disk
```

---

## 5. Create Mount Directory

```bash
sudo mkdir -p /mnt/demo-volume
ls -ltr /mnt
```

---

## 6. Format the New Volume

```bash
sudo mkfs -t ext4 /dev/xvdf
```

⚠️ Warning: This command erases any data on `/dev/xvdf`.

---

## 7. Mount the Volume

```bash
sudo mount /dev/xvdf /mnt/demo-volume
```

---

## 8. Verify with lsblk

```bash
lsblk
```

✅ Output should now show `/mnt/demo-volume`:

```
xvdf    202:80   0   10G  0 disk /mnt/demo-volume
```

---

## 9. Create a Test File

```bash
cd /mnt/demo-volume
sudo touch user-zib
ls user-zib
```

✅ Output:

```
user-zib
```

---

## 10. Check Disk Usage

```bash
df -h
```

✅ Example output:

```
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1      8G   3.2G  4.8G  40% /
/dev/xvdf      9.8G   24K  9.3G   1% /mnt/demo-volume
```

---

## ✅ Final Summary

- Created a **10GB EBS volume**  
- Attached it to **Ubuntu EC2**  
- Formatted with **ext4**  
- Mounted at **/mnt/demo-volume**  
- Created test file **user-zib**  
- Verified with **lsblk, df -h**  

---

