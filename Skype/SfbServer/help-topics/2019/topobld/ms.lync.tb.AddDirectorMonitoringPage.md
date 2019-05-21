---
title: ディレクターの監視の追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorMonitoringPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a9009434-3771-475f-8314-c104f2716a29
ROBOTS: NOINDEX, NOFOLLOW
description: 次のプロパティを構成することで、監視 SQL Server ストアを定義できます。
ms.openlocfilehash: dd6381588580bb5761fdc727630b58d115921d9d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305182"
---
# <a name="add-director-monitoring"></a><span data-ttu-id="2557f-103">ディレクターの監視の追加</span><span class="sxs-lookup"><span data-stu-id="2557f-103">Add Director Monitoring</span></span>
 
<span data-ttu-id="2557f-104">次のプロパティを構成することで **、監視 SQL Server ストアを定義**できます。</span><span class="sxs-lookup"><span data-stu-id="2557f-104">You can **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="2557f-105">**Sql server ストアの監視**: リストから sql server の完全修飾ドメイン名 (FQDN) を選択します (必要に応じて、名前付きの sql server インスタンスも選択します)。</span><span class="sxs-lookup"><span data-stu-id="2557f-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (FQDN) (and, optionally, a named SQL Server instance) from the list.</span></span>
    
    <span data-ttu-id="2557f-106">[**新規**] をクリックして、新しい SQL Server FQDN 定義を作成します。必要に応じて、監視サーバーストアのインスタンス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2557f-106">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="2557f-107">監視サーバーのデータベースミラーリングを追加する場合は、[ **SQL Server ストアのミラーリングを有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2557f-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="2557f-108">既存の**監視 SQL Server ストアミラー**を一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="2557f-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="2557f-109">[**新規**] をクリックして、新しい SQL Server FQDN 定義を作成します。必要に応じて、ミラーストアのインスタンス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2557f-109">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="2557f-110">[ **Sql server ストアのミラーリングを有効**にする] を選択した場合は、必要に応じて [ **sql server ミラーリング監視を有効にする**] を選択して、リストから sql server ミラーリング監視ストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="2557f-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="2557f-111">[**新規**] をクリックして、新しい SQL Server FQDN 定義を作成します。必要に応じて、ミラーリング監視ストアのインスタンス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2557f-111">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="2557f-112">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2557f-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="2557f-113">このダイアログボックスのオプションを入力して構成を続行したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2557f-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="2557f-114">すべての変更を破棄してウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2557f-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="2557f-115">このページなどの状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2557f-115">Click **Help** to access context-sensitive help, such as this page.</span></span>
  

