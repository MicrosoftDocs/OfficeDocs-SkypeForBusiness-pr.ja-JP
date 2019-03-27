---
title: Lync Server 2010 のエッジ サーバー オプションの追加
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 新しいエッジ サーバーまたはエッジ プールを定義し、新しいサーバーまたはプールの機能を定義することが表示されます。 選択できるオプションは次のとおりです。
ms.openlocfilehash: 57c3916b1a43812c1f647f425fc9df65f99cff35
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897459"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Lync Server 2010 のエッジ サーバー オプションの追加

新しいエッジ サーバーまたはエッジ プールを定義し、新しいサーバーまたはプールの機能を定義することが表示されます。 選択できるオプションは次のとおりです。

- **単一の FQDN と IP アドレスを使用**: (選択した場合に IPv4 と IPv6 の両方を使用して、各 IP アドレスの種類のいずれかを定義する必要がありますが)、1 つの IPv4 または IPv6 を使用する] チェック ボックスをオンにアドレスと完全修飾ドメイン名 (FQDN) の外部エッジ インターフェイスです。

    > [!IMPORTANT]
    > このオプションを選択した場合のみ 1 つの IP アドレス、または 1 つの IPv4 と、1 つの IPv6 を使用するが、エッジ インターフェイスごとに異なるポート番号を割り当てる必要があります。

- **フェデレーション (ポート 5061) を有効にする**: その他の SIP フェデレーション、プロバイダー、またはセッション開始プロトコル (SIP) を使用するホストされたサービスとフェデレーションを行うが場合、このチェック ボックスをオンします。

- **このエッジ プールの外部 IP アドレスが NAT によって変換されます**: エッジの外部インターフェイスにプライベート IP アドレスを使用してエッジ サーバーを配置またはエッジ プールの論理的なネットワーク アドレス変換 (NAT) デバイスは、このチェック ボックスをオン分離します。

## <a name="see-also"></a>関連項目

[外部ユーザー アクセスの計画](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[外部ユーザー アクセスを展開します。](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
