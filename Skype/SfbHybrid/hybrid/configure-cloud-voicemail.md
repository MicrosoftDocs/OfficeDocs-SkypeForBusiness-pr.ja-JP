---
title: オンプレミスのユーザー用にクラウドボイスメールサービスを構成する
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Skype for Business Server を使用しているユーザーに対して、クラウドベースのボイスメールを実装する方法について説明します。
ms.openlocfilehash: 29faba6bf092647f0c55899f013c6b4bf146304f
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552583"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="2b1a1-103">オンプレミスのユーザー用にクラウドボイスメールサービスを構成する</span><span class="sxs-lookup"><span data-stu-id="2b1a1-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="2b1a1-104">概要</span><span class="sxs-lookup"><span data-stu-id="2b1a1-104">Overview</span></span> 
<span data-ttu-id="2b1a1-105">この記事では、Skype for Business オンプレミスユーザー用に Microsoft クラウドボイスメールサービスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="2b1a1-106">この記事では、サポートされているトポロジで Skype for Business Server が既に展開されており、ハイブリッド接続をセットアップするための前提条件を満たしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="2b1a1-107">クラウドボイスメールを実装する場合の利点、計画に関する考慮事項、および要件の詳細については、「 [Plan Cloud ボイスメールサービス](plan-cloud-voicemail.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="2b1a1-108">クラウドボイスメールの構成には、次のタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="2b1a1-109">「 [Plan Cloud ボイスメールサービス](plan-cloud-voicemail.md)」で説明されている前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="2b1a1-110">「ハイブリッド[接続を計画](plan-hybrid-connectivity.md)する」および「[ハイブリッド接続を構成](configure-hybrid-connectivity.md)する」の説明に従って、ハイブリッド接続を設定していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="2b1a1-111">この記事で説明されているよう[に、フロントエンドサーバーのホスティングプロバイダーとして Cloud 留守番電話を構成](#configure-cloud-voicemail-as-the-hosting-provider)します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-111">[Configure Cloud Voicemail as the hosting provider on the Front End Server](#configure-cloud-voicemail-as-the-hosting-provider) as described in this article.</span></span>

4.  <span data-ttu-id="2b1a1-112">この記事で説明されているように[、ホスト型ボイスメールポリシーを構成](#configure-a-hosted-voicemail-policy)します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="2b1a1-113">この記事で説明されているように[、ホスト型ボイスメールポリシーを割り当て](#assign-a-hosted-voicemail-policy)ます。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="2b1a1-114">この記事で説明されているよう[に、ユーザーのクラウドボイスメールを有効に](#enable-a-user-for-cloud-voicemail)します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a><span data-ttu-id="2b1a1-115">ホスティングプロバイダーとしてクラウドボイスメールを構成する</span><span class="sxs-lookup"><span data-stu-id="2b1a1-115">Configure Cloud Voicemail as the hosting provider</span></span> 

<span data-ttu-id="2b1a1-116">次のパラメーターを使用して、新しい-CsHostingProvider コマンドレットを使用して、クラウドボイスメールをホスティングプロバイダーとしてフロントエンドサーバーに構成します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="2b1a1-117">**Identity**は、作成するホスティングプロバイダーの一意の文字列値識別子を指定します。たとえば、クラウドボイスメールです。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="2b1a1-118">**Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="2b1a1-119">このパラメーターは True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="2b1a1-120">**EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="2b1a1-121">このパラメーターは True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="2b1a1-122">**Hostソケット Susers**は、ホスティングプロバイダーが Skype For business Server アカウントをホストするために使用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="2b1a1-123">このパラメーターは False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="2b1a1-124">**Proxyfqdn**は、ホスティングプロバイダーによって使用されるプロキシサーバーの完全修飾ドメイン名 (FQDN) を指定します。たとえば、proxyserver.contoso.com のようになります。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="2b1a1-125">この情報については、ホスティング プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="2b1a1-126">この値は変更できません。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-126">This value cannot be modified.</span></span> <span data-ttu-id="2b1a1-127">ホスティングプロバイダーがプロキシサーバーを変更した場合は、そのプロバイダーのエントリを削除してから再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="2b1a1-128">**Islocal**は、ホスティングプロバイダーによって使用されるプロキシサーバーが Skype For business server のトポロジ内に含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="2b1a1-129">このパラメーターは False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-129">This parameter must be set to False.</span></span>

<span data-ttu-id="2b1a1-130">たとえば、Skype for Business 管理シェルでは、次のコマンドレットにより、クラウドボイスメールがホスティングプロバイダーとして構成されます。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="2b1a1-131">ホスト型ボイスメールポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="2b1a1-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="2b1a1-132">組織のボイスメールがクラウドボイスメールサービスにルーティングされるようにするには、組織に対してホスト型ボイスメールポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="2b1a1-133">多くの場合、ホストボイスメールポリシーは1つだけ必要であり、グローバルポリシーを変更してすべてのニーズを満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="2b1a1-134">組織で複数のホスト型ボイスメールポリシーが必要な場合は、set-cshostedvoicemailpolicy コマンドレットを使用してポリシーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="2b1a1-135">グローバルポリシーを変更するには、組織と TenantID を更新した後、Skype for Business Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- <span data-ttu-id="2b1a1-136">**Destination**には、ホストされているクラウドボイスメールサービスの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="2b1a1-137">この値は、 **exap.um.outlook.com**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="2b1a1-138">**組織**は、テナントに割り当てられている既定のドメインです。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="2b1a1-139">この情報を取得するには、テナント管理者が office.com にログインし、[管理センター] アプリをクリックして、左側の [**セットアップ**] に移動し、[**ドメイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="2b1a1-140">例: mytenant.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="2b1a1-141">組織名は、Microsoft 365 または Office 365 の既定のドメイン名でもあります。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-141">The Organization name is also the Default Domain name in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="2b1a1-142">ホスト型ボイスメールポリシーが正常に作成されたことを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-142">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="2b1a1-143">ホスト型ボイスメールポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="2b1a1-143">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="2b1a1-144">既定では、グローバルにホストされるボイスメールポリシーがすべてのユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-144">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="2b1a1-145">別のポリシーを使用する場合は、ホストされたボイスメールにユーザーを有効にする前に、 [set-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps)コマンドレットを使用して、必要なホストボイスメールポリシーをユーザーに付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-145">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="2b1a1-146">たとえば、次のコマンドを実行すると、非グローバルなホスト型ボイスメールポリシーがユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-146">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="2b1a1-147">クラウドボイスメールでユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="2b1a1-147">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="2b1a1-148">ユーザーのボイスメールをクラウドボイスメールにルーティングできるようにするには、HostedVoiceMail パラメーターを指定して、ユーザーのボイス[メールコマンドレット](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)を使用します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-148">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="2b1a1-149">たとえば、次のコマンドを実行すると、クラウドボイスメールのユーザーアカウントが有効になります。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-149">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

<span data-ttu-id="2b1a1-150">このコマンドレットは、クラウドボイスメールポリシーがグローバル、サイト、またはユーザーレベルであることを確認します。--このユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-150">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="2b1a1-151">適用されるポリシーがない場合には、このコマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-151">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="2b1a1-152">次の例では、クラウドボイスメールのユーザーアカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-152">The next example disables a user account for Cloud Voicemail:</span></span>

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

<span data-ttu-id="2b1a1-153">このコマンドレットは、ホストされているボイスメールポリシーがないことを確認します。これは、グローバル、サイト、またはユーザーレベルで、このユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-153">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="2b1a1-154">適用されるポリシーがある場合には、このコマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-154">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="2b1a1-155">ユーザーは、Microsoft クラウドボイスメールサービスを使用するために、エンタープライズ voip が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b1a1-155">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>
