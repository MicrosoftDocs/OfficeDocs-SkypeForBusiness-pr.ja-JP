---
title: ダイレクト ルーティングでメディア バイパスを構成する
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: このトピックでは、電話システムのダイレクトルーティングでメディアバイパスを構成する方法について説明します。
ms.openlocfilehash: 2931194783e2055c468ec2d7ad1286b9fe1940ae
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572236"
---
# <a name="configure-media-bypass-with-direct-routing"></a>ダイレクト ルーティングでメディア バイパスを構成する

ダイレクトルーティングを使用してメディアバイパスを構成する前に、[ダイレクトルーティングによるメディアバイパスの計画](direct-routing-plan-media-bypass.md)があることを確認してください。

メディアのバイパスを有効にするには、次の条件を満たしている必要があります。

1.  セッション境界コントローラー (SBC) ベンダーがメディアバイパスをサポートしていることを確認し、SBC でバイパスを構成する方法について説明します。 SBCs の詳細については、認定ページを参照してください。このページでは、メディアのバイパスがサポートされているものと手順について説明します。

2.  次のコマンドを使用して、トランクでメディアバイパスを有効にする必要があります: **CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**。

3.  必要なポートが開かれていることを確認します。 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>非バイパスの trunks からバイパス対応の trunks に移行する

一度にすべてのユーザーを切り替えることができます。また、段階的なアプローチを実装することもできます (推奨)。

- **一度にすべてのユーザーを切り替える。** すべての条件が満たされた場合は、バイパスモードをオンにすることができます。 ただし、すべての運用ユーザーが同時に切り替えられます。 Trunks とポートを構成するときに、最初にいくつかの問題が発生する可能性があるため、実稼働ユーザーエクスペリエンスに影響を与える可能性があります。 

- **段階的アプローチ。(推奨)**。  同じ SBC (別のポートを持つ) に新しいトランクを作成し、テストして、ユーザーが新しいトランクをポイントするようにオンラインボイスルーティングポリシーを変更します。 

  これは、スムーズな移行と中断のないユーザーエクスペリエンスを実現するために推奨されるアプローチです。 この方法では、SBC、新しい FQDN 名、ファイアウォールの構成が必要です。 注: 証明書で trunks の両方がサポートされていることを確認する必要があります。 SAN では、2つの名前 (**sbc1.contoso.com**と**sbc2.contoso.com**) を使用するか、ワイルドカード証明書を持っている必要があります。

![非バイパスの trunks からバイパス対応の trunks に移行する](media/direct-routing-media-bypass-8.png)

Trunks を構成して移行を実行する方法については、「SBC ベンダーのドキュメント」を参照してください。

- [AudioCodes の展開に関するドキュメント](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 展開に関するドキュメント](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [リボンの通信展開に関するドキュメント](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE システム (anynode) の展開ドキュメント](https://www.anynode.de/anynode-and-microsoft-teams/)

直接ルーティング用に認定したセッション境界コントローラー (SBCs) の一覧については、「[直接ルーティング用に認定済みのセッション罫線ありコントローラーの一覧](direct-routing-border-controllers.md)」を参照してください。



## <a name="see-also"></a>関連項目

[ダイレクトルーティングによるメディアバイパスの計画](direct-routing-plan-media-bypass.md)



