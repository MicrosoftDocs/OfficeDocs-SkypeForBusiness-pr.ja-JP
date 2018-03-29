---
title: Skype for Business Server 2015 での PSTN 使用法レコードの表示
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: '概要: ビジネス サーバー管理シェルのビジネス サーバーのコントロール パネルまたは、Skype、Skype を使用して PSTN 使用法レコードを表示する方法を説明します。'
ms.openlocfilehash: 63e35879f9530d56ef770584de45a169c20ea057
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="view-pstn-usage-records-in-skype-for-business-2015"></a><span data-ttu-id="5dcc5-103">Skype for Business Server 2015 での PSTN 使用法レコードの表示</span><span class="sxs-lookup"><span data-stu-id="5dcc5-103">View PSTN usage records in Skype for Business 2015</span></span>
 
<span data-ttu-id="5dcc5-104">**の概要:**ビジネス サーバー管理シェルのビジネス サーバーのコントロール パネルまたは、Skype、Skype を使用して PSTN 使用法レコードを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5dcc5-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="5dcc5-105">公衆交換電話網 (PSTN) 使用法レコードは、組織内のさまざまなユーザーまたはグループが利用できる通話のクラス (内部、市内、長距離など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="5dcc5-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="5dcc5-106">詳細については、計画ドキュメントの[PSTN 使用法レコード](http://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dcc5-106">For details, see [PSTN Usage Records](http://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>
  
### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5dcc5-107">ビジネス サーバーのコントロール パネルの Skype を使用して、PSTN 使用法レコードを表示するのには</span><span class="sxs-lookup"><span data-stu-id="5dcc5-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="5dcc5-108">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5dcc5-108">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="5dcc5-109">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**PSTN 使用法**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dcc5-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>
    
3. <span data-ttu-id="5dcc5-110">[**PSTN 使用法**] ページで、表示する PSTN 使用法レコードを選択状態にし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dcc5-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5dcc5-111">選択した PSTN 使用法レコードの読み取り専用ページに、関連付けられたルートと関連付けられた音声ポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcc5-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span> 
  
### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="5dcc5-112">Skype ビジネス サーバー管理シェル コマンドレットを使用して PSTN の使用状況に関する情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="5dcc5-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="5dcc5-113">すべての PSTN 使用法の情報を表示するのには、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5dcc5-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
  ```
  Get-CsPstnUsage
  ```

    <span data-ttu-id="5dcc5-114">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="5dcc5-114">This command returns information similar to the following:</span></span>
    
  ```
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
  ```

## <a name="see-also"></a><span data-ttu-id="5dcc5-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5dcc5-115">See also</span></span>

#### 

[<span data-ttu-id="5dcc5-116">作成し、音声ポリシーを変更またはビジネス 2015年の Skype の PSTN 使用法レコードを構成します。</span><span class="sxs-lookup"><span data-stu-id="5dcc5-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)

