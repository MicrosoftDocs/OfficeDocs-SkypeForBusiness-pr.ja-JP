---
title: フロント エンドの監視ストアのページを追加します。
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 次のプロパティを構成することによって SQL Server の監視ストアを定義します。
ms.openlocfilehash: bb53d2105bc3a412b06d1fc51fbd4413c49271e6
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2018
ms.locfileid: "19988335"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="79be7-103">フロント エンドの監視ストアのページを追加します。</span><span class="sxs-lookup"><span data-stu-id="79be7-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="79be7-104">次のプロパティを構成することによって**SQL Server の監視ストアを定義**します。</span><span class="sxs-lookup"><span data-stu-id="79be7-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="79be7-105">**SQL Server の監視を格納**: SQL Server の完全修飾ドメイン名 (および、必要に応じてインスタンス) を一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="79be7-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="79be7-106">新しい SQL Server の FQDN の定義、およびオプションでサーバーの監視ストアのインスタンス名を作成する**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79be7-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="79be7-107">データベース ミラーリング監視サーバーを追加する場合は、**ストアを有効にする SQL Server のミラー化**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="79be7-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="79be7-108">リストから**SQL Server の監視は、ミラーを格納**する既存を選択します。</span><span class="sxs-lookup"><span data-stu-id="79be7-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="79be7-109">新しい SQL Server の FQDN の定義、および必要に応じてミラー ストアのインスタンス名を作成する**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79be7-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="79be7-110">**ストアを有効にする SQL Server のミラーリング**を選択した場合は、必要に応じて**使用して SQL Server の自動フェイル オーバー機能を有効にする補助をミラーリングする**ミラーリング監視ストアを一覧から、SQL Server を選択するを選択します。</span><span class="sxs-lookup"><span data-stu-id="79be7-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="79be7-111">新しい SQL Server の FQDN の定義、および必要に応じてミラーリング監視ストアのインスタンス名を作成する**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79be7-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="79be7-112">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79be7-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="79be7-113">構成を続行するのには、このダイアログ ボックスのオプションの入力が終了したら**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79be7-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="79be7-114">すべての変更と、ウィザードを終了する**キャンセル**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79be7-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="79be7-115">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79be7-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="79be7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="79be7-116">See also</span></span>

[<span data-ttu-id="79be7-117">ビジネス サーバーのフロント エンド プールを Skype 監視ストアに関連付ける</span><span class="sxs-lookup"><span data-stu-id="79be7-117">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span>](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)