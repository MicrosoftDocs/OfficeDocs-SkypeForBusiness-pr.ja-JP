---
title: 匿名ユーザー アクセスの有効化または無効化
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
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
description: ''
ms.openlocfilehash: a65cd80311aaf1d13d5d9471ff285b94545176d1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119386"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="acb8f-102">Skype for Business Server で匿名ユーザー アクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="acb8f-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="acb8f-103">匿名ユーザーとは、組織の Active Directory ドメイン サービスまたはサポートされているフェデレーション ドメインにユーザー アカウントを持たないが、オンプレミスの会議にリモートから参加するために招待できるユーザーです。</span><span class="sxs-lookup"><span data-stu-id="acb8f-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="acb8f-104">会議への匿名参加を許可すると、匿名ユーザー (つまり、会議または会議キーを通じて ID が確認されるユーザー) が会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="acb8f-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="acb8f-105">匿名参加を許可するには、組織で有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="acb8f-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="acb8f-106">後で匿名ユーザーによるアクセスを一時的または完全に防止する場合は、組織で無効にできます。</span><span class="sxs-lookup"><span data-stu-id="acb8f-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="acb8f-107">組織の匿名ユーザー アクセスを有効または無効にするには、このセクションの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="acb8f-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="acb8f-108">組織で匿名ユーザー アクセスを有効にすることで、Access Edge サービスを実行しているサーバーが匿名ユーザーによるアクセスをサポートする必要があるだけになります。</span><span class="sxs-lookup"><span data-stu-id="acb8f-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="acb8f-109">匿名ユーザーは、少なくとも 1 つの会議ポリシーを構成し、1 つ以上のユーザーまたはユーザー グループに適用するまで、組織内の会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="acb8f-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="acb8f-110">匿名ユーザーを会議に招待できる唯一のユーザーは、匿名ユーザーをサポートするように構成された会議ポリシーが割り当てられているユーザーです。</span><span class="sxs-lookup"><span data-stu-id="acb8f-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="acb8f-111">匿名ユーザーの招待をサポートするための会議ポリシーの構成の詳細については、「会議ポリシーの管理 [」を参照してください](../../conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="acb8f-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="acb8f-112">組織の匿名ユーザー アクセスを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="acb8f-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="acb8f-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="acb8f-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="acb8f-114">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="acb8f-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="acb8f-115">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acb8f-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="acb8f-116">[**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="acb8f-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="acb8f-117">[**アクセス エッジ構成の編集**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="acb8f-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="acb8f-118">組織で匿名ユーザー アクセスを有効にするには、[匿名ユーザーとの通信を有効にする **] チェック ボックス** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="acb8f-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="acb8f-119">組織の匿名ユーザー アクセスを無効にするには、[匿名ユーザーとの通信を有効にする **] チェック ボックスを** オフにします。</span><span class="sxs-lookup"><span data-stu-id="acb8f-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="acb8f-120">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acb8f-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="acb8f-121">ユーザーのコマンドレットを使用して匿名ユーザー アクセスを有効またはWindows PowerShellする</span><span class="sxs-lookup"><span data-stu-id="acb8f-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="acb8f-122">匿名ユーザー アクセスを管理するには、Windows PowerShell **Set-CsAccessEdgeConfiguration コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="acb8f-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="acb8f-123">このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="acb8f-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="acb8f-124">匿名ユーザー アクセスを有効にするには</span><span class="sxs-lookup"><span data-stu-id="acb8f-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="acb8f-125">匿名ユーザー アクセスを有効にするには **、AllowAnonymousUsers** プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="acb8f-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="acb8f-126">匿名ユーザー アクセスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="acb8f-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="acb8f-127">匿名ユーザー アクセスを無効にするには **、AllowAnonymousUsers** プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="acb8f-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="acb8f-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="acb8f-128">See Also</span></span>

[<span data-ttu-id="acb8f-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="acb8f-129">Set-CsClientPolicy</span></span>](/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
