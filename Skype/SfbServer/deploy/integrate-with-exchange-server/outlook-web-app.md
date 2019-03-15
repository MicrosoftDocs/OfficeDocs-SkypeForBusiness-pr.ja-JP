---
title: ビジネス サーバーの設置型の Skype と Outlook Web App との統合を構成します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/7/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: '概要: ビジネス サーバーおよび Outlook Web App の Skype を統合します。'
ms.openlocfilehash: 17f58acac3b59611df58d4c60ce875a5a17187cf
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569631"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="4524c-103">ビジネス サーバーの設置型の Skype と Outlook Web App との統合を構成します。</span><span class="sxs-lookup"><span data-stu-id="4524c-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="4524c-104">**の概要:** ビジネス サーバーおよび Outlook Web App には、Skype を統合します。</span><span class="sxs-lookup"><span data-stu-id="4524c-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="4524c-105">ビジネス サーバー展開では、オンプレミスの Skype を使用しているお客様は、ハイブリッド展開モードで、Microsoft Exchange Online での Microsoft Outlook Web App での相互運用性を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4524c-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="4524c-106">相互運用性機能には、シングル サインオンが含まれるほか、Outlook Web App インターフェイスとのインスタント メッセージングおよびプレゼンスの統合が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4524c-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="4524c-107">この統合を有効にするには、次のタスクを完了して、設置の Skype ビジネス サーバーの展開にエッジ サーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4524c-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="4524c-108">共有 SIP アドレス スペースを構成する</span><span class="sxs-lookup"><span data-stu-id="4524c-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="4524c-109">エッジ サーバー上でホスティング プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4524c-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="4524c-110">更新された中央管理ストアのレプリケーションを確認します。</span><span class="sxs-lookup"><span data-stu-id="4524c-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="4524c-111">共有 SIP アドレス スペースを構成する</span><span class="sxs-lookup"><span data-stu-id="4524c-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="4524c-112">Exchange のオンラインでのビジネスのサーバーの設置型の Skype を統合するために共有 SIP アドレス スペースを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4524c-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="4524c-113">同じ SIP ドメインのアドレス スペースは、Skype のビジネス サーバーと Exchange のオンライン サービスの両方でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4524c-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="4524c-114">ビジネス サーバー管理シェルには、Skype を使用して、次の例に表示されているパラメーターを使用して、**セット CSAccessEdgeConfiguration**コマンドレットを実行して、エッジ サーバーのフェデレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="4524c-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="4524c-115">**AllowFederatedUsers** パラメーターは、内部ユーザーがフェデレーション ドメインからのユーザーと通信することを許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4524c-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="4524c-116">このプロパティは、内部ユーザーが、ビジネスのサーバーと Exchange のオンライン共有 SIP アドレス スペースのシナリオで Skype でのユーザーと通信できるかどうかも決定します。</span><span class="sxs-lookup"><span data-stu-id="4524c-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="4524c-117">ビジネス サーバー管理シェルには、Skype の使用に関する詳細については、 [Skype](../../manage/management-shell.md)ビジネス サーバー管理シェルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4524c-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="4524c-118">エッジ サーバーにホスティング プロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="4524c-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="4524c-119">ビジネス サーバー管理シェルには、Skype を使用して、次の例では、パラメーターを使用して、**新規 CsHostingProvider**コマンドレットを実行してエッジ サーバー上でホスティング プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4524c-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="4524c-120">中国の 21Vianet により運営されている Office 365 を使用している場合は、この例の ProxyFqdn パラメーターの値 ("exap.um.outlook.com") を、21Vianet により運営されているサービスの FQDN である "exap.um.partner.outlook.cn" に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4524c-120">If you are using Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="4524c-121">を使用している Office 365 の GCC の高い場合、FQDN を持つ次の使用例がある場合 ("exap.um.outlook.com") で ProxyFqdn パラメーターの値を交換して、GCC を:"exap.um.office365.us"です。</span><span class="sxs-lookup"><span data-stu-id="4524c-121">If you are using Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="4524c-122">**Identity** は、作成するホスティング プロバイダーの、一意の文字列値から成る識別子を指定します (例: "Exchange Online")。</span><span class="sxs-lookup"><span data-stu-id="4524c-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="4524c-123">空白を含む値は、二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="4524c-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="4524c-124">\*\*Enabled \*\* は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4524c-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="4524c-125">これを True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4524c-125">This must be set to True.</span></span>

- <span data-ttu-id="4524c-126">**EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4524c-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="4524c-127">これを True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4524c-127">This must be set to True.</span></span>

- <span data-ttu-id="4524c-128">**HostsOCSUsers**は、Office Communications Server または Skype をビジネスのサーバーのホストにホスティング プロバイダーを使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4524c-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="4524c-129">これを False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4524c-129">This must be set to False.</span></span>

- <span data-ttu-id="4524c-130">**ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="4524c-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="4524c-131">Exchange Online の FQDN は exap.um.outlook.com です。</span><span class="sxs-lookup"><span data-stu-id="4524c-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="4524c-132">**IsLocal**は、ビジネスのサーバー トポロジの場合、Skype 内でホスティング プロバイダーで使用するプロキシ サーバーが含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4524c-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="4524c-133">これを False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4524c-133">This must be set to False.</span></span>

- <span data-ttu-id="4524c-134">**VerificationLevel**ホストされるプロバイダーとの間に送信できるメッセージの確認レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4524c-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="4524c-135">**UseSourceVerification**、ホスティング プロバイダーから送信されたメッセージに含まれている検証のレベルに依存する部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="4524c-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="4524c-136">このレベルが指定されていない場合、メッセージは、確認不能として拒否されます。</span><span class="sxs-lookup"><span data-stu-id="4524c-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="4524c-137">更新された中央管理ストアのレプリケーションを確認する</span><span class="sxs-lookup"><span data-stu-id="4524c-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="4524c-138">コマンドレットを使用して、前のセクションで、加えた変更は、エッジ サーバーに自動的に適用し、を複製するのには 1 分未満がかかります。</span><span class="sxs-lookup"><span data-stu-id="4524c-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="4524c-139">レプリケーションの状態を検証し、次のコマンドレットを使用して、エッジ サーバーに変更が適用されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4524c-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="4524c-140">ビジネス サーバーの展開、Skype の内部のサーバー上のレプリケーションの更新を確認するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4524c-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="4524c-141">古く値がすべてのレプリカの true の場合に表示されているかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4524c-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="4524c-142">エッジ サーバーで、変更が適用されたことを確認するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4524c-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="4524c-143">情報が表示されますが、前の手順でコミットされた変更と一致する場合は、二重にチェックします。</span><span class="sxs-lookup"><span data-stu-id="4524c-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="4524c-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="4524c-144">See also</span></span>

[<span data-ttu-id="4524c-145">Skype を提供するビジネスのサーバーのユーザーのボイス メールでホストされている Exchange UM</span><span class="sxs-lookup"><span data-stu-id="4524c-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="4524c-146">ホストされている Exchange ユニファイド メッセージング統合の Skype ビジネス サーバーの</span><span class="sxs-lookup"><span data-stu-id="4524c-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
