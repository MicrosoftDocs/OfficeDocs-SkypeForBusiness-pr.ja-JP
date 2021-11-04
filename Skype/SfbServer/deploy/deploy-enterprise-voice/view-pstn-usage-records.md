---
title: '[PSTN 使用法レコードの表示] Skype for Business'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: '概要: [コントロール パネル] または [管理シェル] を使用して PSTN 使用法Skype for Business Serverを表示するSkype for Business Server説明します。'
ms.openlocfilehash: 2b09ed19de6ff205ee7d76e7379c8b4c5fc12d06
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771522"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>[PSTN 使用法レコードの表示] Skype for Business

**概要:**[コントロール パネル] または [管理シェル] を使用して PSTN 使用法Skype for Business Serverを表示するSkype for Business Server説明します。

公衆交換電話網 (PSTN) 使用法レコードは、組織内のさまざまなユーザーまたはユーザー グループが行う通話のクラス (内部、ローカル、長距離など) を指定します。 詳細については、「計画」のドキュメントの「[PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records)」を参照してください｡

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用して PSTN 使用法レコードSkype for Business Serverするには

1. [コントロール Skype for Business Server] を開きます。

2. 左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**PSTN 使用法**] をクリックします。

3. [**PSTN 使用法**] ページで、表示する PSTN 使用法レコードを選択状態にし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

    > [!NOTE]
    > 選択した PSTN 使用法レコードの読み取り専用ページに、関連付けられたルートと関連付けられた音声ポリシーが表示されます。

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>管理シェルコマンドレットを使用して PSTN Skype for Business Serverを表示するには

- すべての PSTN 使用法に関する情報を表示するには、次のコマンドを [管理シェル] Skype for Business Server入力し、Enter キーを押します。

  ```powershell
  Get-CsPstnUsage
  ```

    このコマンドは、次のような情報を返します。

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>関連項目

[音声ポリシーを作成または変更し、音声ポリシーで PSTN 使用法レコードを構成Skype for Business](voice-policy-and-pstn-usage-records.md)