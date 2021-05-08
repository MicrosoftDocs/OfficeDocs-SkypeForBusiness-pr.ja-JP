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
f1.keywords:
- NOCSH
description: すべてのユーザーを一度に切り替電話システム、または段階的なアプローチ (推奨) を実装することで、Microsoft Teams のダイレクト ルーティングを使用してメディア バイパスを構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416897"
---
# <a name="configure-media-bypass-with-direct-routing"></a>ダイレクト ルーティングでメディア バイパスを構成する

ダイレクト ルーティングを使用してメディア バイパスを構成する前に、「ダイレクト ルーティングを使用したメディア バイパス [の計画」を参照してください](direct-routing-plan-media-bypass.md)。

メディア バイパスを有効にするには、次の条件を満たしている必要があります。

1.    選択したセッション ボーダー コントローラー (SBC) ベンダーがメディア バイパスをサポートし、SBC でバイパスを構成する方法について説明します。 メディア バイパスをサポートする SBC と手順については、認定に関するページを参照してください。

2.    **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass**$true コマンドを使用して、トランクでメディア バイパスを有効にする必要があります。

3.    必要なポートが開いているか確認します。 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>バイパスされていないトランクからバイパスが有効なトランクに移行する

すべてのユーザーを一度に切り替えるか、段階的なアプローチ (推奨) を実装できます。

- **すべてのユーザーを一度に切り替えます。** すべての条件が満たされている場合は、バイパス モードをオンにできます。 ただし、すべての実稼働ユーザーが同時に切り替えます。 トランクとポートを構成するときに最初に問題が発生する可能性があります。この場合、実稼働環境のユーザー エクスペリエンスが影響を受ける可能性があります。 

- **段階的なアプローチ。(推奨)**。  同じ SBC 用の新しいトランクを (別のポートで) 作成し、テストし、新しいトランクを指すユーザーのオンライン音声ルーティング ポリシーを変更します。 

  これは、スムーズな切り替えと中断のないユーザー エクスペリエンスが可能なので、推奨されるアプローチです。 この方法では、SBC の構成、新しい FQDN 名、ファイアウォールの構成が必要です。 証明書が両方のトランクをサポートしている必要があります。 SAN では、2 つの名前 **(sbc1.contoso.com** と **sbc2.contoso.com)** を持つ必要があります。または、ワイルドカード証明書を持っている必要があります。

![バイパスされていないトランクからバイパスが有効なトランクに移行する)](media/direct-routing-media-bypass-8.png)

トランクを構成して移行を実行する方法については、SBC ベンダーのドキュメントを参照してください。

- [AudioCodes デプロイのドキュメント](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle デプロイのドキュメント](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [リボンコミュニケーションの展開に関するドキュメント](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode) のデプロイに関するドキュメント](https://www.anynode.de/anynode-and-microsoft-teams/)

直接ルーティングの認定を受けたセッション ボーダー コントローラー (SBC) の一覧については、「直接ルーティングの認定を受けた [セッション の一覧」を参照してください](direct-routing-border-controllers.md)。



## <a name="related-topics"></a>関連トピック

[ダイレクト ルーティングを使用してメディア バイパスを計画する](direct-routing-plan-media-bypass.md)



