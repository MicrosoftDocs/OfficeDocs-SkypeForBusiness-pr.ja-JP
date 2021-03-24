---
title: Lync Server 2010 用の仲介サーバー全般設定の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 仲介サーバーのプロパティは、このダイアログで編集します。 左側にクイック リンクのセットがあり、これらにより、[全般] 設定、[次ホップ] 設定、および [PSTN ゲートウェイ] 設定の設定に移動できます。 各セクションには次の設定があります。
ms.openlocfilehash: 6c8c238ce7d89db53f3b92a0f513c080976a3bab
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114193"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Lync Server 2010 用の仲介サーバー全般設定エキスパンダー

仲介サーバーのプロパティは、このダイアログで編集します。 左側にクイック リンクのセットがあり、これらにより、[全般] 設定、[次ホップ] 設定、および [PSTN ゲートウェイ] 設定の設定に移動できます。 各セクションには次の設定があります。

 **全般**:

- **FQDN**: 仲介サーバーの完全修飾ドメイン名を編集します。

- **関連付** け : [エッジ プールの関連付け (メディア コンポーネント **用)]** チェック ボックスをオンにし、仲介サーバーが外部アクセスのメディア パスとして使用するエッジ サーバーまたはエッジ プールを選択します。

  [**次ホップ**]:

- **次ホップの選択**: 展開との通信に使用する仲介サーバーのパスとして使用するフロント エンド サーバーまたはフロント エンド プールを一覧から選択します。

  [**PSTN ゲートウェイ**]:

  [**仲介サーバーの PSTN ゲートウェイ**]:

- **リッスン ポート**: 仲介サーバーがリッスンするポートを定義します。 **TLS** (トランスポート層セキュリティ) または **TCP** (伝送制御プロトコル) 用のポートを定義できます。 TCP 用のポート エントリを利用できるようにするには、[**TCP ポートを有効にする**] チェック ボックスをオンにする必要があります。

    > [!IMPORTANT]
    > ご使用の公衆交換電話網 (PSTN) ゲートウェイのドキュメントおよび構成設定を参照し、ポート値 TLS、TCP、またはその両方の有効化および定義が必要かどうかを判断します。 TLS は、仲介サーバーと PSTN ゲートウェイ間のトラフィックを暗号化するために証明書を使用して、より安全なプロトコルです。 すべての PSTN ゲートウェイが TLS をサポートするわけではありません。

- 展開で定義および構成されている SIP トランクおよびゲートウェイのリストが一覧表示されます。 エントリが存在しない場合、ご使用の展開で構成されている SIP トランクまたは PSTN ゲートウェイはありません。 トポロジ ビルダーの [共有コンポーネント] でトランクとゲートウェイを **定義および** 構成します。

## <a name="see-also"></a>関連項目

[SIP トランキングの概要](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-sip-trunking)

[PSTN ゲートウェイの展開オプション](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-gateway-deployment-options)