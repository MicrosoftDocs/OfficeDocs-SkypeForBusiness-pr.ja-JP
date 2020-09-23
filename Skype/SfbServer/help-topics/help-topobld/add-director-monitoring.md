---
title: ディレクターの監視を追加する
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
- ms.lync.tb.AddDirectorMonitoringPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a9009434-3771-475f-8314-c104f2716a29
description: 以下のプロパティを構成することにより、監視 SQL Server ストアの定義を行えます。
ms.openlocfilehash: 48a626483da0dd69f46eca9740b0a9b224218f4d
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215498"
---
# <a name="add-director-monitoring"></a><span data-ttu-id="31e23-103">ディレクターの監視を追加する</span><span class="sxs-lookup"><span data-stu-id="31e23-103">Add Director Monitoring</span></span>
 
<span data-ttu-id="31e23-104">以下のプロパティを構成することにより、**監視 SQL Server ストアの定義**を行えます。</span><span class="sxs-lookup"><span data-stu-id="31e23-104">You can **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="31e23-105">**Sql server ストアの監視**: リストから sql server の完全修飾ドメイン名 (FQDN) (および必要に応じて、名前付き sql server インスタンス) を選択します。</span><span class="sxs-lookup"><span data-stu-id="31e23-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (FQDN) (and, optionally, a named SQL Server instance) from the list.</span></span>
    
    <span data-ttu-id="31e23-106">[ **新規** ] をクリックして、新しい SQL Server FQDN 定義を作成し、必要に応じて、監視サーバーストアのインスタンス名を作成します。</span><span class="sxs-lookup"><span data-stu-id="31e23-106">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="31e23-107">監視サーバーのデータベースミラーリングを追加する場合は、[ **SQL Server ストアミラーリングを有効** にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="31e23-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="31e23-108">リストから既存の**監視 SQL Server ストア ミラー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="31e23-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="31e23-109">[ **新規** ] をクリックして、新しい SQL Server FQDN 定義を作成し、必要に応じてミラーストアのインスタンス名を作成します。</span><span class="sxs-lookup"><span data-stu-id="31e23-109">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="31e23-110">[ **Sql server ストアミラーリングの有効化**] を選択した場合は、必要に応じて [ **sql server ミラーリング監視を有効にする** ] を選択して、リストから sql server ミラーリング監視ストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="31e23-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="31e23-111">[ **新規** ] をクリックして、新しい SQL Server FQDN 定義を作成し、必要に応じてミラーリング監視ストアのインスタンス名を作成します。</span><span class="sxs-lookup"><span data-stu-id="31e23-111">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="31e23-112">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31e23-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="31e23-113">このダイアログのオプションの入力が完了したら、[**次へ**] をクリックして、構成を続行します。</span><span class="sxs-lookup"><span data-stu-id="31e23-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="31e23-114">すべての変更を破棄し、ウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31e23-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="31e23-115">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31e23-115">Click **Help** to access context-sensitive help, such as this page.</span></span>
  

