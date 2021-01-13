---
title: Skype for Business での PSTN 使用法レコードの表示
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: '概要: Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して PSTN 使用法レコードを表示する方法について説明します。'
ms.openlocfilehash: abf9f3ec9ce1e2801de2c6017d12fd64df0c8954
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830537"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="18c2b-103">Skype for Business での PSTN 使用法レコードの表示</span><span class="sxs-lookup"><span data-stu-id="18c2b-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="18c2b-104">**概要:** Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して PSTN 使用法レコードを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="18c2b-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="18c2b-105">公衆交換電話網 (PSTN) 使用法レコードは、組織内のさまざまなユーザーまたはユーザー グループが行える通話のクラス (内部、ローカル、長距離など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="18c2b-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="18c2b-106">詳細については、「計画」のドキュメントの「[PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx)」を参照してください｡</span><span class="sxs-lookup"><span data-stu-id="18c2b-106">For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="18c2b-107">Skype for Business Server コントロール パネルを使用して PSTN 使用法レコードを表示するには</span><span class="sxs-lookup"><span data-stu-id="18c2b-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="18c2b-108">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="18c2b-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="18c2b-109">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**PSTN 使用法**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18c2b-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="18c2b-110">[**PSTN 使用法**] ページで、表示する PSTN 使用法レコードを選択状態にし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18c2b-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="18c2b-111">選択した PSTN 使用法レコードの読み取り専用ページに、関連付けられたルートと関連付けられた音声ポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="18c2b-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="18c2b-112">Skype for Business Server 管理シェル コマンドレットを使用して PSTN 使用法情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="18c2b-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="18c2b-113">すべての PSTN 使用法に関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="18c2b-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```powershell
  Get-CsPstnUsage
  ```

    <span data-ttu-id="18c2b-114">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="18c2b-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="18c2b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="18c2b-115">See also</span></span>

[<span data-ttu-id="18c2b-116">音声ポリシーを作成または変更し、Skype for Business で PSTN 使用法レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="18c2b-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

