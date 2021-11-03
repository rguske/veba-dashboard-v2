# vRealize Operations Manager Dashboard v2 for project VMware Event Broker Appliance

## Prerequisites vRealize Operations Manager

- **Dashboard is not compatible with vROps 8.6 at the moment!**
- Dashboard tested with vROps version 8.5 - [DOWNLOAD](https://customerconnect.vmware.com/downloads/info/slug/infrastructure_operations_management/vmware_vrealize_operations/8_5)
- Install vRealize Operations Management Pack for Kubernetes - [DOWNLOAD](https://marketplace.cloud.vmware.com/services/details/vrealize-operations-management-pack-for-kubernetes-1-5-1?slug=true)
-- Tested with version 1.5.1
- Mgmt Pack for K8s - [DOCS](https://docs.vmware.com/en/Management-Packs-for-vRealize-Operations-Manager/1.5.1/kubernetes-solution/GUID-10599FD5-4519-4B99-90A6-11168693E283.html)

## Add VEBA as a new endpoint to vROps

- How to configure the Adapter Instance in vROps - [DOCS](https://docs.vmware.com/en/Management-Packs-for-vRealize-Operations-Manager/1.5.1/kubernetes-solution/GUID-87AEB0B9-EB85-4DDC-AD31-1AEE1179C4B4.html)

We need to configure Client Certificate Auth as credential kind. To get the data for `Certificate Authority Data`, `Client Certificate Data` as well as for the `Client Key Data` we need to ssh into VEBA. 
- connect via `ssh`
- Execute: 
```
grep 'client-certificate-data\|client-key-data\|certificate-authority-data' ~/.kube/config
```

![veba-adapter-instance-vrops](https://user-images.githubusercontent.com/31652019/136001604-c4ec5bd0-b246-4b87-9a61-f7b946694e66.jpg)

## Configure a Dynamic Custom Group in vROps

To only have your VEBA instances displayed on the dashboard, we have to configure a Dynamic Custom Group in vROps which has a vSphere Tag based membership criteria configured.

- Creation of a Dynamic Custom Group in vROps - [DOCS](https://docs.vmware.com/en/vRealize-Operations-Manager/8.4/com.vmware.vcom.core.doc/GUID-07BA3A0D-0F3D-494A-B4F1-A0381DD837D6.html)

![veba-vrops-custom-group](https://user-images.githubusercontent.com/31652019/136002061-27adab22-805d-4a82-a55b-81734a85d6dc.jpg)

## Import Views as well as the Dashboard

Download the Dashboard and View archives and use the import functions in vROps to import everything. Start with the Views first.

- Import Views - [DOCS](https://docs.vmware.com/en/VMware-vRealize-Operations-Cloud/services/config-guide/GUID-42F41582-E2EE-4BD3-9751-F65C886E1118.html)
- Import Dashboard - [DOCS](https://docs.vmware.com/en/vRealize-Operations-Manager/8.4/com.vmware.vcom.config.doc/GUID-7F96D356-8A1F-40F8-932E-14C952EC78B5.html)

## Ready to monitor

![veba20-dashboard-screenshot](https://user-images.githubusercontent.com/31652019/135988190-806804de-2e3b-4b49-878b-a4eb6f870f3f.png)
