# Azure Workload Identity Implementation: Building Secure Application Access

## Project Goal
This project involves implementing an Azure workload identity for an application to securely access resources. The key objectives are:

1. Understanding what workload identities are.
2. Creating an identity for a robot helper (application).
3. Granting permissions to perform a specific task.
4. Testing and troubleshooting the setup.

---

## Steps

### 1. Navigate to Entra ID
Access the Azure portal and search for **Entra ID**.

![image](https://github.com/user-attachments/assets/8209ef17-1397-46b4-a11a-60967bbecc80)

### 2. Register the Application
- Go to **App registrations** and click **New registration**.

![image](https://github.com/user-attachments/assets/dcbf3356-7b55-4861-af70-c35462ba323d)

- Fill out the application details:
  - **Name**: Enter a meaningful name.
  - **Supported Account Types**: Choose the appropriate option.
  - Leave the **Redirect URI** blank for now.

![image](https://github.com/user-attachments/assets/2e53fe35-9470-4b8c-897a-2c8c8010caf5)

- Take note of the **Application (client) ID** and **Directory (tenant) ID** for later use.

![image](https://github.com/user-attachments/assets/96dc42df-232e-448e-8677-53454b09563a)

### 3. Add Permissions to the Workload Identity
- Navigate to the application you just created.

![image](https://github.com/user-attachments/assets/709f66ce-335a-4628-9421-ca458f121a63)

- Under the **Manage** tab, select **API permissions**.

![image](https://github.com/user-attachments/assets/963c036d-053c-49c0-990d-ee7182d59570)

- Click **Add permission** > **Microsoft Graph** > **Application permissions** > Select **File.Read.All**.

![image](https://github.com/user-attachments/assets/bf56168a-2a61-4219-96bd-94c1576b9467)

### 4. Create a Secret or Certificate for the Application
- Navigate to **Certificates & Secrets** > **Add new client secret** > **Add client secret**.

![image](https://github.com/user-attachments/assets/61cae599-0abc-4d5d-9325-6b677e9cc56b)

- Copy the **Client Secret** value for later use.

![image](https://github.com/user-attachments/assets/218bf7fd-2972-4eaa-8c03-4c74698421fb)

### 5. Assign the Workload Identity to a Resource
- Navigate to Azure Storage and create a storage account for the robot to access.

![image](https://github.com/user-attachments/assets/277c7c83-7ae2-4c9e-b9eb-72f6b0e4dc85)

- Go to the newly created resource and select **Access Control (IAM)** > **Add role assignment**.

![image](https://github.com/user-attachments/assets/0d642b4b-bcd1-4a29-9a2d-3c3008d102a7)

- Choose **Storage Blob Data Reader**.

![image](https://github.com/user-attachments/assets/f0fbacd1-ceb6-4a09-b100-bba41ba3021f)

- Add the robot as a service principal.

![image](https://github.com/user-attachments/assets/26650945-cfb6-40dc-9f18-0f64601ecffe)

### 6. Create a Container in Storage
- Create a container in the storage account.

![image](https://github.com/user-attachments/assets/53acdd4b-6537-40be-b059-c1a0c48a70cc)

- Upload an image or file to the container.

![image](https://github.com/user-attachments/assets/37b448ad-2fcc-4939-9d9e-297af53924f8)

### 7. Test the Robot's Access
- Use the Azure CLI to test if the robot can access the storage account with its identity and permissions.

![image](https://github.com/user-attachments/assets/c9713070-a3ba-4f38-9a2e-9279ccfd4c10)

- Attempt to read the storage using the **Client ID** and **Client Secret** saved earlier.

- Confirm successful access to the file.

![image](https://github.com/user-attachments/assets/48a02c0e-c19b-4be6-9e63-3a0ae6fcb2fa)

---

## Final Report

### Project Outcomes
- Successfully implemented an Azure workload identity for secure access.
- Granted specific API permissions and verified resource access.
- Ensured the robot could perform its designated task.

### Skills Gained
- Practical experience with Azure App Registrations.
- Understanding of workload identities and their applications.
- Troubleshooting Azure permissions and access issues.






























