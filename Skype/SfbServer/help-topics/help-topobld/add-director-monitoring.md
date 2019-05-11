---
title: ディレクターの監視の追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorMonitoringPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a9009434-3771-475f-8314-c104f2716a29
description: 次のプロパティを構成することによって、SQL Server の監視ストアを定義できます。
ms.openlocfilehash: 4aae503cea5731705f8d7416b8cb14e02dde28aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886502"
---
# <a name="add-director-monitoring"></a><span data-ttu-id="06092-103">ディレクターの監視の追加</span><span class="sxs-lookup"><span data-stu-id="06092-103">Add Director Monitoring</span></span>
 
<span data-ttu-id="06092-104">次のプロパティを構成することによって**SQL Server の監視ストアを定義する**実行できます。</span><span class="sxs-lookup"><span data-stu-id="06092-104">You can **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="06092-105">**SQL Server の監視を格納**: SQL Server の完全修飾ドメイン名 (FQDN) など、必要に応じて、名前付き SQL Server インスタンスをリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="06092-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (FQDN) (and, optionally, a named SQL Server instance) from the list.</span></span>
    
    <span data-ttu-id="06092-106">新しい SQL Server の FQDN の定義、および必要に応じて、監視サーバ ・ ストアのインスタンス名を作成する**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06092-106">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="06092-107">データベース ミラーリング監視サーバーを追加する場合は、**ストアを有効にする SQL Server のミラー化**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06092-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="06092-108">リストから**SQL Server の監視は、ミラーを格納**する既存を選択します。</span><span class="sxs-lookup"><span data-stu-id="06092-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="06092-109">新しい SQL Server の FQDN の定義、および必要に応じて、ミラー ・ ストアのインスタンス名を作成する**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06092-109">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="06092-110">**ストアを有効にする SQL Server のミラーリング**を選択した場合は、必要に応じて**使用して SQL Server の自動フェイル オーバー機能を有効にする補助をミラーリングする**ミラーリング監視ストアを一覧から、SQL Server を選択するを選択します。</span><span class="sxs-lookup"><span data-stu-id="06092-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="06092-111">新しい SQL Server の FQDN の定義、および必要に応じて、ミラーリング監視ストアのインスタンス名を作成する**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06092-111">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="06092-112">前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06092-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="06092-113">構成を続行するのには、このダイアログ ボックスのオプションの入力が終了したら**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06092-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="06092-114">すべての変更と、ウィザードを終了する**キャンセル**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06092-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="06092-115">このページなど、状況依存のヘルプにアクセスするため**のヘルプ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06092-115">Click **Help** to access context-sensitive help, such as this page.</span></span>
  

