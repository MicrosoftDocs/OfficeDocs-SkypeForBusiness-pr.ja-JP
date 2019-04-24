---
title: フェデレーション パートナーの検出の有効化または無効化
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 時に、エッジ サーバーの展開し、フェデレーションを有効になっている、組織の必要がある指定したフェデレーション パートナー ドメインの自動検出をサポートするかどうか。
ms.openlocfilehash: de61d8180a8f4e8f8be13abaab3d8911d2c6e22c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199942"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="a5daa-103">有効にするか、ビジネスのサーバーの Skype でのフェデレーション パートナーの検出を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a5daa-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="a5daa-104">時に、エッジ サーバーの展開し、フェデレーションを有効になっている、組織の必要がある指定したフェデレーション パートナー ドメインの自動検出をサポートするかどうか。</span><span class="sxs-lookup"><span data-stu-id="a5daa-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="a5daa-105">その構成を変更するのにはこのトピックの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5daa-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="a5daa-106">次の手順では、組織のフェデレーションが既に有効にことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a5daa-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="a5daa-107">フェデレーションを有効にする方法の詳細[を有効にするかリモート ユーザー アクセスを無効にする](enable-or-disable-remote-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5daa-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="a5daa-108">有効にするか、組織のフェデレーション ドメインの自動検出を無効にするには</span><span class="sxs-lookup"><span data-stu-id="a5daa-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="a5daa-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a5daa-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a5daa-110">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5daa-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="a5daa-111">左側のナビゲーション ・ バーで [**外部ユーザー アクセス**] をクリックして、[**アクセス エッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5daa-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="a5daa-112">[**アクセス エッジ構成**] ページで、[**グローバル**] をクリック**を編集**するには、、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5daa-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a5daa-113">**アクセス エッジ構成の編集**、**フェデレーション ユーザーとの通信を有効にする**には、選択またはを有効にするか、パートナー ドメインの自動検出を無効にするには、**パートナー ドメインの検出を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a5daa-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="a5daa-114">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5daa-114">Click **Commit**.</span></span>

<span data-ttu-id="a5daa-115">フェデレーション ユーザーにビジネスのサーバーの展開に、Skype のユーザーと共同作業を有効にするには、必要がありますもしているフェデレーション ユーザー アクセスをサポートするために少なくとも 1 つの外部アクセス ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="a5daa-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="a5daa-116">詳細については、[有効にするかフェデレーションとパブリック IM 接続を無効にする](enable-or-disable-federation-and-public-im-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5daa-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="a5daa-117">特定のフェデレーション ドメインのアクセスを制御する方法の詳細は、[ドメインをフェデレーションする SIP を管理](../sip-domains/manage-sip-federated-domains-for-your-organization.md)し、[プロバイダーをフェデレーションする SIP の管理](../sip-providers/manage-sip-federated-providers-for-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5daa-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a5daa-118">有効にするか、Windows PowerShell コマンドレットを使用してフェデレーション パートナーの検出を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a5daa-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a5daa-119">フェデレーション パートナーの検出は、Windows PowerShell とセット CsAccessEdgeConfiguration コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="a5daa-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="a5daa-120">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5daa-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="a5daa-121">フェデレーション パートナーの検出を有効にするには</span><span class="sxs-lookup"><span data-stu-id="a5daa-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="a5daa-122">フェデレーション パートナーの検出を有効にするには、 **EnablePartnerDiscovery**プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="a5daa-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="a5daa-123">DNS SRV がこのプロパティの値を変更するのにはルーティングを有効にする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a5daa-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="a5daa-124">フェデレーション パートナーの検出を無効にするには</span><span class="sxs-lookup"><span data-stu-id="a5daa-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="a5daa-125">フェデレーション パートナーの検出を無効にするには、 **EnablePartnerDiscovery**プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="a5daa-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

