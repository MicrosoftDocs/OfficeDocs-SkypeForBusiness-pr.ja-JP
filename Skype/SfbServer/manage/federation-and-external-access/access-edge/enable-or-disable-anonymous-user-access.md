---
title: 匿名ユーザー アクセスの有効化または無効化
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
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
description: ''
ms.openlocfilehash: 40b365f25abccc05a5eb5156e1c7d79106a7537c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818408"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="a17ad-102">Skype for Business Server で匿名ユーザーのアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="a17ad-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="a17ad-103">匿名ユーザーは、組織の Active Directory ドメインサービスまたはサポートされているフェデレーションドメインでユーザーアカウントを持っていないユーザーですが、オンプレミスの会議にリモートで参加するよう招待することができます。</span><span class="sxs-lookup"><span data-stu-id="a17ad-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="a17ad-104">会議への匿名参加を許可することにより、匿名ユーザーを有効にします (つまり、会議または会議キーによって id が確認されたユーザーのみ)、会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="a17ad-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="a17ad-105">匿名での参加を許可するには、組織で匿名参加を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a17ad-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="a17ad-106">匿名ユーザーによるアクセスを一時的または完全に回避する必要がある場合は、組織で無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a17ad-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="a17ad-107">このセクションの手順を使用して、組織の匿名ユーザーアクセスを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="a17ad-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="a17ad-108">組織に対して匿名ユーザーアクセスを有効にすると、アクセスエッジサービスを実行しているサーバーでは、匿名ユーザーによるアクセスがサポートされることを指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="a17ad-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="a17ad-109">匿名ユーザーは、少なくとも1つの会議ポリシーを構成し、1つ以上のユーザーまたはユーザーグループに適用するまで、組織内のすべての会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="a17ad-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="a17ad-110">匿名ユーザーを会議に招待できるユーザーは、匿名ユーザーをサポートするように構成されている会議ポリシーが割り当てられているユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="a17ad-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="a17ad-111">匿名ユーザーの招待をサポートするように会議ポリシーを構成する方法について詳しくは、「[会議ポリシーを管理](../../conferencing/conferencing-policies.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a17ad-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="a17ad-112">組織の匿名ユーザーアクセスを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="a17ad-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="a17ad-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a17ad-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a17ad-114">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a17ad-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a17ad-115">左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**アクセスエッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a17ad-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="a17ad-116">[**アクセスエッジの構成**] ページで [**グローバル**] をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a17ad-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a17ad-117">[ **Access Edge 構成の編集**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a17ad-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="a17ad-118">組織の匿名ユーザーアクセスを有効にするには、[**匿名ユーザーとの通信を有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a17ad-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="a17ad-119">組織の匿名ユーザーアクセスを無効にするには、[**匿名ユーザーとの通信を有効**にする] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a17ad-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="a17ad-120">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a17ad-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a17ad-121">Windows PowerShell コマンドレットを使用して匿名ユーザーのアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="a17ad-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a17ad-122">Windows PowerShell と**CsAccessEdgeConfiguration**コマンドレットを使用して、匿名ユーザーのアクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a17ad-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="a17ad-123">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="a17ad-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="a17ad-124">匿名ユーザーのアクセスを有効にするには</span><span class="sxs-lookup"><span data-stu-id="a17ad-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="a17ad-125">匿名ユーザーのアクセスを有効にするには、 **AllowAnonymousUsers**プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="a17ad-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="a17ad-126">匿名ユーザーのアクセスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="a17ad-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="a17ad-127">匿名ユーザーのアクセスを無効にするには、 **AllowAnonymousUsers**プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="a17ad-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="a17ad-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="a17ad-128">See Also</span></span>

[<span data-ttu-id="a17ad-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="a17ad-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
