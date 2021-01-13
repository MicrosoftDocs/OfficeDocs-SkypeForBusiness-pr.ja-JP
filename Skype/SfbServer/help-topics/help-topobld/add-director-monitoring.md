---
title: ディレクターの監視を追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 100142faf2f9e552e5ad289fde6df0607669a09d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828917"
---
# <a name="add-director-monitoring"></a><span data-ttu-id="ece3a-103">ディレクターの監視の追加</span><span class="sxs-lookup"><span data-stu-id="ece3a-103">Add Director Monitoring</span></span>
 
<span data-ttu-id="ece3a-104">以下のプロパティを構成することにより、**監視 SQL Server ストアの定義** を行えます。</span><span class="sxs-lookup"><span data-stu-id="ece3a-104">You can **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="ece3a-105">**監視SQL Server:** リストから SQL Server 完全修飾ドメイン名 (FQDN) (および、必要に応じて名前付き SQL Server インスタンス) を選択します。</span><span class="sxs-lookup"><span data-stu-id="ece3a-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (FQDN) (and, optionally, a named SQL Server instance) from the list.</span></span>
    
    <span data-ttu-id="ece3a-106">[ **新規]** をクリックしてSQL Server FQDN 定義を作成し、必要に応じて監視サーバー ストアのインスタンス名を作成します。</span><span class="sxs-lookup"><span data-stu-id="ece3a-106">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="ece3a-107">監視サーバー **にSQL Serverミラーリング** を追加する場合は、[ストア ミラーリングを有効にする] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ece3a-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="ece3a-108">リストから既存の **監視 SQL Server ストア ミラー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ece3a-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="ece3a-109">[ **新規]** をクリックして、新SQL Server FQDN 定義を作成し、必要に応じてミラー ストアのインスタンス名を作成します。</span><span class="sxs-lookup"><span data-stu-id="ece3a-109">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="ece3a-110">[SQL Server ストアミラーリングを有効にする] を選択した場合は、必要に応じて **[SQL Server** ミラーリング監視を使用する] を選択して自動フェールオーバーを有効にし、一覧から SQL Server ミラーリング監視ストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="ece3a-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="ece3a-111">[ **新規]** をクリックして、新SQL Server FQDN 定義を作成し、必要に応じてミラーリング監視ストアのインスタンス名を作成します。</span><span class="sxs-lookup"><span data-stu-id="ece3a-111">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="ece3a-112">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ece3a-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="ece3a-113">このダイアログのオプションの入力が完了したら、[**次へ**] をクリックして、構成を続行します。</span><span class="sxs-lookup"><span data-stu-id="ece3a-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="ece3a-114">すべての変更を破棄し、ウィザードを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ece3a-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="ece3a-115">このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ece3a-115">Click **Help** to access context-sensitive help, such as this page.</span></span>
  

