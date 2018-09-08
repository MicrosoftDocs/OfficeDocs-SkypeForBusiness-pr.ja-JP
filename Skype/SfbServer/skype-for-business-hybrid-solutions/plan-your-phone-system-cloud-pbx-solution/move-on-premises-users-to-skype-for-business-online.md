---
title: ビジネス オンラインの Skype に、オンプレミスのユーザーを移動します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2475674a-f592-4fa8-ae99-f71cbea54dc0
description: '概要: 移動の詳細について設置 Skype ユーザー ビジネスをオンラインにします。'
ms.openlocfilehash: 1cb57e777b9353b1abb5b211563f5b6adc58e72c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882069"
---
# <a name="move-on-premises-users-to-skype-for-business-online"></a><span data-ttu-id="15530-103">ビジネス オンラインの Skype に、オンプレミスのユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="15530-103">Move on-premises users to Skype for Business Online</span></span>
 
<span data-ttu-id="15530-104">**の概要:** ビジネス オンラインの Skype をオンプレミス ユーザーの移動について説明します。</span><span class="sxs-lookup"><span data-stu-id="15530-104">**Summary:** Information about moving on-premises users to Skype for Business Online.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="15530-105">オンプレミス環境で Skype for Business Online に移動する前に、Lync Phone Edition デバイスを最小要求ファームウェアに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15530-105">Lync Phone Edition devices MUST be updated to minimum required firmware in your on premises environment PRIOR to moving to Skype for Business Online.</span></span> <span data-ttu-id="15530-106">オンプレミスからオンラインにユーザーを移動してからファームウェアを更新すると、ユーザーは電話を使用して接続できなくなります。</span><span class="sxs-lookup"><span data-stu-id="15530-106">If you move your users from on-premises to online prior to updating the firmware, users will be unable to connect using their phones.</span></span> <span data-ttu-id="15530-107">この問題を訂正するには、ユーザーをオンプレミス環境に戻して、電話を最小ファームウェアに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15530-107">To correct this problem, users must be moved back to the on premises environment to have their phones updated to the minimum firmware.</span></span> <span data-ttu-id="15530-108">最小ファームウェアに更新するか、電話をハード リセットしてから、ユーザーをオンプレミス環境に戻すことは試みないでください。</span><span class="sxs-lookup"><span data-stu-id="15530-108">DO NOT ATTEMPT TO UPDATE TO MINIMUM FIRMWARE OR HARD RESET THE PHONE PRIOR TO MOVING THE USER BACK TO YOUR ON PREMISES ENVIRONMENT.</span></span>
<span data-ttu-id="15530-109">デバイスが最小ファームウェアになっていないときにハード リセットを実行すると、既定で PIN 認証を使用するようになります。これは、Skype for Business Online でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="15530-109">If a hard reset is performed while the device is not at minimum firmware it will default to using PIN Authentication, which is not supported in Skype for Business Online.</span></span> <span data-ttu-id="15530-110">詳細については、[オンライン ビジネスの Skype の電話を取得する](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15530-110">For more information, please refer to [Getting Phones for Skype for Business Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
<span data-ttu-id="15530-111">これは、オンライン ビジネスの Skype に、オンプレミスのユーザーを移動する場合にのみ要求されるオプションの手順です。</span><span class="sxs-lookup"><span data-stu-id="15530-111">This is an optional step that is required only if you are moving on-premises users to Skype for Business Online.</span></span> <span data-ttu-id="15530-112">Skype をビジネス オンラインのユーザーを移動する作業を開始する前に、ビジネス オンライン コネクタ (Windows PowerShell モジュール) の Skype がフロント エンド サーバーで運用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="15530-112">Before you begin to move users to Skype for Business Online, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="15530-113">、いない場合は、[ダウンロード センター](https://www.microsoft.com/en-us/download/details.aspx?id=39366)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="15530-113">If it isn't, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="15530-114">また、AD を準備するには Azure AD Connect の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="15530-114">Also, to prepare your AD, you'll need to configure Azure AD Connect.</span></span> <span data-ttu-id="15530-115">1.0.9125.0 以降のバージョンの AAD Connect を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15530-115">The version of AAD Connect you use must be version 1.0.9125.0 or later.</span></span> <span data-ttu-id="15530-116">それよりも前のバージョンの AAD Connect ツールまたは DirSync を使用している場合は、サポートされているバージョンにアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="15530-116">If you are using an earlier version of AAD Connect tools or DirSync, please upgrade to the supported version.</span></span> <span data-ttu-id="15530-117">現在のインストールをアップグレードして、環境で定義しているカスタム ルールを維持できます。</span><span class="sxs-lookup"><span data-stu-id="15530-117">You can upgrade your current installation and maintain any custom rules you have defined in your environment.</span></span>
  
<span data-ttu-id="15530-118">使用していずれかの Skype ビジネス サーバーのコントロール パネルまたは Skype のビジネス サーバー管理シェルの設置型展開でユーザーを移動するが、Office 365 の展開の管理者の資格情報を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="15530-118">You move users using either Skype for Business Server Control Panel or Skype for Business Server Management Shell in your on-premises deployment, but you must have administrator credentials for your Office 365 deployment.</span></span>
  
## <a name="moving-users-by-using-skype-for-business-control-panel"></a><span data-ttu-id="15530-119">ビジネス コントロール パネルの Skype を使用して、ユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="15530-119">Moving users by using Skype for Business Control Panel</span></span>

### <a name="to-move-a-user-to-skype-for-business-online"></a><span data-ttu-id="15530-120">Skype をビジネス オンラインのユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="15530-120">To move a user to Skype for Business Online</span></span>

1. <span data-ttu-id="15530-121">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウント、コンピューターにログオンする、ビジネス サーバー、または Skype を内部展開で最小の Skype ビジネス サーバー管理ツールがインストールされているのです。</span><span class="sxs-lookup"><span data-stu-id="15530-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment that has Skype for Business Server, or at least Skype for Business Server Admin tools installed.</span></span>
    
2. <span data-ttu-id="15530-122">[スタート] メニューまたはデスクトップのショートカットでは、ビジネス サーバーのコントロール パネルの Skype を開きます。</span><span class="sxs-lookup"><span data-stu-id="15530-122">From the Start menu or desktop shortcut, open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="15530-123">Skype は、1 つを構成した場合は、管理者の URL を使用してビジネス サーバーのコントロール パネルにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="15530-123">You can also access the Skype for Business Server Control Panel by using the Admin URL if you have configured one.</span></span>
    
3. <span data-ttu-id="15530-124">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15530-124">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="15530-125">[**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15530-125">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="15530-126">ユーザーをクリックし、[**アクション**] メニューで [**選んだユーザーを Skype for Business Online に移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15530-126">Click the user, then in the **Action** menu, click **Move selected users to Skype for Business Online**.</span></span>
    
6. <span data-ttu-id="15530-127">[**選択したユーザーを Skype for Business Online に移動**] ページの情報を確認して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15530-127">On the **Move users to Skype For Business Online** page, read the information and then click **Next**.</span></span>
    
7. <span data-ttu-id="15530-128">次のページでは、するは、まだ署名されていない場合 Office 365 に、 **Office 365 にサインイン**] をクリックして、資格情報を入力、 **[ok]** および [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15530-128">On the next page, if you are not yet signed in to Office 365, click **Sign in to Office 365**, provide your credentials, and click **OK** and **Next**.</span></span>
    
8. <span data-ttu-id="15530-129">移動するユーザー数が正しいことを確認して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15530-129">Confirm that the number of users to be moved is correct, and click **Next**.</span></span>
    
9. <span data-ttu-id="15530-130">次のページで結果を確認して、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15530-130">On the next page, review the results and click **Close**.</span></span>
    
## <a name="moving-users-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="15530-131">Skype ビジネス サーバー管理シェルを使用してユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="15530-131">Moving users by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="15530-132">オンライン ビジネスのテナントの Skype に、オンプレミスのユーザーを移動するには、ビジネス サーバー管理シェルを管理者の資格情報を使用して、Microsoft Office 365 のテナントのため、Skype で次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="15530-132">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="15530-133">"username@contoso.com" を、移動するユーザーの情報で置換します。</span><span class="sxs-lookup"><span data-stu-id="15530-133">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

<span data-ttu-id="15530-134">**HostedMigrationOverrideUrl**パラメーターは次の形式で、ホストの移行サービスが実行されているプールへの URL である必要があります用に指定された URL の形式: _Https://\<プールの FQDN\>/HostedMigration/hostedmigrationService.svc_。</span><span class="sxs-lookup"><span data-stu-id="15530-134">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>
  
<span data-ttu-id="15530-135">Office 365 テナント アカウントのビジネスのオンライン管理センターの Skype の URL を表示することによってホストされている移行サービスの URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="15530-135">You can determine the URL to the Hosted Migration Service by viewing the URL for the Skype for Business Online Admin center for your Office 365 tenant account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15530-136">この URL では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="15530-136">The URL is case sensitive.</span></span> 
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="15530-137">Office 365 テナントのホスティング型移行サービスの URL を確認するには</span><span class="sxs-lookup"><span data-stu-id="15530-137">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="15530-138">管理者として Office 365 テナントにログインします。</span><span class="sxs-lookup"><span data-stu-id="15530-138">Login to your Office 365 tenant as an administrator.</span></span>
    
2. <span data-ttu-id="15530-139">[**Skype for Business 管理センター**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="15530-139">Open the **Skype for Business admin center**.</span></span>
    
3. <span data-ttu-id="15530-p104">[**Skype for Business 管理センター**] が表示されたら、**lync.com** の近くのアドレス バーの URL を選択してコピーします。URL は、次のような書式です。</span><span class="sxs-lookup"><span data-stu-id="15530-p104">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. <span data-ttu-id="15530-142">URL の **webdir** を **admin** に置き換えると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="15530-142">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span> 
    
     `https://admin0a.online.lync.com`
    
5. <span data-ttu-id="15530-143">URL に以下の文字列を付加します。**/HostedMigration/hostedmigrationservice.svc**</span><span class="sxs-lookup"><span data-stu-id="15530-143">Append the following string to the URL: **/HostedMigration/hostedmigrationService.svc**.</span></span>
    
    <span data-ttu-id="15530-144">結果の URL は、 **HostedMigrationOverrideUrl**の値は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="15530-144">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationService.svc`
    

