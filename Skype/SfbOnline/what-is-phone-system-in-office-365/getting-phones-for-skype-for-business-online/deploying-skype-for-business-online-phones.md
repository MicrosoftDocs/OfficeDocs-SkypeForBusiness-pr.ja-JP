---
title: "展開の Skype for Business Online フォン"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: "展開の適切なファームウェアを取得し、必要な場合は、更新、ライセンスを割り当てる Skype for Business online の携帯電話の設定を構成する手順について説明します。"
ms.openlocfilehash: 86756fb1033e2928a7427c9352fbf6fbb24dc154
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="f3ab4-103">展開の Skype for Business Online フォン</span><span class="sxs-lookup"><span data-stu-id="f3ab4-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="f3ab4-104">これは、展開ガイドが展開をサポート Skype for Business Online IP フォンします。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="f3ab4-p101">企業のすべての種類] でが生じる電話番号を行い、音声通話を取得するユーザーは、ビジネスの重要な要件はします。電話番号を持つユーザーはビジネス デバイスが IP 電話、コンピューター、モバイル デバイスなどのすべての Skype の間での音声通話の発信できるようにします。ことができます詳細について Skype ビジネス IP 電話用[Skype for Business Online の取得電話](getting-phones-for-skype-for-business-online.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p101">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="f3ab4-108">IP 電話用展開の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="f3ab4-109">手順 1 - 製造元の管理者ガイドと電話のマニュアルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="f3ab4-110">作業を開始する前に、電話の製造元の管理ガイドと電話ユーザー マニュアルをダウンロードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="f3ab4-111">Polycom 電話、ドキュメントを参照して、[Polycom 展開] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html)。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-111">For Polycom phones, see the [Polycom Deployment Guide]((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="f3ab4-112">Yealink 電話、[ビジネス HD SIP 電話ソリューションの Yealink Skype](http://www.yealink.com/products_top_2.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="f3ab4-113">携帯電話[はプロビジョニング管理ガイド](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="f3ab4-114">手順 2 - 購入または移行する Skype for Business のサポートされている IP 電話とファームウェアを使用しているかどうかを確認</span><span class="sxs-lookup"><span data-stu-id="f3ab4-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="f3ab4-p102">Skype for Business Online サポートの電話とファームウェアが同様に、Skype for Business Server の互換性のあるは、反対が true では常にします。確認するには、購入またはサポートされている電話およびファームウェアのプロビジョニングしているが、 [Skype for Business Online の取得電話](getting-phones-for-skype-for-business-online.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p102">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="f3ab4-117">手順 3 - 右ファームウェアがインストールされていることを確認して、ファームウェアのアップデートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="f3ab4-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="f3ab4-p103">自分の携帯電話にファームウェアのバージョンを確認してください。場合。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p103">Check the firmware version on your phones. For:</span></span>
  
- <span data-ttu-id="f3ab4-120">**Polycom VVX 携帯電話**、**設定**に移動 > **状態** > **プラットフォーム** > **アプリケーション** > **メイン**します。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="f3ab4-121">**Yealink 携帯電話**、携帯電話のメイン画面での**状態**に移動します。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="f3ab4-122">**は携帯電話**、**メニュー**に移動 > **デバイスのステータス** > スタート画面から**ファームウェアのバージョン**。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f3ab4-p104">電話の詳細をリモート アクセスは、製造元の管理ガイドを参照してください。電話のマニュアル、ユーザー ガイドの上にあるリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p104">For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="f3ab4-125">**携帯電話の Lync Phone Edition (LPE)**、**メニュー**に移動 > スタート画面から**システム情報**。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="f3ab4-126">手順 4 - デバイスの更新に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="f3ab4-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="f3ab4-p105">5.5.1.X よりも前の Polycom ファームウェアが Skype for Business の実装「電話のロック」に置き換え、製造元が特定のデバイスのロック メカニズム「デバイスのロック」で保護された 5.4.X.X から「電話ロック」5.5.1.X に電話をアップグレードする「デバイス ロック」のままに保護されていない電話から PIN コードを継承されません。「デバイスのロック」がアクティブになっているユーザーは、ユーザーにアップグレード (lync.deviceUpdate.popUpSK.enabled=1) の時間の制御を渡す次 Polycom デバイスのプロファイルのパラメーターを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p105">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="f3ab4-p106">ファームウェアのアップデートは、ビジネスのサービスの Skype によって管理されます。すべての Skype for Business には、スマート フォンのファームウェアが Skype for Business 更新サーバーにアップロードされ、デバイスの更新が既定ですべての電話で有効になってが認められています。携帯電話とポーリング間隔の待ち時間によって電話をダウンロードしてインストール認定最新ビルド自動的にします。[セット CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)コマンドレットを使用して、 _EnableDeviceUpdate_パラメーターを設定してデバイスの更新プログラムの設定を無効にすることができます`false`します。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p106">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![電話を展開します。](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="f3ab4-p107">新しいファームウェアをいるときに使用できる進む準備ができたらをダウンロードしてインストールする、ユーザーが携帯電話に通知されます。Polycom 電話は、ユーザーに通知され、**更新**または**延期**するオプションを提供してされます。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![電話を展開します。](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="f3ab4-138">Polycom 先の電話番号の**SwUpdate**を選択して、電話のファームウェアを更新できます。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![電話を展開します。](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="f3ab4-p108">パートナー プロビジョニング システムを使用してファームウェアのアップデートを管理することもできます。電話の高度なカスタマイズを含むシステムの管理を提供するパートナー、製造元の管理ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f3ab4-142">単一のデバイス (インバンド デバイスの更新またはサード パーティの準備サーバー) 更新ループを避けるための権限の更新を確認します。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="f3ab4-143">手順 5 - の構成とインフラストラクチャ電話の設定</span><span class="sxs-lookup"><span data-stu-id="f3ab4-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="f3ab4-p109">ポリシーに Skype for Business インバンド管理 Windows PowerShell コマンドレットを使い、頻繁に使用する電話のオプションを設定できます。これらのパラメーターを設定の詳細については、[セット CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="f3ab4-146">ネットワーク インフラストラクチャの計画、 [Skype 運用フレームワーク](https://www.skypeoperationsframework.com/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="f3ab4-147">手順 6: ユーザーのサインイン用に準備します。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="f3ab4-p110">正常に Skype for Business Online の電話にサインインして、通話の発信にユーザーを有効にするには、ユーザーが正しいライセンスを割り当てられているかどうかを確認する必要があります。最低でもは、電話システムでライセンス、プランの呼び出しを割り当てる必要があります。詳細については、 [Skype for Business や Microsoft チーム アドオンのライセンス](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を割り当てると[Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)とビジネスや Microsoft チームのライセンスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p110">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum, you will need to assign a Phone System license and a Calling Plan. For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="f3ab4-151">読みの詳細については、プランの呼び出しを確認できます[Office 365 のプランの呼び出しとは何ですか?](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f3ab4-151">You can find out more about Calling Plans by reading [What are Calling Plans in Office 365?](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)</span></span>
  
- <span data-ttu-id="f3ab4-152">オンライン ユーザーはサポートされている**サインイン オプション**:</span><span class="sxs-lookup"><span data-stu-id="f3ab4-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="f3ab4-153">**Polycom VVX 5 xx/6 xx**電話を持つユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![電話を展開します。](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="f3ab4-155">**Yealink T48G/T46G**電話を持つユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink 電話ログオンします。](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="f3ab4-157">製造元がサポートされているサインイン オプションの詳細については、 [Skype for Business Online の取得電話](getting-phones-for-skype-for-business-online.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="f3ab4-p111">**ユーザー ID**電話のキーパッドを使用して、スクリーン キーボードの (使用可能な場合)、またはユーザーが携帯電話へのサインインに、組織のユーザー名とパスワードを使うことができます。たとえば、 *amosm@contoso.com*のような UPN 形式を使用すると、ユーザー名の必要がありますがします。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like *amosm@contoso.com*  for their user name.</span></span>
    
     ![電話を展開します。](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="f3ab4-161">PIN 認証ではサポートされない Skype for Business Online LPE とパートナー IP 電話用します。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="f3ab4-p112">**PC を使用します。**相乗効果イーサネット (BToE) ソフトウェアは、ユーザーの PC にインストールされているし、有効になっている、ユーザーはで、windows 版の Skype for Business アプリの認証] ウィンドウの使用が携帯電話にログインことができます。その他の情報は、[手順 7 (省略可能): デバイスのペアリングと相乗効果イーサネット (BToE) がある場合](deploying-skype-for-business-online-phones.md#BK_BTOE)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p112">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App. See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f3ab4-p113">ユーザーは、組織のユーザー名とパスワードを使用して、携帯電話にサインインする必要があります。たとえば、 *amosm@contoso.com*のような UPN 形式を使用すると、ユーザー名の必要がありますがします。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  *amosm@contoso.com*  for their user name.</span></span>
  
     ![電話を展開します。](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="f3ab4-p114">**Web のサインインに使用する**: オンライン ユーザー認証標準の web ブラウザーを使用するための新しい方法です。一連の指示に従って、ブラウザーを使用してサインインするときにユーザーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p114">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="f3ab4-169">**Polycom VVX 5 xx/6 xx**電話を持つユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![電話を展開します。](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="f3ab4-171">**Yealink T48G/T46G**電話を持つユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink 電話ログオンします。](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="f3ab4-p115">生成されたコードの有効期限は、15 分以内にします。期限切れ、ユーザーは**再試行**をクリックして**[ok]**によっては、電話、新しいコードを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="f3ab4-175">**Polycom VVX 5 xx/6 xx**電話を持つユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![PIN コードの有効期限が切れています。](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="f3ab4-177">**Yealink T48G/T46G**電話を持つユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink 電話ログオンします。](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="f3ab4-179">ブラウザーを使用してでは、携帯端末で表示されるアドレスに移動して、ビジネス ユーザー名の Skype を入力します。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![電話を展開します。](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="f3ab4-181">携帯端末でコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-181">Enter the code shown on the phone.</span></span>
    
     ![電話を展開します。](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="f3ab4-183">サイトが表示されていることを確認"[電話の製造元の名前] **Skype for Business 認定済み Phone**の場合は、"**続行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![電話を展開します。](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="f3ab4-185">ユーザーの資格情報をクリックするか、**別のアカウントを使用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![電話を展開します。](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="f3ab4-187">次のページが表示されたら、ブラウザーを閉じるには安全です。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![電話を展開します。](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="f3ab4-189">LPE は、skype for Business Online サポート サインイン USB ケーブル接続」のみを電話します。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="f3ab4-190">**サポートされている展開**次の表は、現在サポートされている配置モデルなどの Exchange の統合、多要素認証 (MFA) と Skype for Business Online や社内の先進認証のサポートされている認証の種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f3ab4-191">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="f3ab4-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="f3ab4-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="f3ab4-192">**Exchange**</span></span> <br/> |<span data-ttu-id="f3ab4-193">**携帯電話へのサインイン方法**</span><span class="sxs-lookup"><span data-stu-id="f3ab4-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="f3ab4-194">**Skype for Business アクセス**</span><span class="sxs-lookup"><span data-stu-id="f3ab4-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="f3ab4-195">**最新の認証と MFA を無効になっている Exchange のアクセス**</span><span class="sxs-lookup"><span data-stu-id="f3ab4-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="f3ab4-196">**最新の認証と MFA を有効になっている Exchange のアクセス**</span><span class="sxs-lookup"><span data-stu-id="f3ab4-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="f3ab4-197">オンライン</span><span class="sxs-lookup"><span data-stu-id="f3ab4-197">Online</span></span>  <br/> |<span data-ttu-id="f3ab4-198">オンライン</span><span class="sxs-lookup"><span data-stu-id="f3ab4-198">Online</span></span>  <br/> |<span data-ttu-id="f3ab4-199">Web にサインイン</span><span class="sxs-lookup"><span data-stu-id="f3ab4-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="f3ab4-200">○</span><span class="sxs-lookup"><span data-stu-id="f3ab4-200">Yes</span></span>  <br/> |<span data-ttu-id="f3ab4-201">○</span><span class="sxs-lookup"><span data-stu-id="f3ab4-201">Yes</span></span>  <br/> |<span data-ttu-id="f3ab4-202">○</span><span class="sxs-lookup"><span data-stu-id="f3ab4-202">Yes</span></span>  <br/> |
|<span data-ttu-id="f3ab4-203">オンライン</span><span class="sxs-lookup"><span data-stu-id="f3ab4-203">Online</span></span>  <br/> |<span data-ttu-id="f3ab4-204">オンライン</span><span class="sxs-lookup"><span data-stu-id="f3ab4-204">Online</span></span>  <br/> |<span data-ttu-id="f3ab4-205">ユーザー名とパスワードを入力</span><span class="sxs-lookup"><span data-stu-id="f3ab4-205">Username/Password</span></span>  <br/> |<span data-ttu-id="f3ab4-206">○</span><span class="sxs-lookup"><span data-stu-id="f3ab4-206">Yes</span></span>  <br/> |<span data-ttu-id="f3ab4-207">○</span><span class="sxs-lookup"><span data-stu-id="f3ab4-207">Yes</span></span>  <br/> |<span data-ttu-id="f3ab4-208">×</span><span class="sxs-lookup"><span data-stu-id="f3ab4-208">No</span></span>  <br/> |
|<span data-ttu-id="f3ab4-209">オンライン</span><span class="sxs-lookup"><span data-stu-id="f3ab4-209">Online</span></span>  <br/> |<span data-ttu-id="f3ab4-210">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="f3ab4-210">On-premises</span></span>  <br/> |<span data-ttu-id="f3ab4-211">Web にサインイン</span><span class="sxs-lookup"><span data-stu-id="f3ab4-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="f3ab4-212">○</span><span class="sxs-lookup"><span data-stu-id="f3ab4-212">Yes</span></span>  <br/> |<span data-ttu-id="f3ab4-213">×</span><span class="sxs-lookup"><span data-stu-id="f3ab4-213">No</span></span>  <br/> |<span data-ttu-id="f3ab4-214">×</span><span class="sxs-lookup"><span data-stu-id="f3ab4-214">No</span></span>  <br/> |
|<span data-ttu-id="f3ab4-215">オンライン</span><span class="sxs-lookup"><span data-stu-id="f3ab4-215">Online</span></span>  <br/> |<span data-ttu-id="f3ab4-216">内部設置型</span><span class="sxs-lookup"><span data-stu-id="f3ab4-216">On-Premises</span></span>  <br/> |<span data-ttu-id="f3ab4-217">ユーザー名とパスワードを入力</span><span class="sxs-lookup"><span data-stu-id="f3ab4-217">Username/Password</span></span>  <br/> |<span data-ttu-id="f3ab4-218">○</span><span class="sxs-lookup"><span data-stu-id="f3ab4-218">Yes</span></span>  <br/> |<span data-ttu-id="f3ab4-219">○</span><span class="sxs-lookup"><span data-stu-id="f3ab4-219">Yes</span></span>  <br/> |<span data-ttu-id="f3ab4-220">×</span><span class="sxs-lookup"><span data-stu-id="f3ab4-220">No</span></span>  <br/> |
|<span data-ttu-id="f3ab4-221">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="f3ab4-221">On-premises</span></span>  <br/> |<span data-ttu-id="f3ab4-222">オンライン/内部設置型</span><span class="sxs-lookup"><span data-stu-id="f3ab4-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="f3ab4-223">PIN 認証</span><span class="sxs-lookup"><span data-stu-id="f3ab4-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="f3ab4-224">○</span><span class="sxs-lookup"><span data-stu-id="f3ab4-224">Yes</span></span>  <br/> |<span data-ttu-id="f3ab4-225">×</span><span class="sxs-lookup"><span data-stu-id="f3ab4-225">No</span></span>  <br/> |<span data-ttu-id="f3ab4-226">×</span><span class="sxs-lookup"><span data-stu-id="f3ab4-226">No</span></span>  <br/> |
|<span data-ttu-id="f3ab4-227">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="f3ab4-227">On-premises</span></span>  <br/> |<span data-ttu-id="f3ab4-228">オンライン/内部設置型</span><span class="sxs-lookup"><span data-stu-id="f3ab4-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="f3ab4-229">ユーザー名とパスワードを入力</span><span class="sxs-lookup"><span data-stu-id="f3ab4-229">Username/Password</span></span>  <br/> |<span data-ttu-id="f3ab4-230">○</span><span class="sxs-lookup"><span data-stu-id="f3ab4-230">Yes</span></span>  <br/> |<span data-ttu-id="f3ab4-231">○</span><span class="sxs-lookup"><span data-stu-id="f3ab4-231">Yes</span></span>  <br/> |<span data-ttu-id="f3ab4-232">該当なし</span><span class="sxs-lookup"><span data-stu-id="f3ab4-232">N/A</span></span>  <br/> |
|<span data-ttu-id="f3ab4-233">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="f3ab4-233">On-premises</span></span>  <br/> |<span data-ttu-id="f3ab4-234">オンライン/内部設置型</span><span class="sxs-lookup"><span data-stu-id="f3ab4-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="f3ab4-235">PC (BTOE) でサインイン</span><span class="sxs-lookup"><span data-stu-id="f3ab4-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="f3ab4-236">○</span><span class="sxs-lookup"><span data-stu-id="f3ab4-236">Yes</span></span>  <br/> |<span data-ttu-id="f3ab4-237">○</span><span class="sxs-lookup"><span data-stu-id="f3ab4-237">Yes</span></span>  <br/> |<span data-ttu-id="f3ab4-238">該当なし</span><span class="sxs-lookup"><span data-stu-id="f3ab4-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="f3ab4-p116">**電話の機能**IP 電話パートナーに基づいてやや機能セットが異なる場合があります。完全な機能の設定し、各電話の製造元の機能の詳細については、 [Skype for Business Online の取得電話](getting-phones-for-skype-for-business-online.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p116">**Phone features** The feature set may vary slightly based on the IP phone partner. For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="f3ab4-p117">**電話ロック**は、Skype for Business 電話が認められて、電話をセキュリティで保護するためで最近導入された機能です。有効な場合、ユーザーは認証に失敗した暗証番号 (pin) を作成するように求められます。いったん作成した場合、携帯電話がアイドル状態で定義したタイムアウト、ユーザーが手動で電話をロックまたは携帯電話のペアリングを使用して、PC のロックと電話のロックを同期するときにロックされます。電話ロック PIN は、必要な回数だけが正しく入力は、電話がユーザーをサインアウトするか、電話のロックを解除する管理者向けのコードの要求] しますが、電話パートナーによって異なります。ユーザーの PIN は、6、15 桁の数字でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p117">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="f3ab4-p118">(これは既定で有効に)、組織の携帯電話のロックを無効にする、アイドル状態のタイムアウト、変更、ロックされているか使用していないインバンド設定されている間に、ユーザーが電話をかけることができるかどうかを選択したりできます。これらの設定の詳細については、[セット CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p118">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="f3ab4-248">手順 7 (省略可能): デバイスのペアがある場合、相乗効果イーサネット (BToE)</span><span class="sxs-lookup"><span data-stu-id="f3ab4-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="f3ab4-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="f3ab4-249"></span></span>

<span data-ttu-id="f3ab4-p119">BToE は、paining メカニズム パートナー IP 電話は電話をペア ビジネス アプリケーション BToE 用の Windows でユーザーの電話を使用します。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p119">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:</span></span>
  
- <span data-ttu-id="f3ab4-252">For Business のデスクトップ アプリ (PC を使用して)、Skype を使用して、IP 電話へのサインインします。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="f3ab4-253">PC のロックとロック電話を同期します。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="f3ab4-254">電話をかける] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-254">Click to call</span></span>
    
<span data-ttu-id="f3ab4-p120">2 つのモードで動作する BToE を構成することができます: (既定) の*自動*および*手動*します。こともできます (既定) を有効になっている/用 Skype for Business のインバンド設定を使ってユーザーを無効にします。*手動*モードで使用する場合、ユーザーが携帯電話が Windows アプリのペアに追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p120">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="f3ab4-258">**ユーザーに BToE を展開するには**</span><span class="sxs-lookup"><span data-stu-id="f3ab4-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="f3ab4-259">PC のポートを使用して、電話、PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![電話を展開します。](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="f3ab4-p121">ダウンロードして、次のリンクからの製造元の web サイトから最新の BToE ソフトウェアをインストールします。ユーザー エクスペリエンスを向上するには、配布し、システム センター構成マネージャー (SCCM) などの管理配布ソリューションを使用して BToE ソフトウェアをインストールできます。ヘルプは SCCM を使用して、[パッケージとシステム センター構成マネージャーのプログラム](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as System Center Configuration Manager (SCCM). For help using SCCM, See [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span></span>
    
  - <span data-ttu-id="f3ab4-264">[[サイトの Polycom BToE ソフトウェアのダウンロード](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)</span><span class="sxs-lookup"><span data-stu-id="f3ab4-264">[Polycom BToE Software Download site](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)</span></span>
    
  - [<span data-ttu-id="f3ab4-265">Yealink BToE ソフトウェアのダウンロード</span><span class="sxs-lookup"><span data-stu-id="f3ab4-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
  - [<span data-ttu-id="f3ab4-266">BToE ソフトウェアをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="f3ab4-p122">BToE のサーバーの設定は、既定で**有効に**して**自動モード**に設定されています。これらの設定を変更するには、[セット CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-p122">The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="f3ab4-269">BToE は Mac および VDI プラットフォーム上で現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="f3ab4-270">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f3ab4-270">Related topics</span></span>
[<span data-ttu-id="f3ab4-271">Skype for Business とチームの Microsoft サービスの電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="f3ab4-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="f3ab4-272">ここではされた電話システムで Office 365 での表示</span><span class="sxs-lookup"><span data-stu-id="f3ab4-272">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="f3ab4-273">電話会議とプランの呼び出しの国と地域の空き時間情報</span><span class="sxs-lookup"><span data-stu-id="f3ab4-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)


