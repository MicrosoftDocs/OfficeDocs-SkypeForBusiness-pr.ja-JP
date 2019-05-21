---
title: Skype for Business Server でアーカイブ構成を作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: '概要: Skype for Business Server のアーカイブ構成の作成方法について説明します。'
ms.openlocfilehash: 58d817cea4c1caceff37bd132cd4f5a61445cdb0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286219"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="08429-103">Skype for Business Server でアーカイブ構成を作成する</span><span class="sxs-lookup"><span data-stu-id="08429-103">Create an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="08429-104">**概要:** Skype for Business Server のアーカイブ構成の作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="08429-104">**Summary:** Learn how to create an archiving configuration for Skype for Business Server.</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="08429-105">コントロール パネルを使用してアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="08429-105">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="08429-106">特定のサイトまたはプールのアーカイブ オプションを構成するには</span><span class="sxs-lookup"><span data-stu-id="08429-106">To configure archiving options for a specific site or pool:</span></span> 
  
1. <span data-ttu-id="08429-107">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="08429-107">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="08429-108">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="08429-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="08429-109">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08429-109">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="08429-110">[**アーカイブ構成**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="08429-110">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="08429-111">サイトのアーカイブ構成を作成するには、[**サイト構成**] をクリックし、[**サイトの選択**] で、アーカイブ用に構成するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="08429-111">To create a site archiving configuration, click **Site Configuration**, and then in **Select a site**, select the site to be configured for archiving.</span></span>
    
   - <span data-ttu-id="08429-112">プールのアーカイブ構成を作成するには、[**プール構成**] をクリックし、[**プールの選択**] で、アーカイブ用に構成するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="08429-112">To create a pool archiving configuration, click **Pool Configuration**, and then in **Select a pool**, select the pool to be configured for archiving.</span></span>
    
5. <span data-ttu-id="08429-113">[**新しいアーカイブ設定**] の [**アーカイブ設定**] ドロップダウン リスト ボックスで、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="08429-113">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="08429-114">インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、[**IM セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08429-114">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="08429-115">IM セッションと Web 会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08429-115">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="08429-116">この構成のアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08429-116">To disable archiving for this configuration, click **Disable archiving**.</span></span>
    
6. <span data-ttu-id="08429-117">[**新しいアーカイブ設定**] で、次の操作も実行します。</span><span class="sxs-lookup"><span data-stu-id="08429-117">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="08429-118">アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="08429-118">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="08429-119">アーカイブデータの保存に Microsoft Exchange Server を使用するには、[ **Microsoft exchange 統合**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="08429-119">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="08429-120">データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="08429-120">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
     - <span data-ttu-id="08429-121">一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックし、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="08429-121">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="08429-122">エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08429-122">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="08429-123">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08429-123">Click **Commit**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="08429-124">Windows PowerShell を使用してアーカイブ オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="08429-124">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="08429-125">**New-CsArchivingConfiguration** コマンドレットを使用して、特定のサイトまたはプールのアーカイブ オプションを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="08429-125">You can also configure archiving options for a specific site or pool by using the **New-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="08429-126">次のコマンドを実行すると、レドモンドのサイト用に新しいアーカイブ構成設定のコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="08429-126">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
  
```
New-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="08429-127">このコマンドでは (必須の Identity パラメーター以外の) パラメーターが指定されていないため、新しい構成設定のコレクションでは、すべてのプロパティに既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="08429-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> 
  
<span data-ttu-id="08429-p101">異なるプロパティ値を使用する設定を作成するには、該当するパラメーターとパラメーター値を追加します。次の例では、既定ではインスタント メッセージング セッションのアーカイブのみを許可するアーカイブ構成設定のコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="08429-p101">To create settings that use different property values, simply include the appropriate parameter and parameter value. The following example creates a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions only:</span></span>
  
```
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

<span data-ttu-id="08429-p102">複数のパラメーターを含めることにより複数のプロパティ値を変更できます。たとえば、次のコマンドを実行すると、インスタント メッセージング セッションをアーカイブし、アーカイブ サービスのインスタント メッセージング サービスをブロックして使用不可にする新しい設定が構成されます。</span><span class="sxs-lookup"><span data-stu-id="08429-p102">Multiple property values can be modified by including multiple parameters. For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
  
```
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

<span data-ttu-id="08429-132">詳細については、 [CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="08429-132">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
