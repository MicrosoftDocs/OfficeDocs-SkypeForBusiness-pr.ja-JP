---
title: リモート ユーザー アクセスの有効化または無効化
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
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
description: リモート ユーザーのリモート ユーザー アクセスを有効にした場合、サポートされているリモート ユーザーはインターネット経由で接続し、Skype for Business Server を使用して内部ユーザーと共同作業するために VPN を使用して接続する必要はありません。
ms.openlocfilehash: 9e5ba5828e129c6fed5dd892b1a7bb8e6bd64707
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817397"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="92769-103">Skype for Business Server でリモート ユーザー アクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="92769-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="92769-104">リモート ユーザーは、組織内の永続的な Active Directory ID を持つ、組織内のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="92769-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="92769-105">リモート ユーザーは、多くの場合、組織のネットワークに接続されていない場合に仮想プライベート ネットワーク (VPN) を使用して、ネットワークの外部から Skype for Business Server にサインインします。</span><span class="sxs-lookup"><span data-stu-id="92769-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="92769-106">リモート ユーザーには自宅や外出先で作業する従業員のほか、エンタープライズ資格情報を付与された信頼できるベンダーなどのリモート作業者が含まれます。</span><span class="sxs-lookup"><span data-stu-id="92769-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="92769-107">リモート ユーザーのリモート ユーザー アクセスを有効にした場合、サポートされているリモート ユーザーはインターネット経由で接続し、Skype for Business Server を使用して内部ユーザーと共同作業するために VPN を使用して接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="92769-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="92769-p102">リモート ユーザー アクセスをサポートするには、リモート ユーザー アクセスを有効にする必要があります。有効にする場合は、組織全体に対して有効にします。後でリモート ユーザー アクセスを一時的または永久に禁止する場合は、組織に対するリモート ユーザー アクセスを無効にできます。組織に対するリモート ユーザー アクセスを有効または無効にするには、このセクションの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="92769-p102">To support remote user access, you must enable remote user access. When you enable remote user access, you enable it for your entire organization. If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization. Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="92769-112">リモート ユーザー アクセスを有効にした時点では、アクセス エッジ サービスを実行するサーバーがリモート ユーザーとの通信をサポートするという指定が行われるだけです。</span><span class="sxs-lookup"><span data-stu-id="92769-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="92769-113">1 つのポリシー レベルで適用される Skype for Business Server ポリシー設定は、別のポリシー レベルで適用される設定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="92769-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="92769-114">Skype for Business Server ポリシーの優先順位: ユーザー ポリシー (最も高い) はサイト ポリシーをオーバーライドし、サイト ポリシーはグローバル ポリシーをオーバーライド (最も低い) します。</span><span class="sxs-lookup"><span data-stu-id="92769-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="92769-115">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="92769-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="92769-116">リモート ユーザー アクセスを使用するためのポリシーの構成の詳細については [、「Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92769-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="92769-117">組織に対するリモート ユーザー アクセスを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="92769-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="92769-118">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="92769-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="92769-119">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="92769-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="92769-120">左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92769-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="92769-121">[**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="92769-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="92769-122">[**アクセス エッジ構成の編集**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="92769-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="92769-123">組織に対してリモート ユーザー アクセスを有効にするには、[**リモート ユーザー アクセスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="92769-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="92769-124">組織に対してリモート ユーザー アクセスを無効にするには、[**リモート ユーザー アクセスを有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="92769-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="92769-125">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92769-125">Click **Commit**.</span></span>

<span data-ttu-id="92769-126">リモート ユーザーが Skype for Business Server を実行しているサーバーにサインインするには、リモート ユーザー アクセスをサポートするために少なくとも 1 つの外部アクセス ポリシーも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92769-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="92769-127">詳細については、「Skype for Business Server でリモート ユーザー アクセスを [制御するポリシーを構成する」を参照してください](../external-access-policies/configure-policies-to-control-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="92769-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="92769-128">コマンドレットを使用してリモート ユーザー アクセスを有効Windows PowerShell無効にする</span><span class="sxs-lookup"><span data-stu-id="92769-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="92769-129">リモート ユーザー アクセスは、リモート ユーザー アクセスと Windows PowerShellコマンドレットをSet-CsAccessEdgeConfigurationできます。</span><span class="sxs-lookup"><span data-stu-id="92769-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="92769-130">このコマンドレットは、Skype for Business Server 2013 管理シェルまたは Skype for Business Server 2013 のリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="92769-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="92769-131">リモート ユーザー アクセスを有効にするには</span><span class="sxs-lookup"><span data-stu-id="92769-131">To enable remote user access</span></span>

  - <span data-ttu-id="92769-132">リモート ユーザー アクセスを有効にするには、**AllowOutsideUsers** プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="92769-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="92769-133">リモート ユーザー アクセスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="92769-133">To disable remote user access</span></span>

  - <span data-ttu-id="92769-134">リモート ユーザー アクセスを無効にするには、**AllowOutsideUsers** プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="92769-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


