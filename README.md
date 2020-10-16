# Step to Create, deploy & undeploy hotfix


------------


# Creating the Hotfix.zip
1.   Create the startfix for the issues to be fixed in this patch.
2.  Check-in changes in the Startfix.
3.  Identifiy the impacted Binary files due to solution for hotfix.
4. Configure the impacted SRVPGM and/or PGM in the **"config.properties"** of the propect hotfix.
5. Deedee will pick this startfix onto her build machine and will start the Build for AIX/OS400 Machine 
6. Once the Build is sucessful for the desired files.
7. Deedee Will run the make hotfix.jar from ${HOTFIX_DIR}\ for Win64. This build machine should be able to connect to AIX/OS400 Build machine.
8. Previous step will create a "hotfix.zip" file that could be used to apply the Hotfix.This will be single file for Hotfix Delivery.

------------


# Deploying Hotfix.zip
## Prequisite 
1. Windows Machine from you should have connectivity to target OS400 machine.
2. Environment Variable "JAVA_HOME" should be on Windows machine 
as below
            set JAVA_HOME=${JDK_DIR}\bin
			
## Deployment Process
1. Extract the **"Hotfix.zip"**
2. Move to extracted hotfix folder.
3. Run **"runPatchFix.bat"** from this folder, it will prompt for target OS400 machine,   username (previliged user) & password as below previliged user
                
				Enter a OS400 Target machine IP/Hostname : <Hostname>
				Enter a UserID : <Username>
				Enter a Password : <password>
                
4. This will start deploying the Hotfix on target machine. 

------------


# Undeploy/Rollback Hotfix.
## Prequisite 
1. Windows Machine from you should have connectivity to target OS400 machine.
2. Environment Variable "JAVA_HOME" should be on Windows machine 
as below
            set JAVA_HOME=${JDK_DIR}\bin
3. Hotfix should have been already deployed on target machine.

## Rollback Process
1.  Move to extracted hotfix folder.
2.  Run **"rollback.bat"** from this folder, it will prompt for target OS400 machine,   username (previliged user) & password as below previliged user

		Enter a OS400 Target machine IP/Hostname : <Hostname>
		Enter a UserID : <Username>
		Enter a Password : <password>

3. This will start rollback the Hotfix from target Os400 machine.

------------
@Author **Dinesh Kumar Kori**
**&copy;** HCL Software PVT. LTD

------------





