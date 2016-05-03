---
author: joshbax-msft
title: NDISTest 6.5 - 1 Machine - SRIOVBasicVerification
description: NDISTest 6.5 - 1 Machine - SRIOVBasicVerification
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c3f87651-b547-4429-8594-4254ef32c9f3
---

# NDISTest 6.5 - 1 Machine - SRIOVBasicVerification


This test does the basic verification of the SRI-OV functionality on the miniport adapter in the presence of vSwitch. This is a single machine job and it needs additional configuration for execution.

-   The machine used for testing should have the Hyper-V server role installed. Also, make sure that you select and install the Hyper-V Module PowerShell management tools during installation.

-   Make sure you that copy a Windows 8 VHD (that you want to use for creating the VM) to the local folder (for example: C:\\VHDs) on the machine under test.

Now, you’re ready to run the SRIOVBasicVerification test.

When you select the job and click ‘Run Selected’, you will get a pop-up like the image shown below for entering additional parameters:

![enter parameters](images/hck-win8-lan-ndistest-sriovbasicverification.png)

The values that the job expects are as follows:

-   VMName – You can give any name for the virtual machine. Please make sure that a virtual machine with the same name does not exist on the test machine already.

-   VHDName – Enter the name of the VHD that you copied to the test machine earlier. For example: Mastervhd.vhd. This vhd will not be deleted from the test machine.

-   VHDPath – Enter the path to the VHD location on the test machine (not on the controller). For example: C:\\VHDs.

## Test details


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Associated requirements</strong></p></td>
<td><p>Device.Network.LAN.SRIOV.SRIOV</p>
<p>[See the device hardware requirements.](http://go.microsoft.com/fwlink/p/?linkid=254483)</p></td>
</tr>
<tr class="even">
<td><p><strong>Platforms</strong></p></td>
<td><p>Windows Server 2012 (x64) Windows 8.1 x64 Windows Server 2012 R2</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected run time</strong></p></td>
<td><p>~2 minutes</p></td>
</tr>
<tr class="even">
<td><p><strong>Categories</strong></p></td>
<td><p>Certification Functional</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type</strong></p></td>
<td><p>Automated</p></td>
</tr>
</tbody>
</table>

 

## Running the test


Before you run the test, complete the test setup as described in the test requirements: [LAN Testing Prerequisites](lan-testing-prerequisites.md).

## Troubleshooting


For troubleshooting information, see [Troubleshooting LAN Testing](troubleshooting-lan-testing.md).

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bp_hck\p_hck%5D:%20NDISTest%206.5%20-%201%20Machine%20-%20SRIOVBasicVerification%20%20RELEASE:%20%284/27/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")



