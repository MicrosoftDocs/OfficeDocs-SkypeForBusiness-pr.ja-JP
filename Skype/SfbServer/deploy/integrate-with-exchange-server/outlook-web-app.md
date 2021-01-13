---
title: オンプレミスの Skype for Business Server と組織の間の統合をOutlook Web App
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: '概要: Skype for Business Server と Outlook Web App。'
ms.openlocfilehash: 0a6358c93356bd059aeed34033b07916d856bf10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833967"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="4be6c-103">オンプレミスの Skype for Business Server と組織の間の統合をOutlook Web App</span><span class="sxs-lookup"><span data-stu-id="4be6c-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="4be6c-104">**概要:** Skype for Business Server と Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="4be6c-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="4be6c-105">オンプレミスの Skype for Business Server 展開を使用しているお客様は、ハイブリッド展開モードで Microsoft Outlook Web App Microsoft Exchange Online相互運用性を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4be6c-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="4be6c-106">相互運用性機能には、シングル サインオンとインスタント メッセージング (IM) とプレゼンスの統合が含Outlook Web Appがあります。</span><span class="sxs-lookup"><span data-stu-id="4be6c-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="4be6c-107">この統合を有効にするには、次のタスクを実行して、オンプレミスの Skype for Business Server 展開でエッジ サーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4be6c-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="4be6c-108">共有 SIP アドレス スペースを構成する</span><span class="sxs-lookup"><span data-stu-id="4be6c-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="4be6c-109">エッジ サーバーでホスティング プロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="4be6c-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="4be6c-110">更新された中央管理ストアのレプリケーションを確認する</span><span class="sxs-lookup"><span data-stu-id="4be6c-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="4be6c-111">共有 SIP アドレス スペースを構成する</span><span class="sxs-lookup"><span data-stu-id="4be6c-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="4be6c-112">オンプレミスの Skype for Business Server を Exchange Online と統合するには、共有 SIP アドレス スペースを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4be6c-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="4be6c-113">同じ SIP ドメイン アドレス スペースは、Skype for Business Server と Exchange Online サービスの両方でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4be6c-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="4be6c-114">Skype for Business Server 管理シェルを使用して、次の例に示すパラメーターを使用して **Set-CSAccessEdgeConfiguration** コマンドレットを実行して、フェデレーション用にエッジ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4be6c-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="4be6c-115">**AllowFederatedUsers** パラメーターは、内部ユーザーがフェデレーション ドメインのユーザーと通信できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4be6c-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="4be6c-116">また、このプロパティは、内部ユーザーが Skype for Business Server および Exchange Online との共有 SIP アドレス スペース シナリオでユーザーと通信できるかどうかも決定します。</span><span class="sxs-lookup"><span data-stu-id="4be6c-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="4be6c-117">Skype for Business Server 管理シェルの使用の詳細については [、「Skype for Business Server Management Shell」を参照してください](../../manage/management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="4be6c-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="4be6c-118">エッジ サーバーでホスティング プロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="4be6c-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="4be6c-119">Skype for Business Server 管理シェルを使用して、次の例のパラメーターを使用して **New-CsHostingProvider** コマンドレットを実行して、エッジ サーバーでホスティング プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4be6c-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="4be6c-120">中国の 21Vianet が運用している Microsoft 365 または Office 365 を使用している場合は、この例の ProxyFqdn パラメーターの値 ("exap.um.outlook.com") を、21Vianet が運用しているサービスの FQDN ("exap.um.partner.outlook.cn") に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="4be6c-120">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="4be6c-121">Microsoft 365 または Office 365 GCC High を使用している場合は、この例の ProxyFqdn パラメーターの値 ("exap.um.outlook.com") を GCC High : "exap.um.office365.us" の FQDN に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="4be6c-121">If you are using Microsoft 365 or Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="4be6c-122">**Identity** は、作成するホスティング プロバイダーの一意の文字列値識別子を指定します (例: "Exchange Online")。</span><span class="sxs-lookup"><span data-stu-id="4be6c-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="4be6c-123">スペースを含む値は二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="4be6c-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="4be6c-124">**Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4be6c-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="4be6c-125">True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4be6c-125">This must be set to True.</span></span>

- <span data-ttu-id="4be6c-126">**EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4be6c-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="4be6c-127">True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4be6c-127">This must be set to True.</span></span>

- <span data-ttu-id="4be6c-128">**HostsOCSUsers は** 、ホスティング プロバイダーが Communications Server または Skype for Business Server のOfficeに使用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4be6c-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="4be6c-129">これは False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4be6c-129">This must be set to False.</span></span>

- <span data-ttu-id="4be6c-130">**ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="4be6c-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="4be6c-131">Exchange Online の場合、FQDN はexap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="4be6c-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="4be6c-132">**IsLocal** は、ホスティング プロバイダーによって使用されるプロキシ サーバーが Skype for Business Server トポロジ内に含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4be6c-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="4be6c-133">これは False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4be6c-133">This must be set to False.</span></span>

- <span data-ttu-id="4be6c-134">**VerificationLevel** ホストされるプロバイダーとの間で送信されるメッセージに対して許可される検証レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4be6c-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="4be6c-135">ホスティング プロバイダーから送信されたメッセージに含まれる確認レベルを信頼する **UseSourceVerification** を指定します。</span><span class="sxs-lookup"><span data-stu-id="4be6c-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="4be6c-136">このレベルを指定しない場合、メッセージは確認不可として拒否されます。</span><span class="sxs-lookup"><span data-stu-id="4be6c-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="4be6c-137">更新された中央管理ストアのレプリケーションを確認する</span><span class="sxs-lookup"><span data-stu-id="4be6c-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="4be6c-138">前のセクションのコマンドレットを使用して行った変更は、エッジ サーバーに自動的に適用され、通常、レプリケートに 1 分未満かかっています。</span><span class="sxs-lookup"><span data-stu-id="4be6c-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="4be6c-139">次のコマンドレットを使用して、レプリケーションの状態を検証し、変更がエッジ サーバーに適用されたのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4be6c-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="4be6c-140">レプリケーションの更新を確認するには、Skype for Business Server 展開の内部サーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4be6c-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```powershell
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="4be6c-141">UpToDate の値がすべてのレプリカに対して TRUE と表示されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="4be6c-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="4be6c-142">変更が適用されたのを確認するには、エッジ サーバーで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4be6c-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```powershell
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="4be6c-143">表示される情報が前の手順でコミットされた変更と一致する場合は、ダブル チェックします。</span><span class="sxs-lookup"><span data-stu-id="4be6c-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="4be6c-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="4be6c-144">See also</span></span>

[<span data-ttu-id="4be6c-145">Hosted Exchange UM で Skype for Business Server ユーザーにボイス メールを提供する</span><span class="sxs-lookup"><span data-stu-id="4be6c-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="4be6c-146">Skype for Business Server での Hosted Exchange ユニファイド メッセージングの統合</span><span class="sxs-lookup"><span data-stu-id="4be6c-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
