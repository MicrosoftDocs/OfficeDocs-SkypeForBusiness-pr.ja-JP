---
title: Skype for Business Server 2015 での PSTN 使用法レコードの表示
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: '概要: ビジネス サーバー管理シェルのビジネス サーバーのコントロール パネルまたは、Skype、Skype を使用して PSTN 使用法レコードを表示する方法を説明します。'
ms.openlocfilehash: e4e58326fade20a48b032cf6cdc575894152fac0
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="view-pstn-usage-records-in-skype-for-business-2015"></a>Skype for Business Server 2015 での PSTN 使用法レコードの表示
 
**の概要:** ビジネス サーバー管理シェルのビジネス サーバーのコントロール パネルまたは、Skype、Skype を使用して PSTN 使用法レコードを表示する方法について説明します。
  
公衆交換電話網 (PSTN) 使用法レコードは、組織内のさまざまなユーザーまたはグループが利用できる通話のクラス (内部、市内、長距離など) を指定します。 詳細については、計画ドキュメントの[PSTN 使用法レコード](http://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx)を参照してください。
  
### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、PSTN 使用法レコードを表示するのには

1. Skype をビジネス サーバーのコントロール パネルを開きます。
    
2. 左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**PSTN 使用法**] をクリックします。
    
3. [**PSTN 使用法**] ページで、表示する PSTN 使用法レコードを選択状態にし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。 
    
    > [!NOTE]
    > 選択した PSTN 使用法レコードの読み取り専用ページに、関連付けられたルートと関連付けられた音声ポリシーが表示されます。 
  
### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Skype ビジネス サーバー管理シェル コマンドレットを使用して PSTN の使用状況に関する情報を表示するのには

- すべての PSTN 使用法の情報を表示するのには、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、し、ENTER キーを押します。
    
  ```
  Get-CsPstnUsage
  ```

    このコマンドは、次のような情報を返します。
    
  ```
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
  ```

## <a name="see-also"></a>関連項目

#### 

[作成し、音声ポリシーを変更またはビジネス 2015年の Skype の PSTN 使用法レコードを構成します。](voice-policy-and-pstn-usage-records.md)

