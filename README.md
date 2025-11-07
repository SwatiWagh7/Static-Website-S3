# 🌐 Static Website Hosting in Amazon S3

## **Steps to Host a Static Website**

1. **Search for S3** in the AWS Management Console.

2. **Create a new S3 bucket** — make it **public**.

3. **Give a unique bucket name**, for example:
   `mybucket-swatiwagh2121992`

4. Click **Create bucket**.

5. Open your new bucket → click **Upload** → **Add files or folders** → upload any image(s) you want.

6. After upload, click on any **object (file)** to get its **Object URL** (this URL will later be used in your HTML file).

7. Note: This **Object URL will not be publicly accessible** until you apply a **bucket policy**.

8. To make files public:

   * Go to **Permissions → Bucket Policy → Edit**
   * Paste the below JSON policy (replace the bucket name with yours):

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
   ```

9. Click **Save changes**.

10. Now **upload your `index.html` file** into the same bucket.

    * You can create it on your computer using any text editor (Notepad, VS Code, etc.).
    * Copy your HTML code and save the file as **index.html**.

11. Inside the HTML file, **paste the Object URLs** of the uploaded images (so they appear on your webpage).

12. Go to **Properties → Static website hosting** →

    * Enable **Static website hosting**
    * Choose **Host a static website**
    * Set **index.html** as the index document
    * (Optionally add `error.html` for error handling)
    * Click **Save**

13. Copy the **Website endpoint URL** shown — it will look like this:

    ```
    http://mybucket-swatiwagh2121992.s3-website-us-east-1.amazonaws.com
    ```

14. Open that link in your browser — 🎉 your **static website is live!**

    <img width="1056" height="594" alt="image" src="https://github.com/user-attachments/assets/f3536814-6978-400a-bca2-36c362f125b3" />


