---
title: フロントエンド監視ストアの追加ページ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 監視 SQL Server ストアを定義するには、次のプロパティを設定します。
ms.openlocfilehash: bd9a55e09a87f1c560f6e31d61094ddb915ad450
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275396"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="d11e9-103">フロントエンド監視ストアの追加ページ</span><span class="sxs-lookup"><span data-stu-id="d11e9-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="d11e9-104">**監視 SQL Server ストアを定義**するには、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="d11e9-105">**Sql server ストアの監視**: 一覧から sql server の完全修飾ドメイン名 (および必要に応じてインスタンス) を選択します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="d11e9-106">[**新規**] をクリックして、新しい SQL Server FQDN 定義を作成し、必要に応じて監視サーバーストアのインスタンス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="d11e9-107">監視サーバーのデータベースミラーリングを追加する場合は、[ **SQL Server ストアのミラーリングを有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d11e9-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="d11e9-108">既存の**監視 SQL Server ストアミラー**を一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="d11e9-109">[**新規**] をクリックして、新しい SQL Server FQDN 定義を作成し、必要に応じてミラーストアのインスタンス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="d11e9-110">[ **Sql server ストアのミラーリングを有効**にする] を選択した場合は、必要に応じて [ **sql server ミラーリング監視を有効にする**] を選択して、リストから sql server ミラーリング監視ストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="d11e9-111">[**新規**] をクリックして、新しい SQL Server FQDN 定義を作成し、必要に応じてミラーリング監視ストアのインスタンス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d11e9-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="d11e9-112">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d11e9-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="d11e9-113">このダイアログボックスのオプションを入力して構成を続行したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d11e9-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="d11e9-114">すべての変更を破棄してウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d11e9-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="d11e9-115">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d11e9-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d11e9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d11e9-116">See also</span></span>

[<span data-ttu-id="d11e9-117">Skype for Business Server 2015 での監視ストアとフロントエンド プールの関連付け</span><span class="sxs-lookup"><span data-stu-id="d11e9-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
