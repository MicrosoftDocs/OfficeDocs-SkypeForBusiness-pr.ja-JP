---
title: フロントエンド監視ストアの追加ページ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: '[監視 SQL Server ストアの定義] を行うには、次のプロパティを構成します。'
ms.openlocfilehash: 85b8518bb533de68423dea93f259fc7b927ed9ba
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218878"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="9d7c1-103">フロントエンド監視ストアの追加ページ</span><span class="sxs-lookup"><span data-stu-id="9d7c1-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="9d7c1-104">[**監視 SQL Server ストアの定義**] を行うには、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9d7c1-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="9d7c1-105">**Sql server ストアの監視**: リストから sql server の完全修飾ドメイン名 (および必要に応じてインスタンス) を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d7c1-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="9d7c1-106">[ **新規** ] をクリックして、新しい SQL Server FQDN 定義を作成し、必要に応じて監視サーバーストアのインスタンス名を作成します。</span><span class="sxs-lookup"><span data-stu-id="9d7c1-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="9d7c1-107">監視サーバーのデータベースミラーリングを追加する場合は、[ **SQL Server ストアミラーリングを有効** にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9d7c1-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="9d7c1-108">リストから既存の**監視 SQL Server ストア ミラー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d7c1-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="9d7c1-109">[ **新規** ] をクリックして、新しい SQL Server FQDN 定義を作成し、必要に応じてミラーストアのインスタンス名を作成します。</span><span class="sxs-lookup"><span data-stu-id="9d7c1-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="9d7c1-110">[ **Sql server ストアミラーリングの有効化**] を選択した場合は、必要に応じて [ **sql server ミラーリング監視を有効にする** ] を選択して、リストから sql server ミラーリング監視ストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="9d7c1-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="9d7c1-111">[ **新規** ] をクリックして、新しい SQL Server FQDN 定義を作成し、必要に応じてミラーリング監視ストアのインスタンス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d7c1-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="9d7c1-112">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d7c1-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="9d7c1-113">このダイアログのオプションの入力が完了したら、[**次へ**] をクリックして、構成を続行します。</span><span class="sxs-lookup"><span data-stu-id="9d7c1-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="9d7c1-114">すべての変更を破棄し、ウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d7c1-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="9d7c1-115">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d7c1-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9d7c1-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d7c1-116">See also</span></span>

[<span data-ttu-id="9d7c1-117">Skype for Business Server 2015 でのフロントエンドプールへの監視ストアの関連付け</span><span class="sxs-lookup"><span data-stu-id="9d7c1-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
