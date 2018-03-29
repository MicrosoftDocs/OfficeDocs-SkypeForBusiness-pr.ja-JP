---
title: Skype for Business Server 2015 での SIP トランク構成設定の既存コレクションの削除
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: '概要: ビジネス サーバーのコントロール パネルの Skype を使用してトランク構成設定のコレクションを削除する方法を説明します。'
ms.openlocfilehash: 4193922cbf3c318ada0e896a6082c51f33615330
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="e99de-103">Skype for Business Server 2015 での SIP トランク構成設定の既存コレクションの削除</span><span class="sxs-lookup"><span data-stu-id="e99de-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e99de-104">**の概要:**ビジネス サーバーのコントロール パネルの Skype を使用してトランク構成設定のコレクションを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e99de-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="e99de-p101">SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch eXchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係と機能を定義します。たとえば、次の設定ができます。</span><span class="sxs-lookup"><span data-stu-id="e99de-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="e99de-107">トランクでメディア バイパスを有効化するか。</span><span class="sxs-lookup"><span data-stu-id="e99de-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="e99de-108">Realtime Transport Control Protocol (RTCP) パケットが送信される条件。</span><span class="sxs-lookup"><span data-stu-id="e99de-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="e99de-109">各トランクで Secure Realtime Transport Protocol (SRTP) 暗号化を要求するか。</span><span class="sxs-lookup"><span data-stu-id="e99de-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="e99de-110">ビジネス サーバーの Skype をインストールすると SIP トランク構成設定のグローバル コレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e99de-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="e99de-111">この設定のグローバル コレクションは削除できません。</span><span class="sxs-lookup"><span data-stu-id="e99de-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="e99de-112">ただし、グローバル コレクション内のプロパティを既定値に「リセット」するには、Skype ビジネス サーバーのコントロール パネルの[削除 CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps)コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e99de-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="e99de-113">たとえば、Enable3pccRefer プロパティを True に設定した場合、グローバル コレクションをリセットすると、Enable3pccRefer プロパティは既定値である False に戻ります。</span><span class="sxs-lookup"><span data-stu-id="e99de-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="e99de-p103">管理者がサイト スコープまたはサービス スコープでカスタム トランク構成設定を作成することもできます (個別の PSTN ゲートウェイの場合)。これらのカスタム設定は削除できます。カスタム設定を削除するときは、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e99de-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="e99de-p104">サービス スコープの設定を削除すると、その設定で管理されていた SIP トランクは、サイトに適用されている設定で管理されます (その設定が存在する場合)。サイトの設定が存在しない場合、これらのトランクは、トランク構成設定のグローバル コレクションによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="e99de-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="e99de-118">サイト スコープの設定を削除すると、その設定で管理されていたすべての SIP トランクが、トランク構成設定のグローバル コレクションによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="e99de-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="e99de-119">ビジネス サーバーのコントロール パネルの Skype でのトランク構成の設定を削除するのには</span><span class="sxs-lookup"><span data-stu-id="e99de-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e99de-120">ビジネス サーバーのコントロール パネルの Skype は、[**音声ルーティング**] をクリックしてで**トランクの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e99de-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="e99de-p105">[**トランク構成**] タブで、削除する SIP トランク構成設定のコレクションを選択し、[**編集**]、[**削除**] の順にクリックします。同じ操作で複数のコレクションを削除するには、削除する最初のコレクションをクリックし、Ctrl キーを押しながら、削除するその他のコレクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e99de-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="e99de-p106">コレクションの [**状態**] プロパティが、[**コミットされていません**] に変わります。変更をコミットし、コレクションを削除するには、[**コミット**] をクリックした後、[**すべてコミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e99de-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="e99de-125">[**コミットされていない音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e99de-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="e99de-126">**Skype**ビジネス サーバーのコントロール パネルのダイアログ ボックスで [ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e99de-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="e99de-127">後でコレクションを削除しないことにした場合は、[**コミット**]、[**コミットされていないすべての変更を取り消し**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e99de-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="e99de-128">**Skype**ビジネス サーバーのコントロール パネルのダイアログ ボックスが表示されたら、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e99de-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="e99de-129">Skype ビジネス サーバーの管理シェル コマンドレットを使用してトランク構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="e99de-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="e99de-130">Skype をビジネス サーバー管理シェルを**削除 CsTrunkConfiguration**コマンドレットを使用してトランク構成設定を削除できます。</span><span class="sxs-lookup"><span data-stu-id="e99de-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="e99de-131">実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Skype のリモート セッションからサーバー管理シェルのビジネス。</span><span class="sxs-lookup"><span data-stu-id="e99de-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="e99de-132">指定した設定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="e99de-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="e99de-133">次のコマンドを実行すると、Redmond サイトに適用されていたトランク構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="e99de-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="e99de-134">サイト スコープに適用されているすべてのコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="e99de-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="e99de-135">次のコマンドを実行すると、サービス スコープに適用されているすべてのトランク構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="e99de-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="e99de-136">メディア バイパスが有効になっているすべてのコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="e99de-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="e99de-137">次のコマンドを実行すると、メディア バイパスが有効になっているすべてのトランク構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="e99de-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="e99de-138">詳細については、[削除 CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e99de-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

