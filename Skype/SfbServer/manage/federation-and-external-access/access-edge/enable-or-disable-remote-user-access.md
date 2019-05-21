---
title: リモート ユーザー アクセスの有効化または無効化
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: リモートユーザーに対してリモートユーザーアクセスを有効にすると、サポートされているリモートユーザーはインターネット経由で接続し、Skype for Business Server を使用して内部ユーザーと共同作業するために VPN を使用して接続する必要はありません。
ms.openlocfilehash: dde2bbb2d71d84bc9102683afc37208e3c4616bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280237"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="dc028-103">Skype for Business Server のリモートユーザーアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="dc028-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="dc028-104">リモートユーザーは組織内のユーザーで、組織内に Active Directory id が固定されています。</span><span class="sxs-lookup"><span data-stu-id="dc028-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="dc028-105">リモートユーザーは、組織のネットワークに接続されていないときに仮想プライベートネットワーク (VPN) を使用して、ネットワークの外部から Skype for Business Server にサインインすることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="dc028-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="dc028-106">リモートユーザーには、自宅や外出先で作業している従業員や、信頼できるベンダーなど、企業の資格情報が付与されている信頼できる社員が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dc028-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="dc028-107">リモートユーザーに対してリモートユーザーアクセスを有効にすると、サポートされているリモートユーザーはインターネット経由で接続し、Skype for Business Server を使用して内部ユーザーと共同作業するために VPN を使用して接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dc028-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="dc028-108">リモートユーザーアクセスをサポートするには、リモートユーザーアクセスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc028-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="dc028-109">リモートユーザーアクセスを有効にすると、組織全体で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dc028-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="dc028-110">後でリモートユーザーのアクセスを一時的または完全に禁止する必要がある場合は、組織に対して無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dc028-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="dc028-111">組織のリモートユーザーアクセスを有効または無効にするには、このセクションの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc028-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="dc028-112">リモートユーザーアクセスを有効にすることは、アクセスエッジサービスを実行しているサーバーがリモートユーザーとの通信をサポートしていることを示しますが、リモートユーザーは、を構成するまで、組織内のインスタントメッセージング (IM) または会議に参加することはできません。リモートユーザーアクセスの使用を管理するためのポリシーが少なくとも1つあります。</span><span class="sxs-lookup"><span data-stu-id="dc028-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="dc028-113">1つのポリシーレベルで適用される Skype for Business Server のポリシー設定は、別のポリシーレベルで適用されている設定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="dc028-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="dc028-114">Skype for Business Server のポリシーの優先順位: ユーザーポリシー (ほとんどの影響) でサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。</span><span class="sxs-lookup"><span data-stu-id="dc028-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="dc028-115">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="dc028-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="dc028-116">リモートユーザーアクセスを使用するためのポリシーの構成の詳細については、「 [Skype For Business Server でリモートユーザーアクセスを制御するためのポリシーを構成する](../external-access-policies/configure-policies-to-control-remote-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc028-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="dc028-117">組織のリモートユーザーアクセスを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="dc028-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="dc028-118">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dc028-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc028-119">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="dc028-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="dc028-120">左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc028-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="dc028-121">[**アクセスエッジの構成**] ページで [**グローバル**] をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc028-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="dc028-122">[ **Access Edge 構成の編集**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dc028-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="dc028-123">組織のリモートユーザーアクセスを有効にするには、[**リモートユーザーアクセスを有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="dc028-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="dc028-124">組織のリモートユーザーアクセスを無効にするには、[**リモートユーザーアクセスを有効に**する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="dc028-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="dc028-125">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc028-125">Click **Commit**.</span></span>

<span data-ttu-id="dc028-126">リモートユーザーが Skype for Business Server を実行しているサーバーにサインインできるようにするには、リモートユーザーのアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc028-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="dc028-127">詳細については、「 [Skype For Business Server でリモートユーザーアクセスを制御するためのポリシーを構成する](../external-access-policies/configure-policies-to-control-remote-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc028-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dc028-128">Windows PowerShell コマンドレットを使用したリモートユーザーアクセスの有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="dc028-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="dc028-129">リモートユーザーアクセスを管理するには、Windows PowerShell と CsAccessEdgeConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc028-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="dc028-130">このコマンドレットは、Skype for Business Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="dc028-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="dc028-131">リモートユーザーアクセスを有効にするには</span><span class="sxs-lookup"><span data-stu-id="dc028-131">To enable remote user access</span></span>

  - <span data-ttu-id="dc028-132">リモートユーザーアクセスを有効にするには、 **Allowoutsideusers**プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="dc028-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="dc028-133">リモートユーザーアクセスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="dc028-133">To disable remote user access</span></span>

  - <span data-ttu-id="dc028-134">リモートユーザーアクセスを無効にするには、 **Allowoutsideusers**プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="dc028-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


