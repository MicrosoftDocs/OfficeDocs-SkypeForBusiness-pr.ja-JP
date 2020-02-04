---
title: フロントエンド監視ストアの追加ページ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
ROBOTS: NOINDEX, NOFOLLOW
description: 監視 SQL Server ストアを定義するには、次のプロパティを設定します。
ms.openlocfilehash: e9d26322fa9f3844864f9645e4dcefbccdddecd3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702862"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="81a40-103">フロントエンド監視ストアの追加ページ</span><span class="sxs-lookup"><span data-stu-id="81a40-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="81a40-104">**監視 SQL Server ストアを定義**するには、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="81a40-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="81a40-105">**Sql server ストアの監視**: 一覧から sql server の完全修飾ドメイン名 (および必要に応じてインスタンス) を選択します。</span><span class="sxs-lookup"><span data-stu-id="81a40-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="81a40-106">[**新規**] をクリックして、新しい SQL Server FQDN 定義を作成し、必要に応じて監視サーバーストアのインスタンス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="81a40-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="81a40-107">監視サーバーのデータベースミラーリングを追加する場合は、[ **SQL Server ストアのミラーリングを有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="81a40-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="81a40-108">既存の**監視 SQL Server ストアミラー**を一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="81a40-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="81a40-109">[**新規**] をクリックして、新しい SQL Server FQDN 定義を作成し、必要に応じてミラーストアのインスタンス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="81a40-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="81a40-110">[ **Sql server ストアのミラーリングを有効**にする] を選択した場合は、必要に応じて [ **sql server ミラーリング監視を有効にする**] を選択して、リストから sql server ミラーリング監視ストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="81a40-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="81a40-111">[**新規**] をクリックして、新しい SQL Server FQDN 定義を作成し、必要に応じてミラーリング監視ストアのインスタンス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="81a40-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="81a40-112">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81a40-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="81a40-113">このダイアログボックスのオプションを入力して構成を続行したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81a40-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="81a40-114">すべての変更を破棄してウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81a40-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="81a40-115">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81a40-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="81a40-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="81a40-116">See also</span></span>

[<span data-ttu-id="81a40-117">Skype for Business Server で監視ストアをフロントエンドプールに関連付ける</span><span class="sxs-lookup"><span data-stu-id="81a40-117">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span>](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
