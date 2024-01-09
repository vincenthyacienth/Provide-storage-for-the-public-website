# Provide Storage For The Public Website
## Lets take this exercise;
The company website supplies product images, videos, marketing literature, and customer success stories. Customers are located worldwide and demand is rapidly expanding. The content is mission-critical and requires low latency load times. It’s important to keep track of the document versions and to quickly restore documents if they’re deleted.
## Exercise Instructions
## Create A Storage Account With High Availability.
1. Create a storage account to support the public website.
- In the portal, search for and select Storage accounts.
- Select + Create.
- For resource group select new. Give your resource group a name and select OK.
- Set the Storage account name to publicwebsite. Make sure the storage account name is unique by adding an identifier.
- Take the defaults for other settings.
- Select Review and then Create.
- Wait for the storage account to deploy, and then select Go to resource.
2. This storage requires high availability if there’s a regional outage. Additionally, enable read access to the secondary region.
- In the storage account, in the Data management section, select the Redundancy blade.
- Ensure Read-access Geo-redundant storage is selected.
- Review the primary and secondary location information.
3. Information on the public website should be accessible without requiring customers to login.
- In the storage account, in the Settings section, select the Configuration blade.
- Ensure the Allow blob anonymous access setting is Enabled.
- Be sure to Save your changes.
## Create A Blob Storage Container With Anonymous Read Access
1. The public website has various images and documents. Create a blob storage container for the content. 
- In your storage account, in the Data storage section, select the Containers blade.
- Select + Container.
- Ensure the Name of the container is public.
- Select Create.
2. Customers should be able to view the images without being authenticated. Configure anonymous read access for the public container blobs.
- Select your public container.
- On the Overview blade, select Change access level.
- Ensure the Public access level is Blob (anonymous read access for blobs only).
- Select OK.
## Practice Uploading Files And Testing Access.
1. For testing, upload a file to the public container. The type of file doesn’t matter. A small image or text file is a good choice.
- Ensure you are viewing your container.
- Select Upload.
- Browse to files and select a file. Browse to a file of your choice.
- Select Upload.
- Close the upload window, Refresh the page and ensure your file was uploaded.
2. Determine the URL for your uploaded file. Open a browser and test the URL.
- Select your uploaded file.
- On the Overview tab, copy the URL.
- Paste the URL into a new browser tab.
- If you have uploaded an image file it will display in the browser. Other file types should be downloaded.
## Configure Soft Delete
1. It’s important that the website documents can be restored if they’re deleted. Configure blob soft delete for 21 days. Learn more about soft delete for blobs.
- Go to the Overview blade of the storage account.
- On the Properties page, locate the Blob service section.
- Select the Blob soft delete setting.
- Ensure the Enable soft delete for blobs is checked.
- Change the Keep deleted blobs for (in days setting is 21.
- Notice you can also Enable soft delete for containers.
- Don’t forget to Save your changes.
2. If something gets deleted, you need to practice using soft delete to restore the files.
- Navigate to your container where you uploaded a file.
- Select the file you uploaded and then select Delete.
- Select OK to confirm deleting the file.
- On the container Overview page, toggle the slider Show deleted blobs. This toggle is to the right of the search box.
- Select your deleted file, and use the ellipses on the far right, to Undelete the file.
- Refresh the container and confirm the file has been restored.
## Configure Blob Versioning
1. It’s important to keep track of the different website product document versions. Learn more about blob versioning.
- Go to the Overview blade of the storage account.
- In the Properties section, locate the Blob service section.
- Select the Versioning setting.
- Ensure the Enable versioning for blobs checkbox is checked.
- Notice your options to keep all versions or delete versions after.
- Don’t forget to Save your changes.
2. As you have time experiment with restoring previous blob versions.
- Upload another version of your container file. This overwrites your existing file.
- Your previous file version is listed on Show deleted blobs page
