# ADO Feature Clone - DevOps Extension

## Introduction 
An extension to Deep clone a Feature and its related child items. The context menu doesn't work on other work item types.

## Getting Started to side load the extension
### Prerequisites
You must have the following permission and installations.
- You're an organization Owner. If you don't have an organization, you can create an organization for free.

- Install [Node.js](https://nodejs.org/).

- Install the extension packaging tool (TFX) by running `npm install -g tfx-cli` from a command prompt.

### Package and publish your extension
All extensions, including extensions from Microsoft, are under a publisher. Anyone can create a publisher and publish extensions under it. 
Sign in to the Visual Studio [Marketplace management portal](https://aka.ms/vsmarketplace-manage)

If you don't already have a publisher, you'll be prompted to create one.

![Publisher Name Change](images/publisher-snap-01.png)

In the Create Publisher form, enter your name in the publisher name field. The ID field should get set automatically based on your name:

### Package your extension
- Clone the extension repo or download the archive.
- Extract the archive to a folder named `D:\ADO Clone Feature`.
- Open command prompt with Admin access and navigate to above folder.
- Open your extension manifest file `vss-extension.json` and set the value of the publisher field to the ID of your publisher
  ![Publisher Name Change](images/publisher-snap-02.png)

- VSS Web Extensions SDK requires TFX. If you haven't already installed it, open a command prompt and run the following command.
  ```
  npm install -g tfx-cli
  ```

- From a command prompt, run the TFX tool's packaging command from your extension directory to package your extension
  ```
  npx tfx-cli extension create
  ```
- When it's completed, you see a message indicating your extension has been successfully packaged:
  ```
  === Completed operation: create extension ===
  VSIX: D:\ADO Clone Feature\AnnetteNielsen.clone-extension-1.0.0.vsix
  Extension ID: clone-extension
  Extension Version: 1.0.0
  Publisher: AnnetteNielsen
  ```

  ### Upload your extension to Marketplace
  1. From the [Marketplace management portal](https://aka.ms/vsmarketplace-manage), select your publisher from the drop-down at the top of the page.

  2. Select `New extension`, and then select `Azure DevOps`.
     ![Select New Extension](images/marketplace-snap-01.png)

  3. Drag and drop your file or select it to find your VSIX file, which you created in the previous packaging step, and then choose Upload.
    ![Upload Extension](images/marketplace-snap-02.png)

  4. After a few seconds, your extension appears in the list of published extensions. Don't worry, the extension is only visible to you.
    ![Published Extension](images/marketplace-snap-03.png)

### Installing the extension
Installing requires being the owner of the organization (or having the necessary permissions). Because your extension is private, it must first be shared with the organization you want to install it to.

1. From the management portal, select your extension from the list, right-click, and choose Share/Unshare or Publish/Unpublish, depending on the extension; Share = Publish and Unshare = Unpublish.

    ![Install](images/install-01.png)

2. Select Organization, and then enter the name of your organization. Select Enter.
   ![Share Extension](images/install-02.png)

3. Close the panel. The extension can now be installed into this organization. Click `View Extension`
   ![View Extension](images/install-03.png)

4. In the Marketplace, select your extension to open its `Overview` tab.
   ![Overview](images/install-04.png)

5. Select `Get it free`
   ![Get it Free](images/install-05.png)

6. Then Select `Install`.

### Trying the extension

This extension adds `Clone Feature` as an extra option to the context menu of `Boards->Backlogs` and `Boards->Queries`

**Boards Backlogs**

![Backlogs](images/screen1.png)

**Boards Queries**

![Queries](images/screen1.png)