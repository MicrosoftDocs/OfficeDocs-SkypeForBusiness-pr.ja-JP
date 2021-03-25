---
title: オンプレミス ユーザー向けクラウド ボイスメール サービスの構成
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
description: Skype for Business Server に保存されているユーザーのクラウドベースのボイスメールを実装する手順。
ms.openlocfilehash: a9c308189a5dc70c85382f638f30f52c0ac69bdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118986"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="ea8d4-103">オンプレミス ユーザー向けクラウド ボイスメール サービスの構成</span><span class="sxs-lookup"><span data-stu-id="ea8d4-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="ea8d4-104">概要</span><span class="sxs-lookup"><span data-stu-id="ea8d4-104">Overview</span></span> 
<span data-ttu-id="ea8d4-105">この記事では、Skype for Business オンプレミス ユーザー用に Microsoft Cloud ボイスメール サービスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="ea8d4-106">この記事では、サポートされているトポロジに Skype for Business Server が既に展開済みであり、ハイブリッド接続をセットアップするための前提条件を満たしていることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="ea8d4-107">クラウド ボイスメールを実装するための利点、計画上の考慮事項、および要件の詳細については、「Plan Cloud ボイスメール サービス」 [を参照してください](plan-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="ea8d4-108">クラウド ボイスメールの構成には、次のタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="ea8d4-109">「Plan Cloud ボイスメール サービス」の説明に従って、 [前提条件を満たしていることを確認します](plan-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="ea8d4-110">「ハイブリッド接続の計画」および「ハイブリッド接続の構成[](plan-hybrid-connectivity.md)」の説明に従って、ハイブリッド接続をセットアップ[してください。](configure-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="ea8d4-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="ea8d4-111">[この記事で説明するように、](#configure-cloud-voicemail-as-the-hosting-provider) フロントエンド サーバー上のホスティング プロバイダーとしてクラウド ボイスメールを構成します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-111">[Configure Cloud Voicemail as the hosting provider on the Front End Server](#configure-cloud-voicemail-as-the-hosting-provider) as described in this article.</span></span>

4.  <span data-ttu-id="ea8d4-112">[この記事の説明に従って、](#configure-a-hosted-voicemail-policy) ホストされたボイスメール ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="ea8d4-113">[この記事の説明に従って、](#assign-a-hosted-voicemail-policy) ホストされたボイスメール ポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="ea8d4-114">[この記事の説明に従って、クラウド](#enable-a-user-for-cloud-voicemail) ボイスメールのユーザーを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a><span data-ttu-id="ea8d4-115">クラウド ボイスメールをホスティング プロバイダーとして構成する</span><span class="sxs-lookup"><span data-stu-id="ea8d4-115">Configure Cloud Voicemail as the hosting provider</span></span> 

<span data-ttu-id="ea8d4-116">次のパラメーターを使用して、クラウド ボイスメールをフロントエンド サーバーのホスティング プロバイダーNew-CsHostingProvider構成します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="ea8d4-117">**Identity** は、作成するホスティング プロバイダーの一意の文字列値識別子を指定します。たとえば、クラウド ボイスメール。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="ea8d4-118">**Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="ea8d4-119">このパラメーターは True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="ea8d4-120">**EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="ea8d4-121">このパラメーターは True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="ea8d4-122">**HostsOCSUsers は** 、ホスティング プロバイダーを使用して Skype for Business Server アカウントをホストするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="ea8d4-123">このパラメーターは False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="ea8d4-124">**ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。たとえば、proxyserver.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="ea8d4-125">この情報については、ホスティング プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="ea8d4-126">この値は変更できません。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-126">This value cannot be modified.</span></span> <span data-ttu-id="ea8d4-127">ホスティング プロバイダーがプロキシ サーバーを変更する場合は、そのプロバイダーのエントリを削除してから再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="ea8d4-128">**IsLocal は** 、ホスティング プロバイダーによって使用されるプロキシ サーバーが Skype for Business Server トポロジ内に含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="ea8d4-129">このパラメーターは False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-129">This parameter must be set to False.</span></span>

<span data-ttu-id="ea8d4-130">たとえば、Skype for Business 管理シェルで、次のコマンドレットはクラウド ボイスメールをホスティング プロバイダーとして構成します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="ea8d4-131">ホストされたボイスメール ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="ea8d4-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="ea8d4-132">組織のボイスメールがクラウド ボイスメール サービスにルーティングされるのを確認するには、組織のホストボイスメール ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="ea8d4-133">多くの場合、ホストされるボイスメール ポリシーは 1 つのみ必要であり、すべてのニーズに合わせてグローバル ポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="ea8d4-134">組織で複数のホストされたボイスメール ポリシーが必要な場合は、new-cshostedvoicemailpolicy コマンドレットを使用してポリシーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="ea8d4-135">グローバル ポリシーを変更するには、組織と TenantID を更新した後、Skype for Business Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- <span data-ttu-id="ea8d4-136">**Destination** は、ホストされたクラウド ボイスメール サービスの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="ea8d4-137">この値は、次の値に **exap.um.outlook.com。**</span><span class="sxs-lookup"><span data-stu-id="ea8d4-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="ea8d4-138">**組織** は、テナントに割り当てられている既定のドメインです。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="ea8d4-139">この情報を取得するには、テナント管理者が office.com にログインし、管理センター アプリをクリックし、左側の[セットアップ] に移動し、[ドメイン] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="ea8d4-140">たとえば、次の mytenant.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="ea8d4-141">組織名は、Microsoft 365 または 365 の既定Officeです。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-141">The Organization name is also the Default Domain name in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="ea8d4-142">ホストされたボイスメール ポリシーが正常に作成されたことを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-142">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="ea8d4-143">ホストされたボイスメール ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="ea8d4-143">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="ea8d4-144">既定では、グローバル ホストボイスメール ポリシーは、すべてのユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-144">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="ea8d4-145">別のポリシーを使用する場合は、ホストされたボイスメールのユーザーを有効にする前に、 [まず Grant-CSHostedVoicemailPolicy](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) コマンドレットを使用して、ユーザーに必要なホスト型ボイスメール ポリシーを付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-145">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="ea8d4-146">たとえば、次のコマンドは、グローバル以外のホストボイスメール ポリシーをユーザーに割り当てします。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-146">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="ea8d4-147">クラウド ボイスメールのユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="ea8d4-147">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="ea8d4-148">ユーザーのボイスメール通話をクラウド ボイスメールにルーティングするには [、HostedVoiceMail パラメーターで Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-148">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="ea8d4-149">たとえば、次のコマンドを使用すると、クラウド ボイスメールのユーザー アカウントが有効になります。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-149">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

<span data-ttu-id="ea8d4-150">このコマンドレットは、グローバル、サイト、またはユーザー レベルのクラウド ボイスメール ポリシーが、このユーザーに適用されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-150">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="ea8d4-151">適用されるポリシーがない場合には、このコマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-151">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="ea8d4-152">次の例では、クラウド ボイスメールのユーザー アカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-152">The next example disables a user account for Cloud Voicemail:</span></span>

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

<span data-ttu-id="ea8d4-153">このコマンドレットは、ホストされたボイスメール ポリシー (グローバル、サイト、またはユーザー レベル) がこのユーザーに適用されていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-153">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="ea8d4-154">適用されるポリシーがある場合には、このコマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-154">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="ea8d4-155">Microsoft Cloud ボイスメール サービスを使用するには、ユーザーがエンタープライズ音声を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea8d4-155">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>