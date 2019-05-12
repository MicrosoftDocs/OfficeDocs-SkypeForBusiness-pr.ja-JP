---
title: ビジネス サーバーの Skype で SIP トランク構成設定の既存のコレクションを削除します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP トランクの構成設定は、仲介サーバーおよび公衆交換電話網 (PSTN) ゲートウェイ、IP 公開ブランチ交換機 (PBX)、またはサービス プロバイダーのセッション ボーダー コント ローラー (SBC) の間での機能との関係を定義します。 '
ms.openlocfilehash: 144d40f45853b0d0e3031f9d491fa1a3b1491ba8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33896317"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c9f79-103">ビジネス サーバーの Skype で SIP トランク構成設定の既存のコレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="c9f79-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="c9f79-104">SIP トランクの構成設定は、仲介サーバーおよび公衆交換電話網 (PSTN) ゲートウェイ、IP 公開ブランチ交換機 (PBX)、またはサービス プロバイダーのセッション ボーダー コント ローラー (SBC) の間での機能との関係を定義します。</span><span class="sxs-lookup"><span data-stu-id="c9f79-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="c9f79-105">たとえば、次の設定ができます。</span><span class="sxs-lookup"><span data-stu-id="c9f79-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="c9f79-106">トランクでメディア バイパスを有効化するか。</span><span class="sxs-lookup"><span data-stu-id="c9f79-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="c9f79-107">リアルタイム転送制御プロトコル (RTCP) パケットを送信する条件です。</span><span class="sxs-lookup"><span data-stu-id="c9f79-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="c9f79-108">かどうか各トランクには、セキュリティで保護されたリアルタイム プロトコル (SRTP) 暗号化が必要です。</span><span class="sxs-lookup"><span data-stu-id="c9f79-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="c9f79-109">ビジネス サーバーの Skype をインストールすると SIP トランク構成設定のグローバル コレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c9f79-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="c9f79-110">この設定のグローバル コレクションは削除できません。</span><span class="sxs-lookup"><span data-stu-id="c9f79-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="c9f79-111">ただし、グローバル コレクション内のプロパティを既定値に「リセット」に、Skype ビジネス ServerControl パネルの[削除 CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration)コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9f79-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="c9f79-112">たとえば、Enable3pccRefer プロパティを True に設定した場合、グローバル コレクションをリセットすると、Enable3pccRefer プロパティは既定値である False に戻ります。</span><span class="sxs-lookup"><span data-stu-id="c9f79-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="c9f79-p103">管理者がサイト スコープまたはサービス スコープでカスタム トランク構成設定を作成することもできます (個別の PSTN ゲートウェイの場合)。これらのカスタム設定は削除できます。カスタム設定を削除するときは、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c9f79-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="c9f79-p104">サービス スコープの設定を削除すると、その設定で管理されていた SIP トランクは、サイトに適用されている設定で管理されます (その設定が存在する場合)。サイトの設定が存在しない場合、これらのトランクは、トランク構成設定のグローバル コレクションによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="c9f79-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="c9f79-117">サイト スコープの設定を削除すると、その設定で管理されていたすべての SIP トランクが、トランク構成設定のグローバル コレクションによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="c9f79-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="c9f79-118">**ビジネス サーバーのコントロール パネルの Skype でのトランク構成の設定を削除するのには**</span><span class="sxs-lookup"><span data-stu-id="c9f79-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="c9f79-119">[ビジネス サーバーのコントロール パネルの Skype、**音声ルーティング**を**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9f79-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="c9f79-120">[**トランク構成**] タブで、削除、**編集**] をクリックし、[**削除**] をクリックして、SIP トランク構成設定のコレクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9f79-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="c9f79-121">同じ操作で複数のコレクションを削除するには、削除する最初のコレクションをクリックし、Ctrl キーを押しながら、削除するその他のコレクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9f79-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="c9f79-p106">コレクションの [**状態**] プロパティが、[**コミットされていません**] に変わります。変更をコミットし、コレクションを削除するには、[**コミット**] をクリックした後、[**すべてコミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9f79-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="c9f79-124">[**コミットされていない音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9f79-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="c9f79-125">**Skype ビジネス サーバーのコントロール パネル**] ダイアログ ボックスで [ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9f79-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="c9f79-126">変わったし、コレクションを削除しないことを決定するは、**コミット**をクリックし、**すべてのコミットされていない変更をキャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9f79-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="c9f79-127">**Skype**ビジネス サーバーのコントロール パネルのダイアログ ボックスが表示されたら、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9f79-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c9f79-128">Windows PowerShell コマンドレットを使用してトランク構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="c9f79-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="c9f79-129">トランク構成設定を削除するには、Windows PowerShell と**削除 CsTrunkConfiguration**コマンドレットを使用しています。</span><span class="sxs-lookup"><span data-stu-id="c9f79-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="c9f79-130">実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。</span><span class="sxs-lookup"><span data-stu-id="c9f79-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="c9f79-131">**指定した設定のコレクションを削除するには**</span><span class="sxs-lookup"><span data-stu-id="c9f79-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="c9f79-132">次のコマンドを実行すると、Redmond サイトに適用されていたトランク構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="c9f79-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="c9f79-133">**サイト スコープに適用されているすべてのコレクションを削除するには**</span><span class="sxs-lookup"><span data-stu-id="c9f79-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="c9f79-134">次のコマンドを実行すると、サービス スコープに適用されているすべてのトランク構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="c9f79-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="c9f79-135">**メディア バイパスが有効になっているすべてのコレクションを削除するには**</span><span class="sxs-lookup"><span data-stu-id="c9f79-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="c9f79-136">次のコマンドを実行すると、メディア バイパスが有効になっているすべてのトランク構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="c9f79-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="c9f79-137">詳細については、[削除 CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9f79-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>
