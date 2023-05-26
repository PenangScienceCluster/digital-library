# Installing Calibre-Web as a Docker Container

## Create Calibre-Web Data Folders

1. Open File Station in QTS.

1. Create a Shared Folder. For Calibre, a folder named `calibre` can be created under DataVol1.

1. In "Configure access privileges for users", give `dockuser` read/write access. Leave the rest as default.

1. In the new `calibre` shared folder, create two folders named `books` and `config`.

1. Get the UID/GID of `dockuser` with `id dockuser` in ssh.

1. Download our Calibre seed library to your computer at:

    [github.com/PenangScienceCluster/qnap-digital-library](https://github.com/PenangScienceCluster/qnap-digital-library)

1. Copy the contents of `calibre-seed/books` folder to the `books` folder created earlier. By navigating into the books folder, the following `rsync` command will copy the folder contents to the right folder:

	`rsync -ahvz . <user>@<hostname>:/share/calibre/books/`

1. Set permissions for the folder to `dockuser` with:

	`sudo chown -R <UID>:<GID> /share/calibre/books`

## Create Calibre-Web Container

1. Open Container Station and click on Create. In the search box type in `calibre`. When you see the Docker image `linuxserver/calibre-web` click on the install button.

1. Select the latest image, and click on install. Accept the disclaimer.

1. In the "Create Container" dialog box, click on "Advanced Settings".

1. In Environment, create two fields, `PUID` and `PGID`, filling in the values of `dockuser` from earlier.

1. Select `Shared Folders`.

	1. Click the "Add" button above "Volume from host" (or "Bind Mount Host Path") and in the first column, choose the `config` folder created earlier. Under the `Mount Point` column enter `/config` and make sure the "Write" (or RW) checkbox is selected.

	1. Click the "Add" button above "Volume from host" and in the first column, choose the `books` folder created earlier. Under the `Mount Point` column enter `/books` and make sure the "Write" (or RW) checkbox is selected.

1. Click on Create when done. Confirm the information is correct in the "Summary" dialog box, and click "OK".

## First-Time Configuration

1. In Container Station's overview tab, start `calibre-web-1` (the default name given unless modified) if not started.

1. Click on the blue hyperlink to bring up the container management box.

1. Click on the URL. It will open Calibre-Web's first time setup page.

1. The default login credentials for the admin user are:

    Username: `admin`

    Password: `admin123`

1. In the Database Configuration dialog box, for the database location type in `/books` or navigate to the `books` folder.

Once completed, you should be seeing books immediately available for reading. Remember to change the admin password to something stronger! 

Congratulations! You now have a working library!
