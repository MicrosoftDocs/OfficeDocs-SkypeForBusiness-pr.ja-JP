---
title: クラウド ボイスメール サービスを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/9/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: ビジネス サーバーの Skype ホーム ユーザーのクラウド ベースのボイスメールが実装する方法について。
ms.openlocfilehash: 9cc990cbaecfea74b269809d9e31588d61eee93c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027817"
---
# <a name="configure-cloud-voicemail-service"></a><span data-ttu-id="e9b30-103">クラウド ボイスメール サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-103">Configure Cloud Voicemail service</span></span>


[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a><span data-ttu-id="e9b30-104">概要</span><span class="sxs-lookup"><span data-stu-id="e9b30-104">Overview</span></span> 
<span data-ttu-id="e9b30-105">この資料では、オンプレミス ユーザーのビジネスを Skype のマイクロソフトのクラウドのボイスメール サービスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="e9b30-106">この資料では、ビジネスのサーバーでサポートされているトポロジでは、展開の Skype が既にあることと、ハイブリッドの接続を設定するための前提条件が満たされていると仮定します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="e9b30-107">利点の詳細については、計画の考慮事項、およびクラウドのボイスメールを実装するための要件[計画クラウド ボイスメール サービス](plan-cloud-voicemail.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9b30-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="e9b30-108">クラウドのボイス メールを構成するには、次のタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e9b30-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="e9b30-109">[計画クラウドのボイスメール サービス](plan-cloud-voicemail.md)の説明に従って、前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="e9b30-110">[ハイブリッド接続の計画](plan-hybrid-connectivity.md)と[構成のハイブリッドの接続](configure-hybrid-connectivity.md)で説明したように、ハイブリッド接続の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="e9b30-111">[クラウド ボイスメールをエッジ サーバー上でホスティング プロバイダーとして構成する](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server)と、この資料に記載します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) as described in this article.</span></span>

4.  <span data-ttu-id="e9b30-112">[ホスト ボイスメール ポリシーを構成する](#configure-a-hosted-voicemail-policy)この資料で説明されているようです。</span><span class="sxs-lookup"><span data-stu-id="e9b30-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="e9b30-113">この資料で説明するよう[ホスト ボイスメール ポリシーを設定](#assign-a-hosted-voicemail-policy)。</span><span class="sxs-lookup"><span data-stu-id="e9b30-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="e9b30-114">[クラウド ボイスメールに対してユーザーを有効にする](#enable-a-user-for-cloud-voicemail)この資料で説明されているようです。</span><span class="sxs-lookup"><span data-stu-id="e9b30-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a><span data-ttu-id="e9b30-115">エッジ サーバー上でホスティング プロバイダーとしてのクラウドのボイス メールの構成します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-115">Configure Cloud Voicemail as the hosting provider on the Edge Server</span></span> 

<span data-ttu-id="e9b30-116">クラウドのボイスメールをエッジ サーバー上でホスティング プロバイダーとして構成するには、次のパラメーターを使用して新規 CsHostingProvider コマンドレットを使用しています。</span><span class="sxs-lookup"><span data-stu-id="e9b30-116">You configure Cloud Voicemail as the hosting provider on the Edge Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="e9b30-117">**Id**作成するホスティング プロバイダーの一意の文字列値の識別子を指定します。などのクラウドのボイスメールです。</span><span class="sxs-lookup"><span data-stu-id="e9b30-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="e9b30-118">\*\*Enabled \*\* は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="e9b30-119">このパラメーターを True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9b30-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="e9b30-120">**EnabledSharedAddressSpace**では、ホスティング プロバイダーが共有 SIP アドレス スペースのシナリオで使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="e9b30-121">このパラメーターを True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9b30-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="e9b30-122">**HostsOCSUsers**は、ビジネス サーバー アカウントの Skype をホストするホスティング プロバイダーを使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="e9b30-123">このパラメーターを False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9b30-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="e9b30-124">**ProxyFQDN**は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。たとえば、proxyserver.contoso.com です。</span><span class="sxs-lookup"><span data-stu-id="e9b30-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="e9b30-125">この情報は、ホスティング プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="e9b30-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="e9b30-126">この値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e9b30-126">This value cannot be modified.</span></span> <span data-ttu-id="e9b30-127">ホスティング プロバイダーは、そのプロキシ サーバーを変更する場合は、削除し、そのプロバイダーのエントリを再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9b30-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="e9b30-128">**IsLocal**は、ビジネスのサーバー トポロジの場合、Skype 内でホスティング プロバイダーで使用するプロキシ サーバーが含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="e9b30-129">このパラメーターを False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9b30-129">This parameter must be set to False.</span></span>

<span data-ttu-id="e9b30-130">たとえば、ビジネス管理シェルの Skype で次のコマンドレットでは、クラウドのボイスメールとして構成ホスティング プロバイダー。</span><span class="sxs-lookup"><span data-stu-id="e9b30-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="e9b30-131">ホスト ボイスメール ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="e9b30-132">ボイスメールのクラウド サービスにルーティング組織のボイスメールを確認するのには、組織のホスト ボイスメール ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9b30-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="e9b30-133">多くの場合、1 つだけのホスト ボイスメール ポリシーが必要なと、すべてのニーズに対応するグローバル ポリシーを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e9b30-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="e9b30-134">組織は、複数のホスト ボイスメール ポリシーを必要とする場合は、cshostedvoicemailpolicy で新しいコマンドレットを使用してポリシーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="e9b30-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="e9b30-135">グローバル ポリシーを変更するには、次コマンドを実行、Skype のビジネス サーバーの管理シェル、組織と TenantID を更新した後。</span><span class="sxs-lookup"><span data-stu-id="e9b30-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- <span data-ttu-id="e9b30-136">**送信先**は、ホストされたクラウドのボイスメール サービスの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="e9b30-137">**Exap.um.outlook.com**には、この値を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9b30-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="e9b30-138">**組織**では、テナントに割り当てられている既定のドメインです。</span><span class="sxs-lookup"><span data-stu-id="e9b30-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="e9b30-139">テナント管理者 office.com にログイン管理センターのアプリケーションに、左側の [**セットアップ**へ移動を [**ドメイン**] をクリックすることにより、この情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="e9b30-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="e9b30-140">例: mytenant.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="e9b30-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="e9b30-141">組織の名前が Office 365 の既定のドメイン名もあります。</span><span class="sxs-lookup"><span data-stu-id="e9b30-141">The Organization name is also the Default Domain name in Office 365.</span></span>

- <span data-ttu-id="e9b30-142">**TenantID**を使用して、Office 365 で、テナントを識別します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-142">**TenantID** is used to identify your tenant in Office 365.</span></span> <span data-ttu-id="e9b30-143">詳細については[、Office 365 のテナント ID を検索](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9b30-143">For more information, see [Find your Office 365 tenant ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>

<span data-ttu-id="e9b30-144">ホスト ボイスメール ポリシーが正常に作成されたことを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-144">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="e9b30-145">ホスト ボイスメール ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e9b30-145">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="e9b30-146">既定でホストされているグローバル ボイスメール ポリシーがすべてのユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e9b30-146">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="e9b30-147">ホスト ボイスメールに対してユーザーを有効にする前に、別のポリシーを使用する場合する必要があります最初ユーザーに与える目的のホスト ボイスメール ポリシー[許可 CSHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps)コマンドレットを使用しています。</span><span class="sxs-lookup"><span data-stu-id="e9b30-147">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="e9b30-148">たとえば、次のコマンドは、ユーザーに非グローバルのホスト ボイスメール ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e9b30-148">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="e9b30-149">クラウド ボイスメールに対してユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e9b30-149">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="e9b30-150">クラウドのボイスメールにルーティングするユーザーのボイス メールの呼び出しを有効にするには、HostedVoiceMail パラメーターを使用して[セット CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuser?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-150">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="e9b30-151">たとえば、次のコマンドでは、クラウドのボイスメールのユーザー アカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e9b30-151">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

<span data-ttu-id="e9b30-152">コマンドレットを確認するクラウドのボイスメール ポリシー--グローバル、サイト、またはユーザー レベル--は、このユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9b30-152">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="e9b30-153">ポリシーが適用されない場合、コマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-153">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="e9b30-154">次の例では、クラウドのボイスメールのユーザー アカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e9b30-154">The next example disables a user account for Cloud Voicemail:</span></span>

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

<span data-ttu-id="e9b30-155">コマンドレットを確認、グローバル--ホスト ボイスメール ポリシーがサイト、またはユーザー レベル--は、このユーザーに適用されません。</span><span class="sxs-lookup"><span data-stu-id="e9b30-155">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="e9b30-156">ポリシーが適用される場合は、コマンドレットが失敗します。</span><span class="sxs-lookup"><span data-stu-id="e9b30-156">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="e9b30-157">ユーザーには、エンタープライズ ボイスのマイクロソフトのクラウドのボイスメール サービスを使用するのには有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9b30-157">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>