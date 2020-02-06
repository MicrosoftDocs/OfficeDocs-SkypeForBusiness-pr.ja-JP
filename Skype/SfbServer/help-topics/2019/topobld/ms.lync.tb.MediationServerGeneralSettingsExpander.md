---
title: 仲介サーバーの全般設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: be969f1dc3c860ccae3cd12b4e86d4b9e97788f2
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796226"
---
# <a name="mediation-server-general-settings-expander"></a>仲介サーバーの全般設定エキスパンダー
 


## <a name="general-settings"></a>全般設定

仲介サーバープールまたは仲介サーバーの完全修飾ドメイン名 (FQDN)。 値を変更するには、サーバーの FQDN を編集します。 新しい値と一致しているドメイン ネーム システム (DNS) ホスト (A) レコードがある必要があります。
  
[**関連付け**] セクションで、仲介サーバープールまたは仲介サーバーに関連付けるエッジサーバーまたはエッジサーバープールを選択します。 仲介サーバーのメディアコンポーネントで外部ユーザーのエンタープライズ Voip に使用されるエッジを選択します。
  
現在定義されている Edge サーバーがなく、仲介サーバーとエッジサーバーを関連付ける必要がある場合は、[**新規**作成] をクリックし、[新しいエッジプールの定義] ウィザードで新しいエッジサーバーまたはエッジサーバープールを定義します。
  
## <a name="next-hop-settings"></a>次ホップ設定

定義済みの Enterprise Edition のフロントエンドプールまたは標準エディションのフロントエンドサーバーをドロップダウンリストから選ぶことにより、仲介サーバープールまたは仲介サーバーの次ホップを指定します。 ディレクターまたはディレクタープールが、仲介サーバープールまたは仲介サーバーの次ホップの有効な選択ではないため、一覧に表示されません。 [ **OK]** をクリックして、変更を承諾して保存します。 変更を破棄してプロパティ ページを終了するには、[**キャンセル**] をクリックします。
  
## <a name="pstn-gateway-settings"></a>PSTN ゲートウェイの設定

1. 仲介サーバープールまたは仲介サーバーに関連付けられている PSTN ゲートウェイを定義します。 既にゲートウェイが定義されている場合は、それらを仲介サーバーと関連付けることができます。 仲介サーバーの collocation を有効にした場合、トランスポート層セキュリティ (TLS) のプールサーバーでリッスンポートの範囲を定義します。 既定では、このポートは5067です。 [ **Tcp ポートを有効に**する] を選択した場合、併置された仲介サーバーに対して伝送制御プロトコル (TCP) ポートを定義する必要があります。 これはオプションの設定であり、必要に応じてゲートウェイまたは PSTN の要件を確認する必要があります。 既定では、[TCP ポート] の値は5068です。
    
2. 併置された仲介サーバーに関連付けるトランク。トランクを既に定義している場合は、それらを仲介サーバーに関連付けることができます。 
    
3. 仲介サーバーと関連付けられているトランクが複数ある場合は、トランクを選択して「**デフォルト**に設定」をクリックすると、デフォルトのトランクを指定できます。 既定のゲートウェイとしての選択を解除するには、[**既定値の解除**] をクリックします。 
    

