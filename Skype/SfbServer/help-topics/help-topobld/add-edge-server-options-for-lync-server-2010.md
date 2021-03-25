---
title: Lync Server 2010 のエッジ サーバー オプションを追加する
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
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 新しいエッジ サーバーまたはエッジ プールを定義し、新しいサーバーまたはプールの機能を定義する機会が提供されます。 選択できるオプションは、次のとおりです。
ms.openlocfilehash: dfc8238bbbe4899f9819118a11fc11ba47fe21f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119806"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Lync Server 2010 のエッジ サーバー オプションの追加

新しいエッジ サーバーまたはエッジ プールを定義し、新しいサーバーまたはプールの機能を定義する機会が提供されます。 選択できるオプションは、次のとおりです。

- [**単一の FQDN と IP アドレスを使います**]: 単一の IPv4 アドレスまたは IPv6 アドレス (IPv4 と IPv6 の両方を使用する場合は、それぞれの IP アドレスの種類で 1 つずつ定義する必要があります) と外部エッジ インターフェイスの完全修飾ドメイン名を使用する場合は、このチェック ボックスをオンにします。

    > [!IMPORTANT]
    > このオプションを選択した場合は、IP アドレスを 1 つだけ使用するか、IPv4 と IPv6 を 1 つずつ使用することになりますが、各エッジ インターフェイスには別々のポート番号を割り当てる必要があります。

- [**フェデレーションを有効にします (ポート 5061)**]: セッション開始プロトコル (SIP) を使用している他の SIP フェデレーション、プロバイダー、またはホストされているオファリングとのフェデレーションを行う場合は、このチェック ボックスをオンにします。

- **この** エッジ プールの外部 IP アドレスは NAT によって変換されます。エッジ外部インターフェイスにプライベート IP アドレスを使用し、エッジ サーバーまたはエッジ プールを論理的に背後に配置するネットワーク アドレス変換 (NAT) デバイスを提供する場合は、このチェック ボックスをオンにします。

## <a name="see-also"></a>関連項目

[外部ユーザー アクセスの計画](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)

[エッジ サーバーの展開](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-external-user-access)