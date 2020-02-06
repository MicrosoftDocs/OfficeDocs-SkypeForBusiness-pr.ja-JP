---
title: フェデレーション パートナーの検出の有効化または無効化
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: エッジサーバーを展開して組織のフェデレーションを有効にした時点で、フェデレーションパートナードメインの自動検出をサポートするかどうかを指定する必要があります。
ms.openlocfilehash: a64e2056feacbee076fcaf9b0012a36f72c91523
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818398"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="b07e6-103">Skype for Business Server でフェデレーションパートナーの検出を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="b07e6-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="b07e6-104">エッジサーバーを展開して組織のフェデレーションを有効にした時点で、フェデレーションパートナードメインの自動検出をサポートするかどうかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b07e6-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="b07e6-105">この設定を変更するには、このトピックの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b07e6-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="b07e6-106">次の手順では、組織のフェデレーションを既に有効にしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b07e6-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="b07e6-107">フェデレーションを有効にする方法について詳しくは、「[リモートユーザーアクセスを有効または無効](enable-or-disable-remote-user-access.md)にする」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b07e6-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="b07e6-108">組織のフェデレーションドメインの自動検出を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="b07e6-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="b07e6-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b07e6-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b07e6-110">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b07e6-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="b07e6-111">左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**アクセスエッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b07e6-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="b07e6-112">[**アクセスエッジの構成**] ページで [**グローバル**] をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b07e6-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b07e6-113">[ **Access Edge 構成の編集**] の [**フェデレーションユーザーとの通信を有効**にする] で、パートナードメインの自動検出を有効または無効にするには、[**パートナードメインの検出を有効**にする] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="b07e6-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="b07e6-114">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b07e6-114">Click **Commit**.</span></span>

<span data-ttu-id="b07e6-115">フェデレーションされたユーザーが Skype for Business Server 展開のユーザーと共同作業できるようにするには、フェデレーションされたユーザーアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="b07e6-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="b07e6-116">詳細について[は、「フェデレーションとパブリック IM 接続を有効または無効](enable-or-disable-federation-and-public-im-connectivity.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b07e6-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="b07e6-117">特定のフェデレーションドメインのアクセス制御について詳しくは、「 [sip フェデレーションドメインを管理](../sip-domains/manage-sip-federated-domains-for-your-organization.md)する」と「 [sip フェデレーションプロバイダーを管理](../sip-providers/manage-sip-federated-providers-for-your-organization.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b07e6-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b07e6-118">Windows PowerShell コマンドレットを使用して、フェデレーションパートナーの検出を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="b07e6-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="b07e6-119">フェデレーションパートナーの検出は、Windows PowerShell と CsAccessEdgeConfiguration コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="b07e6-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="b07e6-120">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="b07e6-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="b07e6-121">フェデレーションパートナーの検出を有効にするには</span><span class="sxs-lookup"><span data-stu-id="b07e6-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="b07e6-122">フェデレーションパートナーの検出を有効にするには、 **Enablepartnerdiscovery**プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="b07e6-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="b07e6-123">このプロパティ値を変更するには、DNS SRV ルーティングを有効にする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b07e6-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="b07e6-124">フェデレーションパートナーの検出を無効にするには</span><span class="sxs-lookup"><span data-stu-id="b07e6-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="b07e6-125">フェデレーションパートナーの検出を無効にするには、 **Enablepartnerdiscovery**プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="b07e6-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

