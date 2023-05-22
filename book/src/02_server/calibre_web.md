# Installing Calibre-Web as a Docker Container

1. Using an FTP client (e.g. Filezilla) create a `books` folder and a `config` folder in a location Container Station can access. By default, `/Container`, `/Multimedia`, and `/Public` should be accessible. In our example setup, we created a folder named `CalibreLibrary` in the `/Multimedia` folder. And within it we nested the `books` and `config` folders.

1. Download our Calibre seed library to your computer at:

    [github.com/PenangScienceCluster/qnap-digital-library](https://github.com/PenangScienceCluster/qnap-digital-library)

1. Copy the contents of the `calibre-seed` folder to the `books` folder created earlier.

1. Once the folders are set up, open Container Station and click on Create. In the search box type in `calibre`. When you see the Docker image `linuxserver/calibre-web` click on the install button.

1. Select the latest image, and click on install. Accept the disclaimer.

1. In the "Create Container" dialog box, click on "Advanced Settings".

1. Select `Shared Folders`.

1. Click the "Add" button above "Volume from host" and in the first column, choose the `config` folder created earlier. Under the `Mount Point` column enter `/config` and make sure the "Write" checkbox is selected.

1. Click the "Add" button above "Volume from host" and in the first column, choose the `books` folder created earlier. Under the `Mount Point` column enter `/books` and make sure the "Write" checkbox is selected.

1. Click on Create when done. Confirm the information is correct in the "Summary" dialog box, and click "OK".

## First-Time Configuration

1. In Container Station's overview tab, start `calibre-web-1` (the default name given unless modified) if not started.

1. Click on the blue hyperlink to bring up the container management box.

1. Click on the URL. It will open Calibre-Web's first time setup page.

1. The default login credentials for the admin user are:

    Username: `admin`

    Password: `admin123`

1. In the Database Configuration dialog box, type in `/books`.

Once completed, you should be seeing books immediately available for reading. Remember to change the admin password to something stronger! 

Congratulations! You now have a working library!
