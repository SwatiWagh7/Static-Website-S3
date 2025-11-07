
# 🌐 Static Website Hosting on Amazon S3

This project demonstrates how to **host a static website on AWS S3**, including uploading images, applying public access policies, and enabling static website hosting.

---

## 🧭 Steps to Host a Static Website on S3

### **1. Search for S3 in AWS Console**
- Log in to your AWS account.
- Search for **S3** in the AWS Management Console.

---

### **2. Create a Bucket**
- Click **Create Bucket**.
- Choose a **unique bucket name** (e.g., `mybucket-swatiwagh2121992`).
- Uncheck **Block all public access** to make it **Public**.
- Click **Create bucket**.

---

### **3. Upload Files**
- Open your newly created bucket.
- Click **Upload → Add files**.
- Upload any **images** you want to use on your website.

---

### **4. Get Object URL**
- After uploading, click on an object (image).
- Copy the **Object URL** — you’ll use it later in your HTML file.

> Note: This URL will only work once you apply a public-read policy.

---

### **5. Apply Bucket Policy**
Go to your **Bucket → Permissions → Bucket Policy → Edit**  
Paste the following JSON policy (replace with your bucket name if different):

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::mybucket-swatiwagh2121992/*"
        }
    ]
}
````

Save the policy.

---

### **6. Create and Upload index.html**

* Copy your HTML code and save it as **index.html**.
* In your HTML code, **paste the Object URLs** of your uploaded images.
* Go back to your S3 bucket → **Upload → Add files → index.html**.

---

### **7. Enable Static Website Hosting**

* Go to your **Bucket → Properties**.
* Scroll to **Static website hosting** → Click **Edit**.
* Enable it and set:

  * **Index document:** `index.html`
* Click **Save changes**.

---

### **8. Access Your Website**

Scroll down in the **Static website hosting** section —
You’ll find the **Website URL** at the bottom (something like):

```
http://mybucket-swatiwagh2121992.s3-website-us-east-1.amazonaws.com
```

🎉 Open that URL in your browser — your static website is live!

---

## 🧰 Technologies Used

* **Amazon S3** – Static website hosting
* **HTML5** – Frontend structure
* **AWS IAM Policy** – Public access configuration

---

## 📁 Example Project Structure

```
📁 s3-static-website
 ┣ 📜 index.html
 ┣ 🖼️ image1.jpg
 ┣ 🖼️ image2.png
 ┗ 📜 README.md
```

---


