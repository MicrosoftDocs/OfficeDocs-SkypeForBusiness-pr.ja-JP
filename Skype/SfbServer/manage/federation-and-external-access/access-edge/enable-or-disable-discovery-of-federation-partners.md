---
title: フェデレーション パートナーの検出の有効化または無効化
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: エッジ サーバーを展開して組織のフェデレーションを有効にした際に、フェデレーション パートナー ドメインの自動検出をサポートするかどうかを指定しています。
ms.openlocfilehash: e1f076b725dff149f024a3fd59f9f7d52da4e6a8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817427"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="8a110-103">Skype for Business Server でフェデレーション パートナーの検出を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="8a110-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="8a110-p101">エッジ サーバーを展開して組織のフェデレーションを有効にした際に、フェデレーション パートナー ドメインの自動検出をサポートするかどうかを指定しています。 このトピックの手順を使用して、この構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="8a110-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains. Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="8a110-106">次の手順では、既に組織に対してフェデレーションを有効にしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="8a110-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="8a110-107">フェデレーションを有効にする方法の詳細については、「リモート ユーザー アクセスを [有効または無効にする」を参照してください](enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="8a110-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="8a110-108">組織に対してフェデレーション ドメインの自動検出を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="8a110-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="8a110-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8a110-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8a110-110">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8a110-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="8a110-111">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a110-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="8a110-112">[**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a110-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="8a110-113">[**アクセス エッジ構成の編集**] で、[**フェデレーション ユーザーとの通信を有効にする**] の [**パートナー ドメインの検出を有効にする**] チェック ボックスをオンまたはオフにして、パートナー ドメインの自動検出を有効また無効にします。</span><span class="sxs-lookup"><span data-stu-id="8a110-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="8a110-114">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a110-114">Click **Commit**.</span></span>

<span data-ttu-id="8a110-115">フェデレーション ユーザーが Skype for Business Server 展開のユーザーと共同作業を行うのを有効にするには、フェデレーション ユーザー アクセスをサポートするために少なくとも 1 つの外部アクセス ポリシーも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a110-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="8a110-116">詳細については、「フェデレーションと [パブリック IM 接続を有効または無効にする」を参照してください](enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="8a110-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="8a110-117">特定のフェデレーション ドメインのアクセス制御の詳細については、「SIP フェデレーション ドメインの管理」および [「SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) フェデレーション プロバイダー [の管理」を参照してください](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="8a110-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8a110-118">フェデレーション コマンドレットを使用してフェデレーション パートナーの検出Windows PowerShellまたは無効にする</span><span class="sxs-lookup"><span data-stu-id="8a110-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="8a110-119">フェデレーション パートナーの検出は、フェデレーション コマンドレットと Windows PowerShell使用してSet-CsAccessEdgeConfigurationできます。</span><span class="sxs-lookup"><span data-stu-id="8a110-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="8a110-120">このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8a110-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="8a110-121">フェデレーション パートナーの検出を有効にするには</span><span class="sxs-lookup"><span data-stu-id="8a110-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="8a110-122">フェデレーション パートナーの検出を有効にするには **、EnablePartnerDiscovery** プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="8a110-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="8a110-123">このプロパティ値を変更するには、DNS SRV ルーティングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a110-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="8a110-124">フェデレーション パートナーの検出を無効にするには</span><span class="sxs-lookup"><span data-stu-id="8a110-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="8a110-125">フェデレーション パートナーの検出を無効にするには **、EnablePartnerDiscovery** プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="8a110-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

