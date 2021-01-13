---
title: 仲介サーバーの全般設定の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a78fa8c12f2eb0db4cedd97a765e6445788c3382
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804267"
---
# <a name="mediation-server-general-settings-expander"></a>仲介サーバー全般設定エキスパンダー
 


## <a name="general-settings"></a>全般設定

仲介サーバー プールまたは仲介サーバーの完全修飾ドメイン名 (FQDN)。値を変更するには、サーバーの FQDN を編集します。新しい値と一致しているドメイン ネーム システム (DNS) ホスト (A) レコードがある必要があります。
  
**[関連付け]** で、仲介サーバー プールまたは仲介サーバーに関連付けるエッジ サーバーまたはエッジ サーバー プールを選択します。 仲介サーバーのメディア コンポーネントが外部ユーザー インターフェイスに使用するエッジを選択エンタープライズ VoIP。
  
現在エッジ サーバーを定義しておらず、仲介サーバーをエッジ サーバーに関連付ける必要がある場合、**[新規]** をクリックし、新しいエッジ プールの定義ウィザードで新しいエッジ サーバーまたはエッジ サーバー プールを定義します。
  
## <a name="next-hop-settings"></a>次ホップ設定

ドロップダウン リストから定義済みの Enterprise Edition フロント エンド プールまたは Standard Edition フロント エンド サーバーを選択して、仲介サーバー プールまたは仲介サーバーの次ホップを指定します。 ディレクターまたはディレクター プールは仲介サーバー プールまたは仲介サーバー次ホップの有効な選択肢ではないため、一覧には表示されません。 **[OK] を** クリックして変更を受け入れて保存します。 変更を破棄してプロパティ ページを終了するには、**[キャンセル]** をクリックします。
  
## <a name="pstn-gateway-settings"></a>PSTN ゲートウェイの設定

1. 仲介サーバー プールまたは仲介サーバーに関連付ける PSTN ゲートウェイを定義します。ゲートウェイを既に定義している場合は、それらのゲートウェイを仲介サーバーに関連付けることができます。仲介サーバーの併置を有効にする場合は、プール サーバーでのトランスポート層セキュリティ (TLS) のリッスン ポートの範囲を定義します。既定のポートは 5067 です。[**TCP ポートの有効化**] を選択する場合は、併置する仲介サーバーの伝送制御プロトコル (TCP) ポートを定義する必要があります。これは省略可能な設定です。この設定が必要かどうかは、ゲートウェイまたは PSTN の要件を参照して判断してください。既定では、TCP ポートの値は 5068 です。
    
2. 併置された仲介サーバーに関連付けるトランク。トランクを既に定義している場合は、それらのトランクを仲介サーバーに関連付けることができます。 
    
3. 複数のトランクを仲介サーバーに関連付けている場合は、トランクを選択して [**既定値にする**] をクリックすることで、既定のトランクを指定できます。既定のゲートウェイとしての選択を解除するには、[**既定値の解除**] をクリックします。 
    

