---
title: Lync Server 2010 のエッジ サーバー オプションの追加
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
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 新しいエッジサーバーまたはエッジプールを定義し、新しいサーバーまたはプールの機能を定義する機会を提供します。 次のオプションを選ぶことができます。
ms.openlocfilehash: 983a8a6e4fdeea34930cc9adf2b2cb29e4c75759
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820989"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Lync Server 2010 のエッジ サーバー オプションの追加

新しいエッジサーバーまたはエッジプールを定義し、新しいサーバーまたはプールの機能を定義する機会を提供します。 次のオプションを選ぶことができます。

- **単一の FQDN と IP アドレスを使用**する: 1 つの ipv4 または ipv6 を使用する場合は、このチェックボックスをオンにします (Ipv4 と ipv6 の両方を使用する場合は、それぞれの IP アドレスの種類) アドレスと、外部エッジインターフェイスの完全修飾ドメイン名 (FQDN) を定義する必要があります)。

    > [!IMPORTANT]
    > このオプションを選択した場合は、1つの IP アドレス、または1つの IPv4 と1つの IPv6 のみを使用しますが、各エッジインターフェイスに異なるポート番号を割り当てる必要があります。

- **フェデレーションを有効にする (ポート 5061)**: セッション開始プロトコル (SIP) を使用する他の SIP フェデレーション、プロバイダー、またはホストされるサービスとフェデレーションを行う場合は、このチェックボックスをオンにします。

- **このエッジプールの外部 ip アドレスは、NAT によって変換され**ます。 edge の外部インターフェイスにプライベート IP アドレスを使い、ネットワークアドレス変換 (NAT) デバイスを提供して、エッジサーバーまたはエッジプールを論理的に分離する場合は、このチェックボックスをオンにします。

## <a name="see-also"></a>関連項目

[外部ユーザーアクセスの計画](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[外部ユーザーアクセスの展開](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
