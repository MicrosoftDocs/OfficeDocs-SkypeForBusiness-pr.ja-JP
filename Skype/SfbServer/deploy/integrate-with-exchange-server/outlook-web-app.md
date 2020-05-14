---
title: オンプレミスの Skype for Business Server と Outlook Web App 間の統合を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server と Outlook Web App を統合します。'
ms.openlocfilehash: ee5676c0dbe88568af78a1c278eea8a46457cb5c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221187"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="89fcd-103">オンプレミスの Skype for Business Server と Outlook Web App 間の統合を構成する</span><span class="sxs-lookup"><span data-stu-id="89fcd-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="89fcd-104">**概要:** Skype for Business Server と Outlook Web App を統合します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="89fcd-105">オンプレミスの Skype for Business Server 展開を使用しているお客様は、ハイブリッド展開モードで Microsoft Exchange Online の Microsoft Outlook Web App との相互運用性を構成できます。</span><span class="sxs-lookup"><span data-stu-id="89fcd-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="89fcd-106">相互運用性機能には、Outlook Web App インターフェイスとのシングルサインオン、インスタントメッセージング (IM)、プレゼンス統合が含まれます。</span><span class="sxs-lookup"><span data-stu-id="89fcd-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="89fcd-107">この統合を有効にするには、次のタスクを完了して、オンプレミスの Skype for Business Server 展開でエッジサーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89fcd-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="89fcd-108">共有 SIP アドレススペースを構成する</span><span class="sxs-lookup"><span data-stu-id="89fcd-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="89fcd-109">エッジサーバーのホスティングプロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="89fcd-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="89fcd-110">更新された中央管理ストアのレプリケーションを確認する</span><span class="sxs-lookup"><span data-stu-id="89fcd-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="89fcd-111">共有 SIP アドレススペースを構成する</span><span class="sxs-lookup"><span data-stu-id="89fcd-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="89fcd-112">オンプレミスの Skype for Business Server を Exchange Online と統合するには、共有 SIP アドレススペースを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89fcd-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="89fcd-113">同じ SIP ドメインアドレススペースが、Skype for Business Server と Exchange Online サービスの両方でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="89fcd-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="89fcd-114">Skype for Business Server 管理シェルを使用して、次の例に示されているパラメーターを使用して**set-csaccessedgeconfiguration**コマンドレットを実行し、フェデレーション用にエッジサーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="89fcd-115">**AllowFederatedUsers**パラメーターは、内部ユーザーがフェデレーションドメインからのユーザーと通信できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="89fcd-116">このプロパティは、内部ユーザーが Skype for Business Server と Exchange Online を使用して、共有 SIP アドレススペースシナリオのユーザーと通信できるかどうかも決定します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="89fcd-117">Skype for business Server 管理シェルの使用の詳細については、「 [skype for Business Server Management shell](../../manage/management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89fcd-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="89fcd-118">エッジサーバーのホスティングプロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="89fcd-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="89fcd-119">Skype for Business Server 管理シェルを使用して、次の例のパラメーターを使用して、**新しい-CsHostingProvider**コマンドレットを実行して、エッジサーバーのホスティングプロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="89fcd-120">中国で21Vianet が運用している Microsoft 365 または Office 365 を使用している場合は、この例の ProxyFqdn パラメーター ("exap.um.outlook.com") の値を、21Vianet が運用しているサービスの FQDN に置き換えます。 "exap.um.partner.outlook.cn"。</span><span class="sxs-lookup"><span data-stu-id="89fcd-120">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="89fcd-121">Microsoft 365 または Office 365 GCC High を使用している場合は、この例の ProxyFqdn パラメーターの値 ("exap.um.outlook.com") を、GCC High: "exap.um.office365.us" の FQDN に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="89fcd-121">If you are using Microsoft 365 or Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="89fcd-122">**Identity**は、作成するホスティングプロバイダーの一意の文字列値識別子を指定します (例: "Exchange Online")。</span><span class="sxs-lookup"><span data-stu-id="89fcd-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="89fcd-123">スペースを含む値は、二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="89fcd-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="89fcd-124">**Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="89fcd-125">True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89fcd-125">This must be set to True.</span></span>

- <span data-ttu-id="89fcd-126">**EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="89fcd-127">True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89fcd-127">This must be set to True.</span></span>

- <span data-ttu-id="89fcd-128">**Hostソケット Susers**は、ホスティングプロバイダーが Office Communications server または Skype For business server をホストするために使用されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="89fcd-129">この値は False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89fcd-129">This must be set to False.</span></span>

- <span data-ttu-id="89fcd-130">**ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="89fcd-131">Exchange Online の場合、FQDN は exap.um.outlook.com です。</span><span class="sxs-lookup"><span data-stu-id="89fcd-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="89fcd-132">**Islocal**は、ホスティングプロバイダーによって使用されるプロキシサーバーが Skype For business server のトポロジ内に含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="89fcd-133">この値は False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89fcd-133">This must be set to False.</span></span>

- <span data-ttu-id="89fcd-134">**VerificationLevel**ホストされているプロバイダーとの間で送受信されるメッセージに対して許可される検証レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="89fcd-135">ホスティング プロバイダーから送信されたメッセージに含まれる確認レベルを信頼する **UseSourceVerification** を指定します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="89fcd-136">このレベルが指定されていない場合、メッセージは検証不能として拒否されます。</span><span class="sxs-lookup"><span data-stu-id="89fcd-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="89fcd-137">更新された中央管理ストアのレプリケーションを確認する</span><span class="sxs-lookup"><span data-stu-id="89fcd-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="89fcd-138">前のセクションのコマンドレットを使用して行った変更は、エッジサーバーに自動的に適用され、通常、レプリケートするのに1分未満になります。</span><span class="sxs-lookup"><span data-stu-id="89fcd-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="89fcd-139">次のコマンドレットを使用して、レプリケーションの状態を検証し、変更がエッジサーバーに適用されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="89fcd-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="89fcd-140">レプリケーションの更新を確認するには、Skype for Business Server 展開の内部サーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```powershell
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="89fcd-141">UpToDate value がすべてのレプリカに対して TRUE を示しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="89fcd-142">変更が適用されたことを確認するには、エッジサーバーで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```powershell
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="89fcd-143">表示されている情報が、前の手順で確定した変更内容と一致しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="89fcd-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="89fcd-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="89fcd-144">See also</span></span>

[<span data-ttu-id="89fcd-145">ホストされた Exchange UM で Skype for Business Server ユーザーにボイスメールを提供する</span><span class="sxs-lookup"><span data-stu-id="89fcd-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="89fcd-146">Skype for Business Server でのホスト型 Exchange ユニファイドメッセージングの統合</span><span class="sxs-lookup"><span data-stu-id="89fcd-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
