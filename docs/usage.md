# LocalAI Tool User Guide  
## Product Link  
[LocalAI Platform](https://marketplace.huaweicloud.com/intl/hidden/contents/a097f0fb-aa22-4ca4-bc22-c6e3faf0c88e)  

## Product Description  
LocalAI is your complete AI stack for running AI models locally. It’s designed to be simple, efficient, and accessible, providing a drop-in replacement for OpenAI’s API while keeping your data private and secure. 

## Product Purchase  
You can search for "LocalAI" in the cloud marketplace.  
For **Region** and **Specifications**, use the recommended configurations. The **Purchase Method** can be selected based on your needs—**Pay-as-you-go** for short-term use or **Monthly/Yearly** for long-term use. After confirming the configuration, click **"Buy Now"**.  

![alt text](./images/image.png)  

### Deploy Directly Using RFS Template  
![img.png](images/img1.png)  
Fill in the required fields and click **Next**.  
![img.png](images/img2.png)  
![img.png](images/img3.png)  
After creating the deployment plan, click **Confirm**.  
![img.png](images/img4.png)  
![img.png](images/img5.png)  
Click **Deploy** to execute the plan.  
![img.png](images/img6.png)  
The message **"Apply required resource success."** indicates that the resources have been successfully created.  
![img.png](images/img7.png)  

### ECS Console Configuration  
#### Preparations  

Before configuring the ECS console, you need to set up **Security Group Rules** in advance.  

> **Security Group Rules Configuration:**  
> - Allow inbound traffic on port **8080**, ensuring the source IP range includes your client IP; otherwise, access will be denied.  
> - Allow inbound traffic on port **22** for CloudShell connections to enable console debugging.  
> - Enable full outbound traffic.  

#### Creating an ECS  

After completing the preparations, navigate to the [ECS Purchase Page](https://support.huaweicloud.com/qs-ecs/ecs_01_0103.html) via the ECS console. Configure the ECS resources as shown below:  

**Select CPU Architecture**  
![img.png](images/img8.png)  
**Select Server Specifications**  
![img_1.png](images/img_1.png)  
**Select Image**  
![img_2.png](images/img_2.png)  
Fill in other parameters according to your actual needs, then click **Buy Now**.  
![img_3.png](images/img_3.png)  

> **Important Notes:**  
> - You can create a **VPC** yourself.  
> - Select the **Security Group** configured in the [**Preparations**](#preparations) section.  
> - For **Elastic Public IP**, select **"Purchase Now"** and choose **"Pay-by-Traffic"** (recommended). Set the bandwidth to **5Mbit/s**.  
> - **Advanced Configuration** requires custom data injection, so **Login Credentials** cannot be set as **"Password"**—select **"Set After Creation"** instead.  
> - Other settings can be left as default or configured as needed.  

## Product Usage  
### Logging into the Server to Start the LocalAI Docker Container  
- After accessing the system, run the following command:  
```shell  
cd ~/localai  
docker run -p 8080:8080 -v $PWD/models:/models -ti --rm localai/localai:v3.0.0 --models-path /models  
```  
![alt text](./images/image.png)  

- Access the LocalAI platform via browser:  
**http://yourIp:8080/**  
![alt text](./images/image2.png)  

### Downloading Models & Loading References (LocalAI Manual)  
[LocalAI Manual](https://localai.io/docs/getting-started/models/)
