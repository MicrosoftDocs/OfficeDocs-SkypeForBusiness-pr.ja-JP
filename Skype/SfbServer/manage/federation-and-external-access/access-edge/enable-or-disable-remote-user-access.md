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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: リモート ユーザーのリモート ユーザー アクセスを有効にした場合サポートされているリモート ユーザーは、インターネット経由で接続し、Skype を使用してビジネスのサーバーの内部のユーザーと共同作業するために VPN を使用して接続する必要はありません。
ms.openlocfilehash: 7586d6af408c4f6dd6290ccf1fc9f19dbc23a87e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919475"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="48cb7-103">有効にするか、ビジネスのサーバーの Skype でのリモート ユーザー アクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="48cb7-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="48cb7-104">リモート ユーザーは、組織内の永続的な Active Directory id を持つ、組織内のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="48cb7-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="48cb7-105">リモート ユーザー多くの場合にサインイン Skype ビジネス サーバーからのネットワークの外部組織のネットワークに接続されていない場合、仮想プライベート ネットワーク (VPN) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="48cb7-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="48cb7-106">リモート ユーザーには、在宅勤務の従業員が含まれます。 または、道と他のリモート作業者を信頼できるベンダーなどを与えられているエンタープライズ資格情報です。</span><span class="sxs-lookup"><span data-stu-id="48cb7-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="48cb7-107">リモート ユーザーのリモート ユーザー アクセスを有効にした場合サポートされているリモート ユーザーは、インターネット経由で接続し、Skype を使用してビジネスのサーバーの内部のユーザーと共同作業するために VPN を使用して接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="48cb7-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="48cb7-108">リモート ユーザー アクセスをサポートするには、リモート ユーザー アクセスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="48cb7-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="48cb7-109">リモート ユーザー アクセスを有効にすると、組織全体で有効です。</span><span class="sxs-lookup"><span data-stu-id="48cb7-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="48cb7-110">後で一時的または恒久的には、リモート ユーザー アクセスを防止する場合は、組織で無効にできます。</span><span class="sxs-lookup"><span data-stu-id="48cb7-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="48cb7-111">このセクションでを有効にするか、組織のリモート ユーザー アクセスを無効にする手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="48cb7-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="48cb7-112">アクセス エッジ サービスを実行しているサーバー、リモート ユーザーとの通信をサポートしていますでも構成するまで、リモート ユーザーがインスタント メッセージング (IM) または組織内の会議に参加できないリモート ユーザー アクセスを有効にすることのみを指定します。リモート ユーザー アクセスの使用を管理するために少なくとも 1 つのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="48cb7-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="48cb7-113">Skype ビジネスのサーバーのポリシー設定が 1 つのポリシー レベルで適用されるは、別のポリシー レベルで適用される設定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="48cb7-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="48cb7-114">ビジネス サーバー ポリシーの優先順位の Skype が: ユーザー ポリシー (ほとんどの影響) がサイト ポリシーを上書きし、[サイト ポリシーはグローバル ポリシー (最低限の影響) をよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="48cb7-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="48cb7-115">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="48cb7-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="48cb7-116">リモート ユーザー アクセスを使用するためのポリシーの構成に関する詳細については、 [Skype のビジネス サーバーでリモート ユーザー アクセスを制御するポリシーを構成する](../external-access-policies/configure-policies-to-control-remote-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48cb7-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="48cb7-117">有効にするか、組織のリモート ユーザー アクセスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="48cb7-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="48cb7-118">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="48cb7-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="48cb7-119">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="48cb7-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="48cb7-120">左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48cb7-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="48cb7-121">[**アクセス エッジ構成**] ページで、[**グローバル**] をクリック**を編集**するには、、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48cb7-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="48cb7-122">**アクセス エッジ構成の編集**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="48cb7-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="48cb7-123">組織のリモート ユーザー アクセスを有効にするには、**リモート ユーザー アクセスを有効にする**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="48cb7-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="48cb7-124">組織のリモート ユーザー アクセスを無効にするには、**リモート ユーザー アクセスを有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="48cb7-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="48cb7-125">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48cb7-125">Click **Commit**.</span></span>

<span data-ttu-id="48cb7-126">Skype をビジネスのサーバーを実行しているサーバーにサインインするのにはリモート ユーザーを有効にするには、リモート ユーザー アクセスをサポートするために少なくとも 1 つの外部アクセス ポリシーを構成することもあります。</span><span class="sxs-lookup"><span data-stu-id="48cb7-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="48cb7-127">詳細については、 [Skype のビジネス サーバーでリモート ユーザー アクセスを制御するポリシーを構成する](../external-access-policies/configure-policies-to-control-remote-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48cb7-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="48cb7-128">有効にするか、Windows PowerShell コマンドレットを使用して、リモート ユーザー アクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="48cb7-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="48cb7-129">Windows PowerShell とセット CsAccessEdgeConfiguration コマンドレットを使用して、リモート ユーザー アクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="48cb7-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="48cb7-130">ビジネス Server 2013 の管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="48cb7-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="48cb7-131">リモート ユーザー アクセスを有効にするには</span><span class="sxs-lookup"><span data-stu-id="48cb7-131">To enable remote user access</span></span>

  - <span data-ttu-id="48cb7-132">リモート ユーザー アクセスを有効にするには、 **AllowOutsideUsers**プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="48cb7-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="48cb7-133">リモート ユーザー アクセスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="48cb7-133">To disable remote user access</span></span>

  - <span data-ttu-id="48cb7-134">リモート ユーザー アクセスを無効にするには、 **AllowOutsideUsers**プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="48cb7-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


