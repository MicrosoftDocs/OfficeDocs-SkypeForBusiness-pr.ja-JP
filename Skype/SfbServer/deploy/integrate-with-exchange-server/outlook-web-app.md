---
title: オンプレミスの Skype for Business Server と Outlook Web App との統合を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: '概要: Skype for Business Server と Outlook Web App の統合。'
ms.openlocfilehash: b7c279dc41515d9613d8c000ab9e81164a1ccaa6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244211"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="efb02-103">オンプレミスの Skype for Business Server と Outlook Web App との統合を構成する</span><span class="sxs-lookup"><span data-stu-id="efb02-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="efb02-104">**概要:** Skype for Business Server と Outlook Web App を統合します。</span><span class="sxs-lookup"><span data-stu-id="efb02-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="efb02-105">オンプレミスの Skype for Business Server 展開を使用しているお客様は、ハイブリッド展開モードで Microsoft Exchange Online の Microsoft Outlook Web App との相互運用性を構成できます。</span><span class="sxs-lookup"><span data-stu-id="efb02-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="efb02-106">相互運用性機能には、シングル サインオンが含まれるほか、Outlook Web App インターフェイスとのインスタント メッセージングおよびプレゼンスの統合が含まれます。</span><span class="sxs-lookup"><span data-stu-id="efb02-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="efb02-107">この統合を有効にするには、次のタスクを実行して、オンプレミスの Skype for Business Server 展開でエッジサーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb02-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="efb02-108">共有 SIP アドレス スペースを構成する</span><span class="sxs-lookup"><span data-stu-id="efb02-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="efb02-109">エッジサーバーでホスティングプロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="efb02-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="efb02-110">更新された中央管理ストアのレプリケーションを確認する</span><span class="sxs-lookup"><span data-stu-id="efb02-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="efb02-111">共有 SIP アドレス スペースを構成する</span><span class="sxs-lookup"><span data-stu-id="efb02-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="efb02-112">オンプレミスの Skype for Business Server を Exchange Online と統合するには、共有 SIP アドレス空間を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb02-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="efb02-113">同じ SIP ドメインアドレス空間は、Skype for Business Server と Exchange Online サービスの両方でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="efb02-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="efb02-114">次の例に示すパラメーターを使用して、 **CSAccessEdgeConfiguration**コマンドレットを実行して、Skype For Business Server 管理シェルを使ってフェデレーション用にエッジサーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="efb02-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="efb02-115">**AllowFederatedUsers** パラメーターは、内部ユーザーがフェデレーション ドメインからのユーザーと通信することを許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="efb02-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="efb02-116">このプロパティは、Skype for Business Server および Exchange Online で、内部ユーザーが共有 SIP アドレス空間のシナリオでユーザーと通信できるかどうかも決定します。</span><span class="sxs-lookup"><span data-stu-id="efb02-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="efb02-117">Skype for Business Server 管理シェルの使い方の詳細については、「Skype for business [Server 管理シェル](../../manage/management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb02-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="efb02-118">エッジ サーバーにホスティング プロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="efb02-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="efb02-119">Skype for Business Server 管理シェルを使用して、次の例のパラメーターを使用して、**新しい-CsHostingProvider**コマンドレットを実行して、エッジサーバーでホスティングプロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="efb02-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="efb02-120">中国の 21Vianet により運営されている Office 365 を使用している場合は、この例の ProxyFqdn パラメーターの値 ("exap.um.outlook.com") を、21Vianet により運営されているサービスの FQDN である "exap.um.partner.outlook.cn" に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="efb02-120">If you are using Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="efb02-121">Office 365 GCC High を使用している場合は、この例の ProxyFqdn パラメーター ("exap.um.outlook.com") の値を、GCC High: "exap.um.office365.us" の FQDN に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="efb02-121">If you are using Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="efb02-122">**Identity** は、作成するホスティング プロバイダーの、一意の文字列値から成る識別子を指定します (例: "Exchange Online")。</span><span class="sxs-lookup"><span data-stu-id="efb02-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="efb02-123">空白を含む値は、二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb02-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="efb02-124">\*\*Enabled \*\* は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="efb02-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="efb02-125">これを True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb02-125">This must be set to True.</span></span>

- <span data-ttu-id="efb02-126">**EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="efb02-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="efb02-127">これを True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb02-127">This must be set to True.</span></span>

- <span data-ttu-id="efb02-128">**Hostているユーザー**は、ホスティングプロバイダーが Office Communications server または Skype For business Server をホストするために使用されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="efb02-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="efb02-129">これを False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb02-129">This must be set to False.</span></span>

- <span data-ttu-id="efb02-130">**ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="efb02-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="efb02-131">Exchange Online の FQDN は exap.um.outlook.com です。</span><span class="sxs-lookup"><span data-stu-id="efb02-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="efb02-132">**Islocal**は、ホスティングプロバイダーによって使用されたプロキシサーバーが Skype For business server トポロジ内に含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="efb02-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="efb02-133">これを False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb02-133">This must be set to False.</span></span>

- <span data-ttu-id="efb02-134">**VerificationLevel**ホストされているプロバイダーとの間で送受信されるメッセージに対して許可される確認レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="efb02-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="efb02-135">ホスティング\*\*\*\* プロバイダーから送信されたメッセージに含まれている確認レベルに依存する、"いいね" を指定します。</span><span class="sxs-lookup"><span data-stu-id="efb02-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="efb02-136">このレベルが指定されていない場合、メッセージは、確認不能として拒否されます。</span><span class="sxs-lookup"><span data-stu-id="efb02-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="efb02-137">更新された中央管理ストアのレプリケーションを確認する</span><span class="sxs-lookup"><span data-stu-id="efb02-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="efb02-138">前のセクションのコマンドレットを使用して行った変更は、エッジサーバーに自動的に適用され、通常、複製には1分未満かかります。</span><span class="sxs-lookup"><span data-stu-id="efb02-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="efb02-139">レプリケーションの状態を確認し、次のコマンドレットを使用して、変更がエッジサーバーに適用されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="efb02-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="efb02-140">レプリケーションの更新を確認するには、Skype for Business Server の展開の内部サーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="efb02-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="efb02-141">UpToDate 値がすべてのレプリカの TRUE として表示されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="efb02-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="efb02-142">変更が適用されたことを確認するには、エッジサーバーで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="efb02-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="efb02-143">表示されている情報が、前の手順でコミットした変更内容と一致するかどうかをダブルチェックします。</span><span class="sxs-lookup"><span data-stu-id="efb02-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="efb02-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="efb02-144">See also</span></span>

[<span data-ttu-id="efb02-145">ホストされている Exchange UM での Skype for Business Server ユーザーのボイスメールの提供</span><span class="sxs-lookup"><span data-stu-id="efb02-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="efb02-146">Skype for Business Server でのホストされた Exchange ユニファイドメッセージングの統合</span><span class="sxs-lookup"><span data-stu-id="efb02-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
