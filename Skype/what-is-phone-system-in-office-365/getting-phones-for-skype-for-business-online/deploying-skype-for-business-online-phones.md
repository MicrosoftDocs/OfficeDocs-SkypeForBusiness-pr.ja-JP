---
title: "Skype for Business Online 電話機の展開レポート"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: "適切なファームウェアを取得し、更新が必要な場合、ライセンスを割り当てるビジネス オンライン電話の Skype の設定を構成する配置手順を説明します。"
ms.openlocfilehash: c62a3512929152dabe8f9ea0e8e748d38f82f127
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="2a489-103">Skype for Business Online 電話機の展開レポート</span><span class="sxs-lookup"><span data-stu-id="2a489-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="2a489-104">[] このガイドは Skype for Business Online IP 電話機の展開をサポートするガイドです。</span><span class="sxs-lookup"><span data-stu-id="2a489-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="2a489-p101">あらゆる種類のビジネスにおいて、音声通話を発受信するための電話番号を確保することは、ビジネスを運営する上で重要な条件です。電話番号を有するユーザーは、IP 電話機、PC、モバイル デバイスを含むすべての Skype for Business デバイスで音声通話を行うことができます。Skype for Business IP 電話機の詳細については、「[Skype for Business Online で使う電話を入手する](getting-phones-for-skype-for-business-online.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2a489-p101">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="2a489-108">IP 電話機の展開手順</span><span class="sxs-lookup"><span data-stu-id="2a489-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="2a489-109">ステップ 1 - メーカーの管理者ガイドと電話機のマニュアルのダウンロード</span><span class="sxs-lookup"><span data-stu-id="2a489-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="2a489-110">まず最初に、メーカーの管理ガイドと電話機のマニュアルをダウンロードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2a489-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="2a489-111">ポリコム電話、ガイドを参照 [ポリコムの展開] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html)。</span><span class="sxs-lookup"><span data-stu-id="2a489-111">For Polycom phones, see the [Polycom Deployment Guide]((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="2a489-112">Yealink 電話機については、『[Yealink Skype for Business HD SIP Phones Solution (Yealink Skype for Business HD SIP 電話機のソリューション)](http://www.yealink.com/products_top_2.html)』をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2a489-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="2a489-113">AudioCodes 電話機については、『[Audiocodes Provisioning Management Guide (Audiocodes プロビジョニング管理ガイド)](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)』をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2a489-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="2a489-114">ステップ 2 - Skype for Business 対応 IP 電話機およびファームウェアを購入または移行していることを確認する</span><span class="sxs-lookup"><span data-stu-id="2a489-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="2a489-p102">Skype for Business Online 対応の電話機およびファームウェアは、Skype for Business Server にも互換性がありますが、その逆の互換性は必ずしも保証されません。対応している電話機とファームウェアを購入またはプロビジョニングしていることを確認するには、「[Skype for Business Online で使う電話を入手する](getting-phones-for-skype-for-business-online.md)」の説明をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2a489-p102">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="2a489-117">ステップ 3 - 正しいファームウェアがインストールされていることを確認し、必要に応じてファームウェアを更新する</span><span class="sxs-lookup"><span data-stu-id="2a489-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="2a489-p103">お使いの電話機のファームウェア バージョンを、それぞれ以下の方法で確認します。</span><span class="sxs-lookup"><span data-stu-id="2a489-p103">Check the firmware version on your phones. For:</span></span>
  
- <span data-ttu-id="2a489-120">**VVX のポリコム電話**、**設定**に移動 > **ステータス** > **プラットフォーム** > **アプリケーション** > **メイン**です。</span><span class="sxs-lookup"><span data-stu-id="2a489-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="2a489-121">**Yealink 電話機** の場合は、メインの電話画面で [ **Status (情報)** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="2a489-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="2a489-122">**は電話**、**メニュー**に移動 > **デバイスの状態** > 開始画面から、**ファームウェアのバージョン**です。</span><span class="sxs-lookup"><span data-stu-id="2a489-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2a489-p104">電話機の詳細設定へのリモート アクセスについては、メーカーの管理ガイドをご覧ください。ユーザー ガイドおよび電話機マニュアルについては、上記のリンクをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2a489-p104">For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="2a489-125">**Lync の電話のエディション (LPE) 電話**、**メニュー**に移動 > 開始画面から**システム情報**です。</span><span class="sxs-lookup"><span data-stu-id="2a489-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="2a489-126">ステップ 4 - デバイス更新の考慮事項</span><span class="sxs-lookup"><span data-stu-id="2a489-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="2a489-p105">5.5.1.X より前の Polycom ファームウェアには、メーカー独自のデバイスのロック メカニズムが導入されています。このメカニズムは Skype for Business 実装の「電話のロック」に置換されています。「デバイスのロック」で保護されていた 5.4.X.X から「電話のロック」を備える 5.5.1.X に電話機をアップグレードすると、「デバイスのロック」から PIN コードが継承されないため、電話機が保護されていない状態になります。「デバイスのロック」を有効にしていたユーザーは、次の Polycom デバイスのプロファイル パラメーターを有効にして、ユーザーがアップグレードのタイミングを制御できるようにする必要があります (lync.deviceUpdate.popUpSK.enabled=1)。</span><span class="sxs-lookup"><span data-stu-id="2a489-p105">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="2a489-p106">ファームウェアの更新は Skype for Business Service によって管理されます。Skype for Business 認定済みの電話機のファームウェアは Skype for Business Update サーバーにアップロードされます。既定では、デバイスの更新はすべての電話機で有効になっています。電話機の無通信時間およびポーリング間隔に応じて、電話機では最新の認定済みビルドがダウロードされ、インストールされます。デバイスの更新設定は [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) コマンドレットを使用して、 _EnableDeviceUpdate_ パラメーターを `false` に設定することで無効にできます。</span><span class="sxs-lookup"><span data-stu-id="2a489-p106">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Deploying phones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="2a489-p107">新しいファームウェアが利用可能になり、ダウンロードとインストールの準備が整うと、電話機が通知を受信します。Polycom 電話機では、ユーザーは通知を受信し、[ **Update (更新)** ] または [ **Postpone (延期)** ] のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="2a489-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![Deploying phones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="2a489-138">Polycom 電話機の場合は、 **SwUpdate** を選択することで電話機のファームウェアを更新できます。</span><span class="sxs-lookup"><span data-stu-id="2a489-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Deploying phones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="2a489-p108">パートナーのプロビジョニング システムを使用してファームウェアの更新を管理するように選択することもできます。高度な電話機カスタマイズなど、パートナー プロビジョニング システム管理を行う場合は、製造元の管理ガイドをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2a489-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="2a489-142">更新のループを回避するため、単一のデバイス更新機関 (インバンド デバイス更新またはサードパーティー プロビジョニング サーバー) を利用してください。</span><span class="sxs-lookup"><span data-stu-id="2a489-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="2a489-143">ステップ 5 - 電話の設定の構成とインフラ整備</span><span class="sxs-lookup"><span data-stu-id="2a489-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="2a489-p109">Skype for Business インバンド管理の Windows PowerShell コマンドレットを使用して最も一般的に使用される電話機オプションをセットアップできます。これらのパラメーターおよび設定の詳細については、「[Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2a489-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="2a489-146">ネットワーク インフラストラクチャの計画については、「[Skype Operations Framework (Skype の運用フレームワーク](https://www.skypeoperationsframework.com/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2a489-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="2a489-147">ステップ 6 - ユーザーのサインインの準備</span><span class="sxs-lookup"><span data-stu-id="2a489-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="2a489-148">正常にオンライン ビジネスの電話で、Skype にサインインし、呼び出しを行うユーザーを有効にするには、ユーザーが適切なライセンスを割り当てられているかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a489-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="2a489-149">最低限、電話システムのライセンスとを呼び出す計画を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a489-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="2a489-150">詳細については、 [Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)および[ビジネスおよびマイクロソフトのチームのライセンスを Skype の割り当て](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2a489-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="2a489-151">通話プランの詳細については、「[Office 365 の通話プランについて](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)」を読むことで確認できます。</span><span class="sxs-lookup"><span data-stu-id="2a489-151">You can find out more about Calling Plans by reading [What are Calling Plans in Office 365?](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)</span></span>
  
- <span data-ttu-id="2a489-152">Online ユーザーが利用できる **サインイン オプション** は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2a489-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="2a489-153">**Polycom VVX 5XX/6XX** 電話機のユーザーには次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a489-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Deploying phones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="2a489-155">**Yealink T48G/T46G** 電話機のユーザーには次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a489-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink phones logon.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="2a489-157">製造元ごとのサポートされるサインイン オプションの詳細については、「[Skype for Business Online で使う電話を入手する](getting-phones-for-skype-for-business-online.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2a489-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="2a489-p111">**ユーザー ID** ユーザーは、電話機のキーパッドまたは画面上のキーボード (利用可能な場合) を使用して、組織のユーザー名およびパスワードで電話機にサインインできます。たとえば、ユーザー名として *amosm@contoso.com*  のような UPN 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a489-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like *amosm@contoso.com*  for their user name.</span></span>
    
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="2a489-161">PIN 認証は、LPE およびパートナーの IP 電話機向けの Skype for Business Online ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2a489-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="2a489-162">**PC を使用します。**相乗効果 (BToE) のイーサネットのソフトウェアがユーザーの PC にインストールし、有効にすると、Windows の Skype のビジネス アプリケーションの「認証」ウィンドウを使用して、電話、ユーザーがログオンできます。</span><span class="sxs-lookup"><span data-stu-id="2a489-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="2a489-163">その他の情報[(オプション) - と相乗効果 (BToE) のイーサネット デバイスのペアがある場合の手順 7](deploying-skype-for-business-online-phones.md#BK_BTOE)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a489-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2a489-p113">ユーザーは、電話機にサインインするために組織のユーザー名およびパスワードを使用する必要があります。たとえば、ユーザー名として  *amosm@contoso.com*  のような UPN 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a489-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  *amosm@contoso.com*  for their user name.</span></span>
  
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="2a489-p114">**Web サインインの使用**: これは、Online ユーザーが標準の Web ブラウザを使用して認証を行うことができる新しい方法です。ユーザーには、ブラウザを使ってサインインするときの手順が提供されます。</span><span class="sxs-lookup"><span data-stu-id="2a489-p114">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="2a489-169">**Polycom VVX 5XX/6XX** 電話機のユーザーには次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a489-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Deploying phones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="2a489-171">**Yealink T48G/T46G** 電話機のユーザーには次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a489-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink phone logon.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="2a489-p115">生成されるコードの有効期限は 15 分です。期限が切れると、ユーザーは電話機に応じて [ **再試行**] または [ **OK**] をクリックして新しいコードを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a489-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="2a489-175">**Polycom VVX 5XX/6XX** 電話機のユーザーには次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a489-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![PIN code expired.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="2a489-177">**Yealink T48G/T46G** 電話機のユーザーには次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a489-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink phones logon.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="2a489-179">ブラウザを使用して、電話機に表示されるアドレスに移動して、Skype for Business ユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2a489-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Deploying phones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="2a489-181">電話機に表示されるコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="2a489-181">Enter the code shown on the phone.</span></span>
    
     ![Deploying phones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="2a489-183">サイトに「[電話機メーカーの名前] **Skype for Business Certified Phone (Skype for Business 認定済みの電話機)**」と表示されていることを確認し、[ **続行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a489-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![Deploying phones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="2a489-185">ユーザーの資格情報をクリックするか、[ **Use another account (別のアカウントを使用する)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a489-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Deploying phones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="2a489-187">下記のページが表示されたら、ブラウザを安全に閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="2a489-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![Deploying phones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="2a489-189">Skype for Business Online 向けの LPE 電話機は USB テザリングを介したサインインのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2a489-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="2a489-190">**サポートされる展開** 次の表は、Exchange 統合、多要素認証 (MFA) による先進認証、Skype for Business Online およびオンプレミスといった現在サポートされている展開モデルの対応認証方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2a489-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a489-191">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="2a489-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="2a489-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="2a489-192">**Exchange**</span></span> <br/> |<span data-ttu-id="2a489-193">**電話機のサインイン方法**</span><span class="sxs-lookup"><span data-stu-id="2a489-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="2a489-194">**Skype For Business アクセス**</span><span class="sxs-lookup"><span data-stu-id="2a489-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="2a489-195">**先進認証と MFA を無効にした Exchange アクセス**</span><span class="sxs-lookup"><span data-stu-id="2a489-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="2a489-196">**先進認証と MFA を有効にした Exchange アクセス**</span><span class="sxs-lookup"><span data-stu-id="2a489-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="2a489-197">オンライン</span><span class="sxs-lookup"><span data-stu-id="2a489-197">Online</span></span>  <br/> |<span data-ttu-id="2a489-198">オンライン</span><span class="sxs-lookup"><span data-stu-id="2a489-198">Online</span></span>  <br/> |<span data-ttu-id="2a489-199">Web サイン イン</span><span class="sxs-lookup"><span data-stu-id="2a489-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="2a489-200">あり</span><span class="sxs-lookup"><span data-stu-id="2a489-200">Yes</span></span>  <br/> |<span data-ttu-id="2a489-201">あり</span><span class="sxs-lookup"><span data-stu-id="2a489-201">Yes</span></span>  <br/> |<span data-ttu-id="2a489-202">あり</span><span class="sxs-lookup"><span data-stu-id="2a489-202">Yes</span></span>  <br/> |
|<span data-ttu-id="2a489-203">オンライン</span><span class="sxs-lookup"><span data-stu-id="2a489-203">Online</span></span>  <br/> |<span data-ttu-id="2a489-204">オンライン</span><span class="sxs-lookup"><span data-stu-id="2a489-204">Online</span></span>  <br/> |<span data-ttu-id="2a489-205">ユーザー名/パスワード</span><span class="sxs-lookup"><span data-stu-id="2a489-205">Username/Password</span></span>  <br/> |<span data-ttu-id="2a489-206">あり</span><span class="sxs-lookup"><span data-stu-id="2a489-206">Yes</span></span>  <br/> |<span data-ttu-id="2a489-207">あり</span><span class="sxs-lookup"><span data-stu-id="2a489-207">Yes</span></span>  <br/> |<span data-ttu-id="2a489-208">なし</span><span class="sxs-lookup"><span data-stu-id="2a489-208">No</span></span>  <br/> |
|<span data-ttu-id="2a489-209">オンライン</span><span class="sxs-lookup"><span data-stu-id="2a489-209">Online</span></span>  <br/> |<span data-ttu-id="2a489-210">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="2a489-210">On-premises</span></span>  <br/> |<span data-ttu-id="2a489-211">Web サイン イン</span><span class="sxs-lookup"><span data-stu-id="2a489-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="2a489-212">あり</span><span class="sxs-lookup"><span data-stu-id="2a489-212">Yes</span></span>  <br/> |<span data-ttu-id="2a489-213">なし</span><span class="sxs-lookup"><span data-stu-id="2a489-213">No</span></span>  <br/> |<span data-ttu-id="2a489-214">なし</span><span class="sxs-lookup"><span data-stu-id="2a489-214">No</span></span>  <br/> |
|<span data-ttu-id="2a489-215">オンライン</span><span class="sxs-lookup"><span data-stu-id="2a489-215">Online</span></span>  <br/> |<span data-ttu-id="2a489-216">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="2a489-216">On-Premises</span></span>  <br/> |<span data-ttu-id="2a489-217">ユーザー名/パスワード</span><span class="sxs-lookup"><span data-stu-id="2a489-217">Username/Password</span></span>  <br/> |<span data-ttu-id="2a489-218">あり</span><span class="sxs-lookup"><span data-stu-id="2a489-218">Yes</span></span>  <br/> |<span data-ttu-id="2a489-219">あり</span><span class="sxs-lookup"><span data-stu-id="2a489-219">Yes</span></span>  <br/> |<span data-ttu-id="2a489-220">なし</span><span class="sxs-lookup"><span data-stu-id="2a489-220">No</span></span>  <br/> |
|<span data-ttu-id="2a489-221">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="2a489-221">On-premises</span></span>  <br/> |<span data-ttu-id="2a489-222">オンライン/オンプレミス</span><span class="sxs-lookup"><span data-stu-id="2a489-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="2a489-223">PIN 認証</span><span class="sxs-lookup"><span data-stu-id="2a489-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="2a489-224">あり</span><span class="sxs-lookup"><span data-stu-id="2a489-224">Yes</span></span>  <br/> |<span data-ttu-id="2a489-225">なし</span><span class="sxs-lookup"><span data-stu-id="2a489-225">No</span></span>  <br/> |<span data-ttu-id="2a489-226">なし</span><span class="sxs-lookup"><span data-stu-id="2a489-226">No</span></span>  <br/> |
|<span data-ttu-id="2a489-227">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="2a489-227">On-premises</span></span>  <br/> |<span data-ttu-id="2a489-228">オンライン/オンプレミス</span><span class="sxs-lookup"><span data-stu-id="2a489-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="2a489-229">ユーザー名/パスワード</span><span class="sxs-lookup"><span data-stu-id="2a489-229">Username/Password</span></span>  <br/> |<span data-ttu-id="2a489-230">あり</span><span class="sxs-lookup"><span data-stu-id="2a489-230">Yes</span></span>  <br/> |<span data-ttu-id="2a489-231">あり</span><span class="sxs-lookup"><span data-stu-id="2a489-231">Yes</span></span>  <br/> |<span data-ttu-id="2a489-232">該当なし</span><span class="sxs-lookup"><span data-stu-id="2a489-232">N/A</span></span>  <br/> |
|<span data-ttu-id="2a489-233">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="2a489-233">On-premises</span></span>  <br/> |<span data-ttu-id="2a489-234">オンライン/オンプレミス</span><span class="sxs-lookup"><span data-stu-id="2a489-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="2a489-235">PC 経由のサイン イン(BTOE)</span><span class="sxs-lookup"><span data-stu-id="2a489-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="2a489-236">あり</span><span class="sxs-lookup"><span data-stu-id="2a489-236">Yes</span></span>  <br/> |<span data-ttu-id="2a489-237">あり</span><span class="sxs-lookup"><span data-stu-id="2a489-237">Yes</span></span>  <br/> |<span data-ttu-id="2a489-238">該当なし</span><span class="sxs-lookup"><span data-stu-id="2a489-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="2a489-239">**電話の機能**IP 電話のパートナーにわずかに基づく機能セットが異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2a489-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="2a489-240">完全な機能の設定し、電話のメーカーごとの機能の詳細については、[オンライン ビジネスの Skype の電話を取得](getting-phones-for-skype-for-business-online.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a489-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="2a489-p117">**電話のロック** は、電話機を保護するために Skype for Business 認定済み電話機に最近導入されてた機能です。この機能が有効な場合、ユーザーは正常な認証後に PIN を作成するように求められます。PIN の作成後、定義したアイドル タイムアウトを過ぎると電話機がロックされます。さらに、ユーザーは電話機を手動でロックするか、電話のペアリングを使用して電話のロックを同期させることもできます。電話のロックの PIN を複数回誤って入力すると、ユーザーが電話機からサインアウトされるか、管理者のコードを使用して電話機をロック解除する必要があります。ただし、これは電話機パートナーによって異なります。ユーザーの PIN は 6 桁から 15 桁です。</span><span class="sxs-lookup"><span data-stu-id="2a489-p117">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="2a489-p118">既定で有効化されている組織の電話のロックの無効化、アイドル タイムアウトの変更、ロック時またはインバンド設定の未使用時にユーザーが通話できるかどうかの設定を行うことができます。これらの設定の詳細については、「[Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2a489-p118">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="2a489-248">ステップ 7 (省略可能) - デバイス ペアリングおよび Better Together over Ethernet (BToE) を使用する場合</span><span class="sxs-lookup"><span data-stu-id="2a489-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="2a489-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="2a489-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="2a489-p119">BToE は、ユーザーの電話機を Windows Skype for Business アプリとペアリングさせるパートナー IP 電話機の電話ペアリング メカニズムです。BToE により、ユーザーを次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2a489-p119">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:</span></span>
  
- <span data-ttu-id="2a489-252">Skype for Business デスクトップ アプリ (PC を使用) を使用して IP 電話機にサインインする</span><span class="sxs-lookup"><span data-stu-id="2a489-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="2a489-253">電話のロックを PC のロックと同期する</span><span class="sxs-lookup"><span data-stu-id="2a489-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="2a489-254">クリックして通話する</span><span class="sxs-lookup"><span data-stu-id="2a489-254">Click to call</span></span>
    
<span data-ttu-id="2a489-p120">BToE の動作は [ *自動*  ] (既定) および [ *手動*  ] の 2 つのモードで構成できます。Skype for Business のインバンド設定を使用して、ユーザーに対して有効 (既定) または無効にすることもできます。[ *手動*  ] モードでの動作では、電話機と Windows アプリをペアリングするために追加の手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="2a489-p120">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="2a489-258">**ユーザーに BToE を展開する方法**</span><span class="sxs-lookup"><span data-stu-id="2a489-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="2a489-259">PC ポートを使用して PC を電話機に接続します。</span><span class="sxs-lookup"><span data-stu-id="2a489-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Deploying phones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="2a489-p121">次に示すリンクを使ってメーカーの Web サイトから最新の BToE ソフトウェアをダウンロードし、インストールします。ユーザーの利便性を向上するため、System Center Configuration Manager (SCCM) などの管理配布ソリューションを使用して BToE ソフトウェアを配布して、インストールすることができます。SCCM の使用については、「[System Center Configuration Manager のパッケージとプログラム](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2a489-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as System Center Configuration Manager (SCCM). For help using SCCM, See [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span></span>
    
  - [<span data-ttu-id="2a489-264">Polycom BToE ソフトウェア ダウンロード サイト</span><span class="sxs-lookup"><span data-stu-id="2a489-264">Polycom BToE Software Download site</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [<span data-ttu-id="2a489-265">Yealink BToE ソフトウェア ダウンロード</span><span class="sxs-lookup"><span data-stu-id="2a489-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
  - [<span data-ttu-id="2a489-266">AudioCodes BToE ソフトウェア ダウンロード</span><span class="sxs-lookup"><span data-stu-id="2a489-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="2a489-267">BToE のサーバーの設定は、既定で**有効に**して**自動モード**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2a489-267">The server setting for BToE is set to **Enabled** and **Auto mode** by default.</span></span> <span data-ttu-id="2a489-268">これらの設定を変更するには、[セット CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a489-268">To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="2a489-269">BToE は Mac および VDI プラットフォームでは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2a489-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="2a489-270">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2a489-270">Related topics</span></span>
[<span data-ttu-id="2a489-271">Skype のビジネスおよびマイクロソフトのチームのサービスの電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="2a489-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="2a489-272">Office 365 での電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="2a489-272">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="2a489-273">オーディオ会議や予定を呼び出すための国および地域の可用性</span><span class="sxs-lookup"><span data-stu-id="2a489-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)


