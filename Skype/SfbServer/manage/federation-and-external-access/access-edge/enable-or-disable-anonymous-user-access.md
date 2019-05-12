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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 6bc424dc0b26f794d45c5a601b468bbb78c92ef6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919452"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="98a2f-102">有効にするか、ビジネスのサーバーの Skype の匿名ユーザー アクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="98a2f-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="98a2f-103">匿名ユーザーは、ユーザーが組織の Active Directory ドメイン サービスまたはサポートされているフェデレーション ドメインのユーザー アカウントはありませんが、オンプレミス会議にリモートで参加するように招待することができます。</span><span class="sxs-lookup"><span data-stu-id="98a2f-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="98a2f-104">匿名ユーザー (つまり、ユーザー id を確認して会議出席依頼や会議のキーのみを使用) を有効にした匿名ミーティングへの参加を許可することで会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="98a2f-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="98a2f-105">匿名参加を許可するには、組織では有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="98a2f-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="98a2f-106">後で、一時的または恒久的には、匿名ユーザーによるアクセスを防ぐためにする場合は、組織に無効にできます。</span><span class="sxs-lookup"><span data-stu-id="98a2f-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="98a2f-107">このセクションでを有効にするか、組織の匿名ユーザー アクセスを無効にする手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="98a2f-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="98a2f-108">組織の匿名ユーザー アクセスを有効にすることによってのみを指定するアクセス エッジ サービスを実行しているサーバーが匿名ユーザーによるアクセスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="98a2f-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="98a2f-109">匿名ユーザーが表示されるまでも、少なくとも 1 つの会議ポリシーを構成する 1 つまたは複数のユーザーまたはユーザー グループに適用する、組織内のすべての会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="98a2f-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="98a2f-110">匿名ユーザーをサポートするために構成されている会議ポリシーを割り当てられているこれらのユーザーは会議への匿名ユーザーを招待することがあるユーザーだけです。</span><span class="sxs-lookup"><span data-stu-id="98a2f-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="98a2f-111">匿名ユーザーの招待をサポートするための会議ポリシーを構成する方法の詳細は、[会議ポリシーの管理](../../conferencing/conferencing-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98a2f-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="98a2f-112">有効にするか、組織の匿名ユーザー アクセスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="98a2f-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="98a2f-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="98a2f-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="98a2f-114">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="98a2f-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="98a2f-115">左側のナビゲーション ・ バーでは、**外部ユーザー アクセス**をクリックし、**アクセス エッジの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98a2f-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="98a2f-116">[**アクセス エッジ構成**] ページで、[**グローバル**] をクリック**を編集**するには、、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98a2f-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="98a2f-117">**アクセス エッジ構成の編集**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="98a2f-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="98a2f-118">組織の匿名ユーザー アクセスを有効にするには、**匿名ユーザーとの通信を有効にする**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="98a2f-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="98a2f-119">組織の匿名ユーザー アクセスを無効にするには、**匿名ユーザーとの通信を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="98a2f-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="98a2f-120">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98a2f-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="98a2f-121">有効にするか、Windows PowerShell コマンドレットを使用して匿名ユーザーのアクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="98a2f-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="98a2f-122">Windows PowerShell と**セット CsAccessEdgeConfiguration**コマンドレットを使用して、匿名ユーザー アクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="98a2f-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="98a2f-123">実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。</span><span class="sxs-lookup"><span data-stu-id="98a2f-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="98a2f-124">匿名ユーザー アクセスを有効にするには</span><span class="sxs-lookup"><span data-stu-id="98a2f-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="98a2f-125">匿名ユーザー アクセスを有効にするには、 **AllowAnonymousUsers**プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="98a2f-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="98a2f-126">匿名ユーザー アクセスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="98a2f-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="98a2f-127">匿名ユーザー アクセスを無効にするには、 **AllowAnonymousUsers**プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="98a2f-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="98a2f-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="98a2f-128">See Also</span></span>

[<span data-ttu-id="98a2f-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="98a2f-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
