---
title: Skype for Business Online 電話機の展開レポート
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 適切なファームウェアを取得し、必要に応じて更新し、ライセンスを割り当て、Skype for Business online 電話機の設定を構成するための展開手順について説明します。
ms.openlocfilehash: efcea04a454d846c0140e9d1dba561da228df1de
ms.sourcegitcommit: a61d33fe15982bd8a34f1759b6b89be5aa699fe3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2020
ms.locfileid: "41784754"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="e8493-103">Skype for Business Online 電話機の展開レポート</span><span class="sxs-lookup"><span data-stu-id="e8493-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="e8493-104">[] このガイドは Skype for Business Online IP 電話機の展開をサポートするガイドです。</span><span class="sxs-lookup"><span data-stu-id="e8493-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="e8493-p101">あらゆる種類のビジネスにおいて、音声通話を発受信するための電話番号を確保することは、ビジネスを運営する上で重要な条件です。電話番号を有するユーザーは、IP 電話機、PC、モバイル デバイスを含むすべての Skype for Business デバイスで音声通話を行うことができます。Skype for Business IP 電話機の詳細については、「[Skype for Business Online で使う電話を入手する](getting-phones-for-skype-for-business-online.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8493-p101">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="e8493-108">IP 電話機の展開手順</span><span class="sxs-lookup"><span data-stu-id="e8493-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="e8493-109">ステップ 1 - メーカーの管理者ガイドと電話機のマニュアルのダウンロード</span><span class="sxs-lookup"><span data-stu-id="e8493-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="e8493-110">まず最初に、メーカーの管理ガイドと電話機のマニュアルをダウンロードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e8493-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="e8493-111">Polycom 電話の場合は、 [Poly ドキュメントライブラリ](https://documents.polycom.com/category/voice)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8493-111">For Polycom phones, see the [Poly Documentation Library](https://documents.polycom.com/category/voice).</span></span>
    
- <span data-ttu-id="e8493-112">Yealink 電話機については、『[Yealink Skype for Business HD SIP Phones Solution (Yealink Skype for Business HD SIP 電話機のソリューション)](http://www.yealink.com/products_top_2.html)』をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8493-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="e8493-113">AudioCodes 電話機については、『[Audiocodes Provisioning Management Guide (Audiocodes プロビジョニング管理ガイド)](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)』をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8493-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="e8493-114">ステップ 2 - Skype for Business 対応 IP 電話機およびファームウェアを購入または移行していることを確認する</span><span class="sxs-lookup"><span data-stu-id="e8493-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="e8493-p102">Skype for Business Online 対応の電話機およびファームウェアは、Skype for Business Server にも互換性がありますが、その逆の互換性は必ずしも保証されません。対応している電話機とファームウェアを購入またはプロビジョニングしていることを確認するには、「[Skype for Business Online で使う電話を入手する](getting-phones-for-skype-for-business-online.md)」の説明をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8493-p102">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="e8493-117">ステップ 3 - 正しいファームウェアがインストールされていることを確認し、必要に応じてファームウェアを更新する</span><span class="sxs-lookup"><span data-stu-id="e8493-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="e8493-p103">お使いの電話機のファームウェア バージョンを、それぞれ以下の方法で確認します。</span><span class="sxs-lookup"><span data-stu-id="e8493-p103">Check the firmware version on your phones. For:</span></span>
  
- <span data-ttu-id="e8493-120">**Polycom VVX 電話**の場合は、**[設定]** > **[ステータス]** > **[プラットフォーム]** > **[アプリケーション]** > **[メイン]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8493-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="e8493-121">**Yealink 電話機** の場合は、メインの電話画面で [ **Status (情報)** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8493-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="e8493-122">**AudioCodes 電話**の場合は、**[メニュー]** > **[デバイス ステータス]** > **[ファームウェア バージョン]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8493-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e8493-p104">電話機の詳細設定へのリモート アクセスについては、メーカーの管理ガイドをご覧ください。ユーザー ガイドおよび電話機マニュアルについては、上記のリンクをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8493-p104">For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="e8493-125">**Lync Phone Edition (LPE) 電話**: スタート画面から \*\*[メニュー] \*\* > \*\*[システム情報] \*\*に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8493-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="e8493-126">ステップ 4 - デバイス更新の考慮事項</span><span class="sxs-lookup"><span data-stu-id="e8493-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="e8493-p105">5.5.1.X より前の Polycom ファームウェアには、メーカー独自のデバイスのロック メカニズムが導入されています。このメカニズムは Skype for Business 実装の「電話のロック」に置換されています。「デバイスのロック」で保護されていた 5.4.X.X から「電話のロック」を備える 5.5.1.X に電話機をアップグレードすると、「デバイスのロック」から PIN コードが継承されないため、電話機が保護されていない状態になります。「デバイスのロック」を有効にしていたユーザーは、次の Polycom デバイスのプロファイル パラメーターを有効にして、ユーザーがアップグレードのタイミングを制御できるようにする必要があります (lync.deviceUpdate.popUpSK.enabled=1)。</span><span class="sxs-lookup"><span data-stu-id="e8493-p105">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="e8493-p106">ファームウェアの更新は Skype for Business Service によって管理されます。Skype for Business 認定済みの電話機のファームウェアは Skype for Business Update サーバーにアップロードされます。既定では、デバイスの更新はすべての電話機で有効になっています。電話機の無通信時間およびポーリング間隔に応じて、電話機では最新の認定済みビルドがダウロードされ、インストールされます。デバイスの更新設定は [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) コマンドレットを使用して、 _EnableDeviceUpdate_ パラメーターを `false` に設定することで無効にできます。</span><span class="sxs-lookup"><span data-stu-id="e8493-p106">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![電話の展開を示すスクリーンショット](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="e8493-p107">新しいファームウェアが利用可能になり、ダウンロードとインストールの準備が整うと、電話機が通知を受信します。Polycom 電話機では、ユーザーは通知を受信し、[ **Update (更新)** ] または [ **Postpone (延期)** ] のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e8493-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![更新と延期のオプションが表示されたスクリーンショット。](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="e8493-138">Polycom 電話機の場合は、 **SwUpdate** を選択することで電話機のファームウェアを更新できます。</span><span class="sxs-lookup"><span data-stu-id="e8493-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![SwUpdate オプションを示すスクリーンショット](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="e8493-p108">パートナーのプロビジョニング システムを使用してファームウェアの更新を管理するように選択することもできます。高度な電話機カスタマイズなど、パートナー プロビジョニング システム管理を行う場合は、製造元の管理ガイドをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8493-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e8493-142">更新のループを回避するため、単一のデバイス更新機関 (インバンド デバイス更新またはサードパーティー プロビジョニング サーバー) を利用してください。</span><span class="sxs-lookup"><span data-stu-id="e8493-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="e8493-143">ステップ 5 - 電話の設定の構成とインフラ整備</span><span class="sxs-lookup"><span data-stu-id="e8493-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="e8493-p109">Skype for Business インバンド管理の Windows PowerShell コマンドレットを使用して最も一般的に使用される電話機オプションをセットアップできます。これらのパラメーターおよび設定の詳細については、「[Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8493-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="e8493-146">ネットワーク インフラストラクチャの計画については、「[Skype Operations Framework (Skype の運用フレームワーク](https://www.skypeoperationsframework.com/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8493-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="e8493-147">ステップ 6 - ユーザーのサインインの準備</span><span class="sxs-lookup"><span data-stu-id="e8493-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="e8493-148">ユーザーが正常に Skype for Business Online 電話機にサインインし、通話できるようにするには、ユーザーに正しいライセンスが割り当てられていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8493-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="e8493-149">最低でも、電話システムのライセンスと通話プランを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8493-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="e8493-150">詳細については、「 [skype For business および Microsoft teams のアドオンライセンス](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」を参照して、 [skype For Business および microsoft teams のライセンスを割り当てる](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="e8493-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="e8493-151">通話プランの詳細については、「[電話システムと通話プラン](/microsoftteams/calling-plan-landing-page)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8493-151">You can find out more about Calling Plans by reading [Phone System and Calling Plans](/microsoftteams/calling-plan-landing-page)</span></span>
  
- <span data-ttu-id="e8493-152">Online ユーザーが利用できる **サインイン オプション** は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8493-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="e8493-153">**Polycom VVX 5XX/6XX** 電話機のユーザーには次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8493-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Polycom 電話のログオンを示すスクリーンショット](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="e8493-155">**Yealink T48G/T46G** 電話機のユーザーには次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8493-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     !["ごみ箱" の電話が表示されているスクリーンショット。](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="e8493-157">製造元ごとのサポートされるサインイン オプションの詳細については、「[Skype for Business Online で使う電話を入手する](getting-phones-for-skype-for-business-online.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8493-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="e8493-p111">**ユーザー ID** ユーザーは、電話機のキーパッドまたは画面上のキーボード (利用可能な場合) を使用して、組織のユーザー名およびパスワードで電話機にサインインできます。たとえば、ユーザー名として <em>amosm@contoso.com</em>  のような UPN 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="e8493-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![ログイン画面を示すスクリーンショット](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="e8493-161">PIN 認証は、LPE およびパートナーの IP 電話機向けの Skype for Business Online ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e8493-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="e8493-162">**PC の使用** ユーザーの PC に Better Together over Ethernet (BToE) ソフトウェアがインストールされ、有効化されている場合、ユーザーは Windows Skype for Business アプリの認証ウィンドウを使用して電話機にログインできます。</span><span class="sxs-lookup"><span data-stu-id="e8493-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="e8493-163">他の情報については、「手順 7 (オプション)」を参照してください。[デバイスのペアリングとイーサネット (BToE) 経由での共同作業がより](deploying-skype-for-business-online-phones.md#BK_BTOE)簡単になります。</span><span class="sxs-lookup"><span data-stu-id="e8493-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="e8493-p113">ユーザーは、電話機にサインインするために組織のユーザー名およびパスワードを使用する必要があります。たとえば、ユーザー名として  <em>amosm@contoso.com</em>  のような UPN 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="e8493-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![ログイン画面を示すスクリーンショット](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="e8493-p114">**Web サインインの使用**: これは、Online ユーザーが標準の Web ブラウザを使用して認証を行うことができる新しい方法です。ユーザーには、ブラウザを使ってサインインするときの手順が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e8493-p114">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="e8493-169">**Polycom VVX 5XX/6XX** 電話機のユーザーには次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8493-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Polycom の手順を示すスクリーンショット](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="e8493-171">**Yealink T48G/T46G** 電話機のユーザーには次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8493-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     !["Alink" の命令が表示されたスクリーンショット](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="e8493-p115">生成されるコードの有効期限は 15 分です。期限が切れると、ユーザーは電話機に応じて [ **再試行**] または [ **OK**] をクリックして新しいコードを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8493-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="e8493-175">**Polycom VVX 5XX/6XX** 電話機のユーザーには次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8493-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![有効期限が切れた Polycom コードを示すスクリーンショット](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="e8493-177">**Yealink T48G/T46G** 電話機のユーザーには次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8493-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![期限切れになったごみ箱コードを示すスクリーンショット](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="e8493-179">ブラウザを使用して、電話機に表示されるアドレスに移動して、Skype for Business ユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e8493-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![メールの確認が表示されたスクリーンショット](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="e8493-181">電話機に表示されるコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e8493-181">Enter the code shown on the phone.</span></span>
    
     ![ログイン画面にコードを入力する画面を示すスクリーンショット](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="e8493-183">サイトに「[電話機メーカーの名前] **Skype for Business Certified Phone (Skype for Business 認定済みの電話機)**」と表示されていることを確認し、[ **続行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8493-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![名前の確認を示すスクリーンショット](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="e8493-185">ユーザーの資格情報をクリックするか、[ **Use another account (別のアカウントを使用する)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8493-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![資格情報オプションが表示されたスクリーンショット](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="e8493-187">下記のページが表示されたら、ブラウザを安全に閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="e8493-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![確認メッセージが表示されたスクリーンショット](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="e8493-189">Skype for Business Online 向けの LPE 電話機は USB テザリングを介したサインインのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e8493-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="e8493-190">**サポートされる展開** 次の表は、Exchange 統合、多要素認証 (MFA) による先進認証、Skype for Business Online およびオンプレミスといった現在サポートされている展開モデルの対応認証方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e8493-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e8493-191">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="e8493-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="e8493-192">**交換**</span><span class="sxs-lookup"><span data-stu-id="e8493-192">**Exchange**</span></span> <br/> |<span data-ttu-id="e8493-193">**電話機のサインイン方法**</span><span class="sxs-lookup"><span data-stu-id="e8493-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="e8493-194">**Skype For Business アクセス**</span><span class="sxs-lookup"><span data-stu-id="e8493-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="e8493-195">**先進認証と MFA を無効にした Exchange アクセス**</span><span class="sxs-lookup"><span data-stu-id="e8493-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="e8493-196">**先進認証と MFA を有効にした Exchange アクセス**</span><span class="sxs-lookup"><span data-stu-id="e8493-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="e8493-197">オンライン</span><span class="sxs-lookup"><span data-stu-id="e8493-197">Online</span></span>  <br/> |<span data-ttu-id="e8493-198">オンライン</span><span class="sxs-lookup"><span data-stu-id="e8493-198">Online</span></span>  <br/> |<span data-ttu-id="e8493-199">Web サイン イン</span><span class="sxs-lookup"><span data-stu-id="e8493-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="e8493-200">はい</span><span class="sxs-lookup"><span data-stu-id="e8493-200">Yes</span></span>  <br/> |<span data-ttu-id="e8493-201">はい</span><span class="sxs-lookup"><span data-stu-id="e8493-201">Yes</span></span>  <br/> |<span data-ttu-id="e8493-202">はい</span><span class="sxs-lookup"><span data-stu-id="e8493-202">Yes</span></span>  <br/> |
|<span data-ttu-id="e8493-203">オンライン</span><span class="sxs-lookup"><span data-stu-id="e8493-203">Online</span></span>  <br/> |<span data-ttu-id="e8493-204">オンライン</span><span class="sxs-lookup"><span data-stu-id="e8493-204">Online</span></span>  <br/> |<span data-ttu-id="e8493-205">ユーザー名/パスワード</span><span class="sxs-lookup"><span data-stu-id="e8493-205">Username/Password</span></span>  <br/> |<span data-ttu-id="e8493-206">はい</span><span class="sxs-lookup"><span data-stu-id="e8493-206">Yes</span></span>  <br/> |<span data-ttu-id="e8493-207">はい</span><span class="sxs-lookup"><span data-stu-id="e8493-207">Yes</span></span>  <br/> |<span data-ttu-id="e8493-208">いいえ</span><span class="sxs-lookup"><span data-stu-id="e8493-208">No</span></span>  <br/> |
|<span data-ttu-id="e8493-209">オンライン</span><span class="sxs-lookup"><span data-stu-id="e8493-209">Online</span></span>  <br/> |<span data-ttu-id="e8493-210">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="e8493-210">On-premises</span></span>  <br/> |<span data-ttu-id="e8493-211">Web サイン イン</span><span class="sxs-lookup"><span data-stu-id="e8493-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="e8493-212">はい</span><span class="sxs-lookup"><span data-stu-id="e8493-212">Yes</span></span>  <br/> |<span data-ttu-id="e8493-213">いいえ</span><span class="sxs-lookup"><span data-stu-id="e8493-213">No</span></span>  <br/> |<span data-ttu-id="e8493-214">いいえ</span><span class="sxs-lookup"><span data-stu-id="e8493-214">No</span></span>  <br/> |
|<span data-ttu-id="e8493-215">オンライン</span><span class="sxs-lookup"><span data-stu-id="e8493-215">Online</span></span>  <br/> |<span data-ttu-id="e8493-216">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="e8493-216">On-Premises</span></span>  <br/> |<span data-ttu-id="e8493-217">ユーザー名/パスワード</span><span class="sxs-lookup"><span data-stu-id="e8493-217">Username/Password</span></span>  <br/> |<span data-ttu-id="e8493-218">はい</span><span class="sxs-lookup"><span data-stu-id="e8493-218">Yes</span></span>  <br/> |<span data-ttu-id="e8493-219">はい</span><span class="sxs-lookup"><span data-stu-id="e8493-219">Yes</span></span>  <br/> |<span data-ttu-id="e8493-220">なし</span><span class="sxs-lookup"><span data-stu-id="e8493-220">No</span></span>  <br/> |
|<span data-ttu-id="e8493-221">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="e8493-221">On-premises</span></span>  <br/> |<span data-ttu-id="e8493-222">オンライン/オンプレミス</span><span class="sxs-lookup"><span data-stu-id="e8493-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="e8493-223">PIN 認証</span><span class="sxs-lookup"><span data-stu-id="e8493-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="e8493-224">はい</span><span class="sxs-lookup"><span data-stu-id="e8493-224">Yes</span></span>  <br/> |<span data-ttu-id="e8493-225">いいえ</span><span class="sxs-lookup"><span data-stu-id="e8493-225">No</span></span>  <br/> |<span data-ttu-id="e8493-226">なし</span><span class="sxs-lookup"><span data-stu-id="e8493-226">No</span></span>  <br/> |
|<span data-ttu-id="e8493-227">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="e8493-227">On-premises</span></span>  <br/> |<span data-ttu-id="e8493-228">オンライン/オンプレミス</span><span class="sxs-lookup"><span data-stu-id="e8493-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="e8493-229">ユーザー名/パスワード</span><span class="sxs-lookup"><span data-stu-id="e8493-229">Username/Password</span></span>  <br/> |<span data-ttu-id="e8493-230">はい</span><span class="sxs-lookup"><span data-stu-id="e8493-230">Yes</span></span>  <br/> |<span data-ttu-id="e8493-231">はい</span><span class="sxs-lookup"><span data-stu-id="e8493-231">Yes</span></span>  <br/> |<span data-ttu-id="e8493-232">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8493-232">N/A</span></span>  <br/> |
|<span data-ttu-id="e8493-233">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="e8493-233">On-premises</span></span>  <br/> |<span data-ttu-id="e8493-234">オンライン/オンプレミス</span><span class="sxs-lookup"><span data-stu-id="e8493-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="e8493-235">PC 経由のサイン イン(BTOE)</span><span class="sxs-lookup"><span data-stu-id="e8493-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="e8493-236">はい</span><span class="sxs-lookup"><span data-stu-id="e8493-236">Yes</span></span>  <br/> |<span data-ttu-id="e8493-237">はい</span><span class="sxs-lookup"><span data-stu-id="e8493-237">Yes</span></span>  <br/> |<span data-ttu-id="e8493-238">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8493-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="e8493-239">**電話機の機能** 機能セットは IP 電話機パートナーによって多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8493-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="e8493-240">すべての機能セットと、各電話の製造元の各機能の詳細については、「 [Skype For Business Online の電話を取得](getting-phones-for-skype-for-business-online.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8493-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="e8493-p117">**電話のロック** は、電話機を保護するために Skype for Business 認定済み電話機に最近導入されてた機能です。この機能が有効な場合、ユーザーは正常な認証後に PIN を作成するように求められます。PIN の作成後、定義したアイドル タイムアウトを過ぎると電話機がロックされます。さらに、ユーザーは電話機を手動でロックするか、電話のペアリングを使用して電話のロックを同期させることもできます。電話のロックの PIN を複数回誤って入力すると、ユーザーが電話機からサインアウトされるか、管理者のコードを使用して電話機をロック解除する必要があります。ただし、これは電話機パートナーによって異なります。ユーザーの PIN は 6 桁から 15 桁です。</span><span class="sxs-lookup"><span data-stu-id="e8493-p117">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="e8493-246">既定で有効化されている組織の電話のロックの無効化、アイドル タイムアウトの変更、ロック時またはインバンド設定の未使用時にユーザーが通話できるかどうかの設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e8493-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="e8493-247">これらの設定の詳細については[、「Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8493-247">See [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="e8493-248">ステップ 7 (省略可能) - デバイス ペアリングおよび Better Together over Ethernet (BToE) を使用する場合</span><span class="sxs-lookup"><span data-stu-id="e8493-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="e8493-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="e8493-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="e8493-p119">BToE は、ユーザーの電話機を Windows Skype for Business アプリとペアリングさせるパートナー IP 電話機の電話ペアリング メカニズムです。BToE により、ユーザーを次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e8493-p119">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:</span></span>
  
- <span data-ttu-id="e8493-252">Skype for Business デスクトップ アプリ (PC を使用) を使用して IP 電話機にサインインする</span><span class="sxs-lookup"><span data-stu-id="e8493-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="e8493-253">電話のロックを PC のロックと同期する</span><span class="sxs-lookup"><span data-stu-id="e8493-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="e8493-254">クリックして通話する</span><span class="sxs-lookup"><span data-stu-id="e8493-254">Click to call</span></span>
    
<span data-ttu-id="e8493-p120">BToE の動作は [ *自動*  ] (既定) および [ *手動*  ] の 2 つのモードで構成できます。Skype for Business のインバンド設定を使用して、ユーザーに対して有効 (既定) または無効にすることもできます。[ *手動*  ] モードでの動作では、電話機と Windows アプリをペアリングするために追加の手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="e8493-p120">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="e8493-258">**ユーザーに BToE を展開する方法**</span><span class="sxs-lookup"><span data-stu-id="e8493-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="e8493-259">PC ポートを使用して PC を電話機に接続します。</span><span class="sxs-lookup"><span data-stu-id="e8493-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![PC への接続を示すスクリーンショット](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="e8493-261">次に示すリンクを使ってメーカーの Web サイトから最新の BToE ソフトウェアをダウンロードし、インストールします。</span><span class="sxs-lookup"><span data-stu-id="e8493-261">Download and install the latest BToE software from the manufacturer website from the links below.</span></span> <span data-ttu-id="e8493-262">優れたユーザーエクスペリエンスを実現するには、Microsoft Endpoint Configuration Manager などの管理者配布ソリューションを使用して、BToE ソフトウェアの配布とインストールを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e8493-262">For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="e8493-263">構成マネージャーの使い方については、「[構成マネージャーでのパッケージとプログラム](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8493-263">For help using Configuration Manager, See [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="e8493-264">Polycom BToE ソフトウェア ダウンロード サイト</span><span class="sxs-lookup"><span data-stu-id="e8493-264">Polycom BToE Software Download site</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="e8493-265">Yealink BToE ソフトウェア ダウンロード</span><span class="sxs-lookup"><span data-stu-id="e8493-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="e8493-266">AudioCodes BToE ソフトウェア ダウンロード</span><span class="sxs-lookup"><span data-stu-id="e8493-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="e8493-267">既定では、BToE のサーバー設定は [ **有効** ] および **自動モード** です。</span><span class="sxs-lookup"><span data-stu-id="e8493-267">The server setting for BToE is set to **Enabled** and **Auto mode** by default.</span></span> <span data-ttu-id="e8493-268">これらの設定を変更するには、 [セット CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8493-268">To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="e8493-269">BToE は Mac および VDI プラットフォームでは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e8493-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="e8493-270">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e8493-270">Related topics</span></span>
[<span data-ttu-id="e8493-271">Skype for Business および Microsoft Teams のサービス電話番号の取得</span><span class="sxs-lookup"><span data-stu-id="e8493-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="e8493-272">Office 365 の電話システムでできること</span><span class="sxs-lookup"><span data-stu-id="e8493-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="e8493-273">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="e8493-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
