---
title: Skype for Business Server でアーカイブを有効または無効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: '概要: Skype for Business Server でアーカイブを有効または無効にする方法について説明します。'
ms.openlocfilehash: 0e4ef4dde27ffa5856f2b73b69ffbadc24399c59
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286145"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="54f4d-103">Skype for Business Server でアーカイブを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="54f4d-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="54f4d-104">**概要:** Skype for Business Server でアーカイブを有効または無効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="54f4d-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="54f4d-105">コントロール パネルを使用してアーカイブを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="54f4d-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="54f4d-106">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="54f4d-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="54f4d-107">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="54f4d-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="54f4d-108">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54f4d-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="54f4d-109">アーカイブ構成の一覧から適切なグローバル、サイト、またはプール構成を選択し、[**編集**] をクリックし、[**詳細の表示**] をクリックしてから次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="54f4d-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="54f4d-110">インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、[**IM セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54f4d-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="54f4d-111">IM セッションと会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54f4d-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="54f4d-112">構成のアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54f4d-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="54f4d-113">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54f4d-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="54f4d-114">Windows PowerShell を使用してアーカイブを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="54f4d-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="54f4d-115">アーカイブは、**Set-CsArchivingConfiguration** コマンドレットを使用して有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="54f4d-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="54f4d-116">たとえば、次のコマンドは、IM セッションのみがアーカイブされるようにすべてのアーカイブ構成設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="54f4d-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="54f4d-117">このコマンドは、**Get-CsArchivingConfiguration** コマンドレットをパラメーターなしで呼び出して、組織で現在使用されているすべてのアーカイブ構成設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="54f4d-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="54f4d-118">次に、このコレクションは **Where-Object** コマンドレットにパイプ処理され、EnableArchiving プロパティが "ImAndWebConf" と等しい (-eq) 設定のみが選択されます。</span><span class="sxs-lookup"><span data-stu-id="54f4d-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="54f4d-119">そして、フィルターされたコレクションは **Set-CsArchivingConfiguration** コマンドレットにパイプ処理され、コレクション内の各項目が取得され、EnableArchiving の値が "ImOnly" に変更されます。</span><span class="sxs-lookup"><span data-stu-id="54f4d-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
