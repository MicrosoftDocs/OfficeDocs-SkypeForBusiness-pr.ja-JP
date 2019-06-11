---
title: SIP トランク構成設定の既存コレクションの削除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b896d53760184d15b02afed14b8a9c0d660f96b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="ba4f2-102">Lync Server 2013 で既存の SIP トランク構成設定のコレクションを削除する</span><span class="sxs-lookup"><span data-stu-id="ba4f2-102">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba4f2-103">_**最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="ba4f2-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="ba4f2-104">SIP トランク構成設定は、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ、IP パブリックブランチ交換 (PBX)、またはサービスプロバイダのセッションボーダーコントローラー (SBC) 間の関係と機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="ba4f2-105">たとえば、次の設定ができます。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="ba4f2-106">トランクでメディア バイパスを有効化するか。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="ba4f2-107">リアルタイム伝送制御プロトコル (RTCP) パケットを送信する条件。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="ba4f2-108">各トランクで、セキュリティで保護されたリアルタイムプロトコル (SRTP) 暗号化が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="ba4f2-109">Microsoft Lync Server 2013 をインストールすると、SIP トランク構成設定のグローバルコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="ba4f2-110">この設定のグローバル コレクションは削除できません。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="ba4f2-111">ただし、Lync Server コントロールパネルまたは[set-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))コマンドレットを使用して、グローバルコレクションのプロパティを既定値に "リセット" することができます。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-111">However, you can use the Lync Server Control Panel or the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="ba4f2-112">たとえば、Enable3pccRefer プロパティを True に設定した場合、グローバル コレクションをリセットすると、Enable3pccRefer プロパティは既定値である False に戻ります。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="ba4f2-p103">管理者がサイト スコープまたはサービス スコープでカスタム トランク構成設定を作成することもできます (個別の PSTN ゲートウェイの場合)。これらのカスタム設定は削除できます。カスタム設定を削除するときは、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

  - <span data-ttu-id="ba4f2-p104">サービス スコープの設定を削除すると、その設定で管理されていた SIP トランクは、サイトに適用されている設定で管理されます (その設定が存在する場合)。サイトの設定が存在しない場合、これらのトランクは、トランク構成設定のグローバル コレクションによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>

  - <span data-ttu-id="ba4f2-117">サイト スコープの設定を削除すると、その設定で管理されていたすべての SIP トランクが、トランク構成設定のグローバル コレクションによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="ba4f2-118">Lync Server コントロールパネルでトランク構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="ba4f2-118">To remove trunk configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ba4f2-119">Lync Server コントロールパネルで、[**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-119">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="ba4f2-p105">[**トランク構成**] タブで、削除する SIP トランク構成設定のコレクションを選択し、[**編集**]、[**削除**] の順にクリックします。同じ操作で複数のコレクションを削除するには、削除する最初のコレクションをクリックし、Ctrl キーを押しながら、削除するその他のコレクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>

3.  <span data-ttu-id="ba4f2-p106">コレクションの [**状態**] プロパティが、[**コミットされていません**] に変わります。変更をコミットし、コレクションを削除するには、[**コミット**] をクリックした後、[**すべてコミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

4.  <span data-ttu-id="ba4f2-124">[**コミットされていない音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

5.  <span data-ttu-id="ba4f2-125">[ **Microsoft Lync Server 2013 コントロールパネル**] ダイアログボックスで、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-125">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

6.  <span data-ttu-id="ba4f2-126">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span><span class="sxs-lookup"><span data-stu-id="ba4f2-126">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="ba4f2-127">[ **Microsoft Lync Server 2013 コントロールパネル**] ダイアログボックスが表示されたら、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-127">When the **Microsoft Lync Server 2013 Control Panel** dialog box appears, click **OK**.</span></span>

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ba4f2-128">Windows PowerShell コマンドレットを使用したトランク構成設定の削除</span><span class="sxs-lookup"><span data-stu-id="ba4f2-128">Removing Trunk Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ba4f2-129">Windows PowerShell と**set-cstrunkconfiguration**コマンドレットを使用して、トランク構成設定を削除できます。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="ba4f2-130">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-130">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ba4f2-131">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="ba4f2-132">指定した設定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="ba4f2-132">To remove a specified collection of settings</span></span>

  - <span data-ttu-id="ba4f2-133">次のコマンドを実行すると、Redmond サイトに適用されていたトランク構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="ba4f2-134">サイト スコープに適用されているすべてのコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="ba4f2-134">To remove all the collections applied to the site scope</span></span>

  - <span data-ttu-id="ba4f2-135">次のコマンドを実行すると、サービス スコープに適用されているすべてのトランク構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="ba4f2-136">メディア バイパスが有効になっているすべてのコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="ba4f2-136">To remove all the collections where media bypass is enabled</span></span>

  - <span data-ttu-id="ba4f2-137">次のコマンドを実行すると、メディア バイパスが有効になっているすべてのトランク構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

<span data-ttu-id="ba4f2-138">詳細については、 [set-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba4f2-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

