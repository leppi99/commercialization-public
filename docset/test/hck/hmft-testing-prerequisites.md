---
author: joshbax-msft
title: HMFT Testing Prerequisites
description: HMFT Testing Prerequisites
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c2deb4b8-6532-4659-b4d7-554a7b7e7aca
---

# HMFT Testing Prerequisites


This section describes the tasks that you must complete before you test a Hardware Media Foundation Transform (HMFT)–compliant device by using the Windows Hardware Certification Kit (Windows HCK):

-   [Review the hardware requirements](#bkmk-hck-hmft-hr)

-   [Review the software requirements](#bkmk-hck-hmft-sr)

-   [Configure the test computers](#bkmk-hck-hmft-tc)

An HMFT-compliant device is a video card or chipset that supports hardware-based encoding or decoding of digital content.

**Note**  
If the video card is a not a stand-alone product (for example, a video chipset on a system board), these tests run as part of system certification.

 

## <a href="" id="bkmk-hck-hmft-hr"></a>Hardware requirements


The following hardware is required for testing an HMFT-compliant device:

-   A test computer.

    **Note**  
    The test computer must meet the [Windows HCK Prerequisites](windows-hck-prerequisites.md). It also must have at least 75 GB free on the drive used as the HCK working directory.

     

-   An HMFT-compliant video card (the test device), unless the HMFT feature is included in a video chipset on the system board.

You might need additional hardware if the test device includes audio, networking, or other features. To determine whether additional hardware requirements apply, see the description for each test that's identified for your video card or chipset in Windows HCK Studio.

## <a href="" id="bkmk-hck-hmft-sr"></a>Software requirements


The following software is required for testing an HMFT-compliant device:

-   The latest Windows HCK filters or updates.

-   Standard video files that are used during decoding or encoding tests.

    **Note**  
    During installation of the Windows HCK, standard video files are downloaded to Windows HCK Studio.

     

Before running the HMFT encoding and decoding tests, you must download the [Windows Hardware Certification Kit (HCK) Supplemental Test Content for HMFT Multimedia Tests](http://msdn.microsoft.com/windows/hardware/hh852358) from the Windows Dev Center. After downloading the supplemental test content, you must store this content in one of the following ways:

-   On the HCK controller, under the path %DTMBIN%..\\Tests\\HMFTContent, the default value for the ContentSource parameter must be used when scheduling the tests. This causes each test to copy over the input content that it requires only for that single test, and then delete the content after the test has completed. This is useful for computers with less than 75GB free space available.

-   In a different location than %DTMBIN%..\\Tests\\HMFTContent or on a network share accessible to the client computers. You must configure the ContentSource parameter to the location you copied the files to when scheduling the tests. This has the same behavior as the first item in this list, but allows you to specify where the content is located.

-   Copy the content locally on each client computer before running the tests. You must configure the ContentSource parameter to be the path to the content on the client computer. For example, if you use an external drive with letter d: and place the content in d:\\HMFTContent, the ContentSource parameter must be configured to d:\\HMFTContent. This will cause the test to use the local content and not copy each file for each test. This option requires at least 75 GB of free space on the client computers but will speed up the test run because the content will not have to be copied for each test.

    **Note**  
    The ContentSource parameter is passed to all client computers that the tests are scheduled against so ensure that content location is identical on all client computers.

     

-   Copy the content locally on each client computer before running the tests and add the content location to the %PATH% environment variable. Leave the default value for the ContentSource parameter. This will cause the tests to behave similarly to the third item in this list. This option does not require that the content is in the same location on every client computer.

## <a href="" id="bkmk-hck-hmft-tc"></a>Test computer configuration


To configure the test computer for testing a HMFT-compliant device:

1.  Install the appropriate Windows operating system on the test computer, and then configure the computer for your test network (the network that contains Windows HCK Studio and Windows HCK Controller).

    **Note**  
    If you are testing on Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2, you must install the Desktop Experience package. From a command prompt, type:

    **Dism.exe /online /enable-feature /featurename:DesktopExperience /all**

    If the computer does not restart, you must restart it manually.

     

2.  Install the manufacturer-supplied device driver, if necessary, on the test computer.

3.  For a stand-alone video card, install the card in the test computer.

4.  Install the Windows HCK client application on the test computer.

5.  By using Windows HCK Studio, create a computer pool and move the test computer to that pool.

Make sure that the test computer is in the ready state before you begin your testing. If a test requires parameters to be set before it's run, a dialog box is displayed for that test. Review the specific test topic for more information.

Manual Windows HCK tests require user intervention. When running tests for a submission, it's best to run the automated tests in a block separately from manual tests. This prevents a manual test from interrupting completion of automated tests.

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bp_hck\p_hck%5D:%20HMFT%20Testing%20Prerequisites%20%20RELEASE:%20%284/27/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")



