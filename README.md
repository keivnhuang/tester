# vApp Templates Guide
This repository contains the vApp Templates, guide documentation and some notice.
See the office documentation on [pubs.vmware.com]

-[Add a vApp Templates to My Cloud](#Add-a-vApp-Templates-to-My-Cloud)
-[Upload an OVF Package/ISO package as a vApp Template](#Upload-an-OVF-Package/ISO package-as-a-vApp-Template)
-[Save a vApp as a vApp Templates](#Save-a-vApp-as-a-vApp-Templates)
-[Modify vApp Templates Prerequisites](#Modify-vApp-Templates-Prerequisites)

## Add a vApp Templates to My Cloud
You can add a vApp template as a vApp from your catalog to My Cloud.
You are at least a vApp author.
If the vApp template is based on an OVF file that includes OVF properties for customizing its virtual machines, those properties are passed to the vApp. If any of those properties are user-configurable, you can specify the values.
### Prerequisites
A vApp template is available in a published or a locally shared catalog.
### Procedure
1. Click __Catalogs__.
2. In the left pane, click on a catalog option.
  + My Organization's Catalogs
  + Public Catalogs
3. On the vApp Templates tab, select a vApp template, right-click, and select Add to My Cloud.
4. Type a name and optional description for the vApp.
5. Select a runtime and storage lease and click Next.
6. Select a virtual datacenter, configure the virtual machines in the vApp, and click Next.
7. Configure the custom properties, if any, and click Next.
8. Configure the networking options for the vApp and click Next.
9. Review the vApp summary information and click Finish.
vCloud Director creates a vApp on the My Cloud > vApps page.
### Related Command and Caution
1. yum install open-vm-tools
2. check status, systemctl -a |grep vmtool

 `vmtoolsd.service`                                                                                                                 
`loaded    active   running   Service for virtual machines hosted on VMware`

3. Firefox version 18.0.1 

## Upload an OVF Package/ISO package as a vApp Template
You can upload an OVF package from remote shares and your local directory to vCloud Director as a vApp template.
You are at least a catalog creator.
vCloud Director supports OVFs based on the Open Virtualization Format (OVF) Specification. If you upload an OVF file that includes OVF properties for customizing its virtual machines, those properties are preserved in the vApp template.
### Prerequisites
  + The computer from which you are uploading must have Java Plug-in 1.6.0_10 or later installed.
  + For information about creating OVFs, see the OVF Tool User Guide and VMware vCenter Converter 4.0.1 User's Guide.
  + vCloud Director does not support uploading compressed OVF files.
### Procedure
1. Click Catalogs > My Organization's Catalogs.
2. On the vApp Templates tab, click the Upload button.
3. Type the name and path of the OVF file to upload, or click Browse, select the OVF file, and click Upload.
4. Type a name and optional description for the vApp template.
5. Select a destination vDC and catalog.
6. Click Upload.
### What to do next
Verify that VMware Tools is installed in each virtual machine in the vApp. See [Installing VMware Tools in a vApp].


## Save a vApp as a vApp Templates
You can save a vApp to a catalog as a vApp template.
You are at least a vApp author.
### Prerequisites
  + Your organization has a catalog and a vDC with available space.
  + The vApp must be stopped.
### Procedure
1. Click My Cloud.
2. In the left pane, click vApps.
3. Right-click a vApp and select Add to Catalog.
4. Type a name and optional description for the vApp template.
5. Select a vDC, a catalog, and a storage lease.
6. Select a vApp creation option.
This option applies when creating a vApp based on this template. It is ignored when building a vApp using individual virtual machines from this template.

|Option                                |Description                         |
|:------------------------------------:|------------------------------------|
|Make identical copy                   |vApps that are created from this vApp template must follow the guest operating system settings of the vApp template. If you select this option, and guest customization is enabled, the guest operating system is personalized.|
|Customize VM settings                 |Guest operating system is personalized regardless of the vApp template settings, and the guest operating system is personalized when the vApp is deployed. This option requires that a supported version of VMware Tools be installed on all virtual machines in the vApp. |

7. Click OK.
The vApp is saved as a vApp template and appears in the destination catalog.


## Modify vApp Templates Prerequisites
You can modify some basic properties of a vApp template. To make more advanced changes to a vApp template, add it to My Cloud, make the changes, then add it back to the catalog as a new vApp template.
You are an organization administrator.
### Procedure
1. Click Catalogs > My Organization's Catalogs.
2. On the vApp Templates tab, right-click a vApp template and select Properties.
3. On the General tab, modify the vApp template name and description.
4. Select a vApp creation option.
   This option applies when creating a vApp based on this template. It is ignored when building a vApp using individual virtual machines from this template.
5. Choose whether or not to mark the vApp template as a Gold Master in the catalog.
   If you mark a vApp template as a Gold Master, this information appears in the list of vApp templates.
6. To reset the vApp template storage lease, select the Reset lease check box and select a new storage lease.
7. Click OK.


[pubs.vmware.com]: https://pubs.vmware.com/vcd-51/index.jsp?topic=%2Fcom.vmware.vcloud.install.doc_51%2FGUID-F14315CC-B373-4A21-A3D9-270FFCF0A417.html
[Installing VMware Tools in a vApp]: https://pubs.vmware.com/vcd-51/index.jsp?topic=%2Fcom.vmware.vcloud.users.doc_51%2FGUID-F0826E73-7F9F-489C-B0DB-17C7D742B1AF.html
