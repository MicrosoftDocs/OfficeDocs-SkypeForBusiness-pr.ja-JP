---
title: Lync Server 2010 仲介サーバーの全般設定の展開
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: このダイアログ ボックス内の仲介サーバーのプロパティを編集するとします。 左側にあるをクリックすると全般的な設定、次のホップの設定、および PSTN ゲートウェイの設定の設定へのクイック リンクのセットです。 各セクションで、次の設定です。
ms.openlocfilehash: 262cdcbbbf4c4cfcf35a01de91c88c6511da3360
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260476"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Lync Server 2010 仲介サーバーの全般設定の展開

このダイアログ ボックス内の仲介サーバーのプロパティを編集するとします。 左側にあるをクリックすると全般的な設定、次のホップの設定、および PSTN ゲートウェイの設定の設定へのクイック リンクのセットです。 各セクションで、次の設定です。

 **全般**。

- **FQDN**: 仲介サーバーの完全修飾ドメイン名を編集します。

- **関連付け**:**関連付けるエッジ プール**を (メディア コンポーネント) のチェック ボックスをオンにし、外部アクセス用のメディアのパスとして使用するには、エッジ サーバーまたは仲介サーバーのエッジ プールを選択します。

 **次ホップ**:

- **次ホップの選択**: 展開と通信するために使用する仲介サーバーへのパスとして使用するフロント エンド サーバーまたはフロント エンド プールを一覧から選択します。

 **PSTN ゲートウェイ**:

 **仲介サーバー PSTN ゲートウェイ**:

- **リッスンするポート**: 仲介サーバーがリッスンするポートを定義します。 **TLS**またはトランスポート層セキュリティ、または**TCP**のポートを定義することができますまたはトランス ポート プロトコルを制御します。 使用する TCP のポートのエントリを**有効にする TCP ポート**のチェック ボックスを選択します。

    > [!IMPORTANT]
    > TLS と TCP のどちらか一方または両方のポートの値を有効にして、定義する必要がある場合を判断するのには公衆交換電話網 (PSTN) ゲートウェイのドキュメントおよび構成の設定] を参照してください。 TLS は、仲介サーバーと PSTN ゲートウェイ間のトラフィックを暗号化する証明書を使用して、安全なプロトコルです。 すべての PSTN ゲートウェイが TLS をサポートします。

- SIP トランクと定義して、展開用に構成されているゲートウェイの一覧が表示されます。 エントリが存在しない場合がない SIP トランクまたは PSTN ゲートウェイの展開用に構成されています。 定義し、トポロジ ビルダーでトランクおよび**共有コンポーネント**] の下のゲートウェイを構成します。

## <a name="see-also"></a>関連項目

[SIP トランクの概要](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[PSTN ゲートウェイの展開オプション](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)