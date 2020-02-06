---
title: Lync Server 2010 用の仲介サーバー全般設定の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: このダイアログボックスで、仲介サーバーのプロパティを編集します。 左側には、[全般設定]、[次ホップの設定]、[PSTN ゲートウェイ] の設定の設定に移動するためのクイックリンクがあります。 各セクションには、次の設定があります。
ms.openlocfilehash: 3f7dad61778f54fee7a9be984191bc21f5029502
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819619"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Lync Server 2010 用の仲介サーバー全般設定の展開

このダイアログボックスで、仲介サーバーのプロパティを編集します。 左側には、[全般設定]、[次ホップの設定]、[PSTN ゲートウェイ] の設定の設定に移動するためのクイックリンクがあります。 各セクションには、次の設定があります。

 **一般的な**方法:

- [ **FQDN**: 仲介サーバーの完全修飾ドメイン名を編集します。

- [**関連付け**]: [ **Edge プールを関連付ける (メディアコンポーネント用)** ] チェックボックスをオンにし、仲介サーバーが外部アクセスのメディアパスとして使用するエッジサーバーまたはエッジプールを選択します。

  **次のホップ**:

- **[次のホップの選択**]: 展開との通信に使用する仲介サーバーのパスとして使用するフロントエンドサーバーまたはフロントエンドプールの一覧から選択します。

  **PSTN ゲートウェイ**:

  **仲介サーバー PSTN ゲートウェイ**:

- **リスニングポート**: 仲介サーバーがリッスンするポートを定義します。 **TLS**またはトランスポート層のセキュリティ、 **TCP**、またはトランスポート制御プロトコルのポートを定義できます。 TCP 用のポートエントリを利用できるようにするには、[ **tcp ポートを有効**にする] チェックボックスをオンにする必要があります。

    > [!IMPORTANT]
    > ポート値 TLS、TCP、またはその両方を有効にする必要があるかどうかを判断するには、公衆交換電話網 (PSTN) ゲートウェイのドキュメントと構成の設定を参照してください。 TLS はセキュリティで保護されたプロトコルであり、証明書を使って仲介サーバーと PSTN ゲートウェイ間のトラフィックを暗号化します。 すべての PSTN ゲートウェイで TLS がサポートされるわけではありません。

- 展開用に定義および構成されている SIP trunks とゲートウェイの一覧が表示されます。 エントリが存在しない場合は、展開用に構成された SIP trunks または PSTN ゲートウェイがありません。 Trunks とゲートウェイは、「トポロジビルダーの**共有コンポーネント**」で定義して構成します。

## <a name="see-also"></a>関連項目

[SIP トランクの概要](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[PSTN ゲートウェイの展開オプション](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
