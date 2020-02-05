---
title: Skype for Business での PSTN 使用状況レコードの表示
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使用して、PSTN 使用状況レコードを表示する方法について説明します。'
ms.openlocfilehash: 1f6cbd5bb013cd57f9304c3b0eb0c64ac7dabcff
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766920"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Skype for Business での PSTN 使用状況レコードの表示

**概要:** Skype for Business Server コントロールパネルまたは Skype for Business Server の管理シェルを使用して、PSTN 使用状況レコードを表示する方法について説明します。

公衆交換電話網 (PSTN) 使用法レコードは、組織内のさまざまなユーザーまたはグループが利用できる通話のクラス (内部、市内、長距離など) を指定します。詳細については、「計画」のドキュメントの「[PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx)」を参照してください。

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して PSTN 使用状況レコードを表示するには

1. Skype for Business Server コントロールパネルを開きます。

2. 左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**PSTN 使用法**] をクリックします。

3. [**PSTN 使用法**] ページで、表示する PSTN 使用法レコードを選択状態にし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

    > [!NOTE]
    > 選択した PSTN 使用法レコードの読み取り専用ページに、関連付けられたルートと関連付けられた音声ポリシーが表示されます。

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Skype for Business Server 管理シェルコマンドレットを使用して、PSTN の使用状況の情報を表示するには

- すべての PSTN 使用状況に関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。

  ```powershell
  Get-CsPstnUsage
  ```

    このコマンドは、次のような情報を返します。

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>関連項目

[Skype for Business で音声ポリシーを作成または変更し、PSTN 使用状況レコードを構成する](voice-policy-and-pstn-usage-records.md)

