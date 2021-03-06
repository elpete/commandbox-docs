# Package Lifecycle

## preInstall

Announced prior to installing a package. If a package has additional dependencies to install, each of them will fire this interception point.

**interceptData**

* `installArgs` - Struct containing the following keys used in installation of the package.
  * `ID` - The ID of the package to install
  * `directory` - Directory to install to.  May be null, if none supplied.
  * `save` - Flag to save box.json dependency
  * `saveDev` - Flag to save box.json dev dependency
  * `production` - Flag to perform a production install
  * `currentWorkingDirectory` - Original working directory that requested installation
  * `verbose` - Flag to print verbose output
  * `force` - Flag to force installation
  * `packagePathRequestingInstallation` - Path to package requesting installing.  This climbs the folders structure for nested dependencies.

## postInstall

Announced after an installation is complete.  If a package has additional dependencies to install, each of them will fire this interception point.

**interceptData**

* `installArgs` - Same as `preInstall` above

## preUninstall

Announced before the uninstallation of a package.

**interceptData**

* `uninstallArgs` - Struct containing the following keys used in removal of the package
  * `ID` - ID of the package to uninstall
  * `directory` - The directory to be uninstalled from (used to find box.json)
  * `save` - Whether to update box.json
  * `currentWorkingDirectory` - Path to package requesting removal .  This climbs the folders structure for nested dependencies.

## postUninstall

Announced after the uninstallation of a package.

**interceptData**

* `uninstallArgs` - Same as `preUninstall` above
 
