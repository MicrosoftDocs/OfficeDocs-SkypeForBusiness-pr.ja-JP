---
title: Skype for Business で PSTN 使用法レコードを表示する
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
ms.openlocfilehash: 6a447f7aeb9db0a7ca858cf58df10273c28b533b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109833"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Skype for Business で PSTN 使用法レコードを表示する

**概要:** Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して PSTN 使用法レコードを表示する方法について説明します。

公衆交換電話網 (PSTN) 使用法レコードは、組織内のさまざまなユーザーまたはユーザー グループが行う通話のクラス (内部、ローカル、長距離など) を指定します。 詳細については、「計画」のドキュメントの「[PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records)」を参照してください｡

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して PSTN 使用法レコードを表示するには

1. Skype for Business Server コントロール パネルを開きます。

2. 左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**PSTN 使用法**] をクリックします。

3. [**PSTN 使用法**] ページで、表示する PSTN 使用法レコードを選択状態にし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

    > [!NOTE]
    > 選択した PSTN 使用法レコードの読み取り専用ページに、関連付けられたルートと関連付けられた音声ポリシーが表示されます。

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Skype for Business Server Management Shell コマンドレットを使用して PSTN 使用法情報を表示するには

- すべての PSTN 使用法に関する情報を表示するには、Skype for Business Server 管理シェルに次のコマンドを入力し、Enter キーを押します。

  ```powershell
  Get-CsPstnUsage
  ```

    このコマンドは、次のような情報を返します。

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>関連項目

[音声ポリシーを作成または変更し、Skype for Business で PSTN 使用法レコードを構成する](voice-policy-and-pstn-usage-records.md)