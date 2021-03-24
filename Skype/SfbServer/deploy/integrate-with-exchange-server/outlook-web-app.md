---
title: オンプレミスの Skype for Business Server とサーバー間の統合を構成Outlook Web App
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
description: '概要: Skype for Business Server とビジネス サーバーを統合Outlook Web App。'
ms.openlocfilehash: daa9430034d82a3a8dee980a9b075b2fc5656c86
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109693"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="9cda7-103">オンプレミスの Skype for Business Server とサーバー間の統合を構成Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="9cda7-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="9cda7-104">**概要:** Skype for Business Server とビジネス サーバーを統合Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="9cda7-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="9cda7-105">オンプレミスの Skype for Business Server 展開を使用しているお客様は、ハイブリッド展開モードで Microsoft Outlook Web App Microsoft Exchange Online相互運用性を構成できます。</span><span class="sxs-lookup"><span data-stu-id="9cda7-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="9cda7-106">相互運用性の機能には、シングル サインオンとインスタント メッセージング (IM) とプレゼンスの統合が含Outlook Web Appがあります。</span><span class="sxs-lookup"><span data-stu-id="9cda7-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="9cda7-107">この統合を有効にするには、次のタスクを実行して、オンプレミスの Skype for Business Server 展開でエッジ サーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cda7-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="9cda7-108">共有 SIP アドレス空間を構成する</span><span class="sxs-lookup"><span data-stu-id="9cda7-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="9cda7-109">エッジ サーバーでホスティング プロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="9cda7-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="9cda7-110">更新されたサーバーの全体管理ストアのレプリケーションを確認する</span><span class="sxs-lookup"><span data-stu-id="9cda7-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="9cda7-111">共有 SIP アドレス空間の構成</span><span class="sxs-lookup"><span data-stu-id="9cda7-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="9cda7-112">オンプレミスの Skype for Business Server を Exchange Online と統合するには、共有 SIP アドレス空間を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cda7-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="9cda7-113">同じ SIP ドメイン アドレス空間は、Skype for Business Server と Exchange Online サービスの両方でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9cda7-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="9cda7-114">Skype for Business Server 管理シェルを使用して、次の例に示すパラメーターを使用して **Set-CSAccessEdgeConfiguration** コマンドレットを実行して、フェデレーション用にエッジ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="9cda7-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="9cda7-115">**AllowFederatedUsers** パラメーターは、内部ユーザーがフェデレーション ドメインのユーザーと通信できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9cda7-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="9cda7-116">このプロパティは、内部ユーザーが Skype for Business Server および Exchange Online との共有 SIP アドレス空間シナリオでユーザーと通信できるかどうかも決定します。</span><span class="sxs-lookup"><span data-stu-id="9cda7-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="9cda7-117">Skype for Business Server 管理シェルの使用の詳細については [、「Skype for Business Server Management Shell」を参照してください](../../manage/management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="9cda7-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="9cda7-118">エッジ サーバーでホスティング プロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="9cda7-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="9cda7-119">Skype for Business Server 管理シェルを使用して、次の例のパラメーターを使用して **、New-CsHostingProvider** コマンドレットを実行してエッジ サーバー上のホスティング プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="9cda7-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="9cda7-120">中国で 21Vianet が運用する Microsoft 365 または Office 365 を使用している場合は、この例 ("exap.um.outlook.com") の ProxyFqdn パラメーターの値を、21Vianet が運用するサービスの FQDN に置き換えてください。"exap.um.partner.outlook.cn"。</span><span class="sxs-lookup"><span data-stu-id="9cda7-120">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="9cda7-121">Microsoft 365 または Office 365 GCC High を使用している場合は、この例 ("exap.um.outlook.com") の ProxyFqdn パラメーターの値を GCC High の FQDN "exap.um.office365.us" に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="9cda7-121">If you are using Microsoft 365 or Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="9cda7-122">**Identity** は、作成するホスティング プロバイダーの一意の文字列値識別子を指定します (たとえば、"Exchange Online")。</span><span class="sxs-lookup"><span data-stu-id="9cda7-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="9cda7-123">スペースを含む値は二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cda7-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="9cda7-124">**Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9cda7-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="9cda7-125">これは True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cda7-125">This must be set to True.</span></span>

- <span data-ttu-id="9cda7-126">**EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9cda7-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="9cda7-127">これは True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cda7-127">This must be set to True.</span></span>

- <span data-ttu-id="9cda7-128">**HostsOCSUsers は** 、ホスティング プロバイダーを使用して通信サーバーまたは Skype for Business Server Officeホストするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9cda7-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="9cda7-129">これは False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cda7-129">This must be set to False.</span></span>

- <span data-ttu-id="9cda7-130">**ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cda7-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="9cda7-131">Exchange Online の場合、FQDN は exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="9cda7-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="9cda7-132">**IsLocal は** 、ホスティング プロバイダーによって使用されるプロキシ サーバーが Skype for Business Server トポロジ内に含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9cda7-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="9cda7-133">これは False に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cda7-133">This must be set to False.</span></span>

- <span data-ttu-id="9cda7-134">**VerificationLevel** ホストされているプロバイダーとの間で送信されるメッセージに対して許可される検証レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="9cda7-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="9cda7-135">ホスティング プロバイダーから送信されたメッセージに含まれる確認レベルを信頼する **UseSourceVerification** を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cda7-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="9cda7-136">このレベルを指定しない場合、メッセージは確認できないとして拒否されます。</span><span class="sxs-lookup"><span data-stu-id="9cda7-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="9cda7-137">更新された中央管理ストアのレプリケーションを確認する</span><span class="sxs-lookup"><span data-stu-id="9cda7-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="9cda7-138">前のセクションのコマンドレットを使用して行った変更は、エッジ サーバーに自動的に適用され、一般にレプリケートに 1 分未満かかっています。</span><span class="sxs-lookup"><span data-stu-id="9cda7-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="9cda7-139">レプリケーションの状態を検証し、次のコマンドレットを使用して、エッジ サーバーに変更が適用されたと確認できます。</span><span class="sxs-lookup"><span data-stu-id="9cda7-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="9cda7-140">レプリケーションの更新を確認するには、Skype for Business Server 展開の内部サーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9cda7-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```powershell
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="9cda7-141">すべてのレプリカに対して UpToDate 値が TRUE を表示している場合に確認します。</span><span class="sxs-lookup"><span data-stu-id="9cda7-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="9cda7-142">変更が適用されたと確認するには、エッジ サーバーで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9cda7-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```powershell
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="9cda7-143">表示される情報が、前の手順でコミットされた変更と一致する場合は、ダブル チェックします。</span><span class="sxs-lookup"><span data-stu-id="9cda7-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cda7-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cda7-144">See also</span></span>

[<span data-ttu-id="9cda7-145">ホストされている Exchange UM での Skype for Business Server ユーザーのボイス メールの提供</span><span class="sxs-lookup"><span data-stu-id="9cda7-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[<span data-ttu-id="9cda7-146">Skype for Business Server でのホストされた Exchange ユニファイド メッセージングの統合</span><span class="sxs-lookup"><span data-stu-id="9cda7-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)