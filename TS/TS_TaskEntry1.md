* Download and extract MDTRunWithServiceUI.wsf (zip file)

  * https://blogs.technet.microsoft.com/deploymentguys/2015/07/06/script-to-make-serviceui-exe-easier-to-use-for-osd-custom-user-interfaces/
  * Direct: https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/telligent.evolution.components.attachments/01/6127/00/00/03/65/17/75/MDTRunWithServiceUI.zip

* Copy the .wsf script, and your .hta script into the %DeployRoot%\scripts\ folder
  * example: Get-MdtTsClientSelection.hta (stored in %DeployRoot%\scripts\)

* Copy the custom app installer script files into the %DeployRoot%\scripts folder

* Add task step in Task Sequence (New / General / Run Command Line)
  * Command: cscript "%DeployRoot%\scripts\MDTRunWithServiceUI.wsf" /UIExePath:"%SystemRoot%\System32\mshta.exe" /UIExeParam:"%DeployRoot%\scripts\Get-MdtTsClientSelection.hta"
