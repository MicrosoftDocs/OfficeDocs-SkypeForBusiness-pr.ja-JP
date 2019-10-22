---
title: オンプレミスのユーザー用にクラウドボイスメールサービスを構成する
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Skype for Business Server を使用しているユーザーに対して、クラウドベースのボイスメールを実装する方法について説明します。
ms.openlocfilehash: 7423f16e7985a063ae5a974ea6c36684bfb75e7c
ms.sourcegitcommit: 0de27096ea3c9d6f210aeb4aad31c4255c3c0244
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2019
ms.locfileid: "37616077"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="3c197-103">オンプレミスのユーザー用にクラウドボイスメールサービスを構成する</span><span class="sxs-lookup"><span data-stu-id="3c197-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="3c197-104">概要</span><span class="sxs-lookup"><span data-stu-id="3c197-104">Overview</span></span> 
<span data-ttu-id="3c197-105">この記事では、Skype for Business オンプレミスユーザー用に Microsoft クラウドボイスメールサービスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c197-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="3c197-106">この記事では、サポートされているトポロジで Skype for Business Server が既に展開されており、ハイブリッド接続をセットアップするための前提条件を満たしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="3c197-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="3c197-107">クラウドボイスメールを実装する場合の利点、計画に関する考慮事項、および要件の詳細については、「 [Plan Cloud ボイスメールサービス](plan-cloud-voicemail.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c197-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="3c197-108">クラウドボイスメールの構成には、次のタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3c197-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="3c197-109">「 [Plan Cloud ボイスメールサービス](plan-cloud-voicemail.md)」で説明されている前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3c197-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="3c197-110">「ハイブリッド[接続を計画](plan-hybrid-connectivity.md)する」および「[ハイブリッド接続を構成](configure-hybrid-connectivity.md)する」の説明に従って、ハイブリッド接続を設定していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3c197-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="3c197-111">この記事で説明されているよう[に、エッジサーバーのホスティングプロバイダーとして Cloud 留守番電話を構成](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server)します。</span><span class="sxs-lookup"><span data-stu-id="3c197-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) as described in this article.</span></span>

4.  <span data-ttu-id="3c197-112">この記事で説明されているように[、ホスト型ボイスメールポリシーを構成](#configure-a-hosted-voicemail-policy)します。</span><span class="sxs-lookup"><span data-stu-id="3c197-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="3c197-113">この記事で説明されているように[、ホスト型ボイスメールポリシーを割り当て](#assign-a-hosted-voicemail-policy)ます。</span><span class="sxs-lookup"><span data-stu-id="3c197-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="3c197-114">この記事で説明されているよう[に、ユーザーのクラウドボイスメールを有効に](#enable-a-user-for-cloud-voicemail)します。</span><span class="sxs-lookup"><span data-stu-id="3c197-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a><span data-ttu-id="3c197-115">エッジサーバーのホスティングプロバイダーとして Cloud 留守番電話を構成する</span><span class="sxs-lookup"><span data-stu-id="3c197-115">Configure Cloud Voicemail as the hosting provider on the Edge Server</span></span> 

<span data-ttu-id="3c197-116">次のパラメーターを使用して、新しい-CsHostingProvider コマンドレットを使用して、クラウドボイスメールをホスティングプロバイダーとしてフロントエンドサーバーに構成します。</span><span class="sxs-lookup"><span data-stu-id="3c197-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="3c197-117">**Identity**は、作成するホスティングプロバイダーの一意の文字列値識別子を指定します。たとえば、クラウドボイスメールです。</span><span class="sxs-lookup"><span data-stu-id="3c197-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="3c197-118">**Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3c197-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="3c197-119">このパラメーターは True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c197-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="3c197-120">**EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3c197-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="3c197-121">このパラメーターは True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c197-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="3c197-122">**Hostソケット Susers**は、ホスティングプロバイダーが Skype For business Server アカウントをホストするために使用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3c197-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="3c197-123">このパラメーターは False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c197-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="3c197-124">**Proxyfqdn**は、ホスティングプロバイダーによって使用されるプロキシサーバーの完全修飾ドメイン名 (FQDN) を指定します。たとえば、proxyserver.contoso.com のようになります。</span><span class="sxs-lookup"><span data-stu-id="3c197-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="3c197-125">この情報については、ホスティング プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="3c197-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="3c197-126">この値は変更できません。</span><span class="sxs-lookup"><span data-stu-id="3c197-126">This value cannot be modified.</span></span> <span data-ttu-id="3c197-127">ホスティングプロバイダーがプロキシサーバーを変更した場合は、そのプロバイダーのエントリを削除してから再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c197-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="3c197-128">**Islocal**は、ホスティングプロバイダーによって使用されるプロキシサーバーが Skype For business server のトポロジ内に含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3c197-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="3c197-129">このパラメーターは False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c197-129">This parameter must be set to False.</span></span>

<span data-ttu-id="3c197-130">たとえば、Skype for Business 管理シェルでは、次のコマンドレットにより、クラウドボイスメールがホスティングプロバイダーとして構成されます。</span><span class="sxs-lookup"><span data-stu-id="3c197-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="3c197-131">ホスト型ボイスメールポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="3c197-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="3c197-132">組織のボイスメールがクラウドボイスメールサービスにルーティングされるようにするには、組織に対してホスト型ボイスメールポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c197-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="3c197-133">多くの場合、ホストボイスメールポリシーは1つだけ必要であり、グローバルポリシーを変更してすべてのニーズを満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="3c197-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="3c197-134">組織で複数のホスト型ボイスメールポリシーが必要な場合は、set-cshostedvoicemailpolicy コマンドレットを使用してポリシーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="3c197-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="3c197-135">グローバルポリシーを変更するには、組織と TenantID を更新した後、Skype for Business Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3c197-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -Tenant “11111111-1111-1111-1111-111111111111”
```

- <span data-ttu-id="3c197-136">**Destination**には、ホストされているクラウドボイスメールサービスの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c197-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="3c197-137">この値は、 **exap.um.outlook.com**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c197-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="3c197-138">**組織**は、テナントに割り当てられている既定のドメインです。</span><span class="sxs-lookup"><span data-stu-id="3c197-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="3c197-139">この情報を取得するには、テナント管理者が office.com にログインし、[管理センター] アプリをクリックして、左側の [**セットアップ**] に移動し、[**ドメイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c197-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="3c197-140">例: mytenant.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="3c197-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="3c197-141">組織名は、Office 365 の既定のドメイン名でもあります。</span><span class="sxs-lookup"><span data-stu-id="3c197-141">The Organization name is also the Default Domain name in Office 365.</span></span>

- <span data-ttu-id="3c197-142">**テナント**は、Office 365 でテナントを識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3c197-142">**Tenant** is used to identify your tenant in Office 365.</span></span> <span data-ttu-id="3c197-143">詳細については、「 [Office の Office 365 テナント ID を検索する](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c197-143">For more information, see [Find your Office 365 tenant ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>

<span data-ttu-id="3c197-144">ホスト型ボイスメールポリシーが正常に作成されたことを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3c197-144">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="3c197-145">ホスト型ボイスメールポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="3c197-145">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="3c197-146">既定では、グローバルにホストされるボイスメールポリシーがすべてのユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3c197-146">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="3c197-147">別のポリシーを使用する場合は、ホストされたボイスメールにユーザーを有効にする前に、 [set-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps)コマンドレットを使用して、必要なホストボイスメールポリシーをユーザーに付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c197-147">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="3c197-148">たとえば、次のコマンドを実行すると、非グローバルなホスト型ボイスメールポリシーがユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3c197-148">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="3c197-149">クラウドボイスメールでユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="3c197-149">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="3c197-150">ユーザーのボイスメールをクラウドボイスメールにルーティングできるようにするには、HostedVoiceMail パラメーターを指定して、ユーザーのボイス[メールコマンドレット](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c197-150">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="3c197-151">たとえば、次のコマンドを実行すると、クラウドボイスメールのユーザーアカウントが有効になります。</span><span class="sxs-lookup"><span data-stu-id="3c197-151">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

<span data-ttu-id="3c197-152">このコマンドレットは、クラウドボイスメールポリシーがグローバル、サイト、またはユーザーレベルであることを確認します。--このユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3c197-152">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="3c197-153">適用されるポリシーがない場合には、このコマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="3c197-153">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="3c197-154">次の例では、クラウドボイスメールのユーザーアカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="3c197-154">The next example disables a user account for Cloud Voicemail:</span></span>

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

<span data-ttu-id="3c197-155">このコマンドレットは、ホストされているボイスメールポリシーがないことを確認します。これは、グローバル、サイト、またはユーザーレベルで、このユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3c197-155">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="3c197-156">適用されるポリシーがある場合には、このコマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="3c197-156">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="3c197-157">ユーザーは、Microsoft クラウドボイスメールサービスを使用するために、エンタープライズ voip が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c197-157">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>
