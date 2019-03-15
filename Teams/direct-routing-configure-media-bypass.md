---
title: メディア バイ パスを直接ルーティングの構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 電話システムの直接のルーティングを使用してメディア バイ パスを構成する方法については、このトピックを参照してください。
ms.openlocfilehash: 405f71fd0a1e0ea3e8fec6ee1061786c93fabf1b
ms.sourcegitcommit: 260635a24b282fbdf4a4aeffdb0f4f9be5407ec6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "30631066"
---
# <a name="configure-media-bypass-with-direct-routing"></a>メディア バイ パスを直接ルーティングの構成します。

構成のメディアは、直接ルーティングをバイパスする前に、[メディアの計画に直接ルーティングをバイパス](direct-routing-plan-media-bypass.md)を読んだことを確認します。

メディアのバイパスを有効にするのには次の条件を満たす必要があります。

1.  任意のセッション ボーダー コント ローラー (SBC) ベンダーがメディア バイ パスがサポートされていてを構成する手順については、SBC のバイパスは、確認します。 SBCs、するもののサポート ・ メディアは、次の回避、および手順についての説明に証明のページを参照してください。

2.  次のコマンドを使用してトランク上のメディア バイ パスを有効にする必要があります:**セット CSOnlinePSTNGateway ・ アイデンティティの <sbc_FQDN> - MediaBypass $true**。

3.  必要なポートが開かれることを確認します。 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>非バイパスのトランクからトランクのバイパスが有効なへの移行します。

一度にすべてのユーザーを切り替えることができますまたは段階的なアプローチを実装することができます (推奨)。

- **一度にすべてのユーザーを切り替えます。** すべての条件を満たしている場合は、バイパス モードをオンにします。 ただし、運用環境のすべてのユーザーは、同時に切り替えられます。 トランクとポートを構成するときに最初にいくつかの問題が発生する可能性があります、ため、運用環境のユーザー エクスペリエンスの影響を受けます。 

- **Phased アプローチです。(推奨)**。  (別のポート) を持つ同じ SBC の新しい樹幹を作成、テスト、および新しいトランクを指すようにユーザーのオンラインの音声ルーティング ポリシーを変更します。 

  これは、滑らかな切り替えと中断のないユーザー エクスペリエンスのための推奨される方法です。 このアプローチでは、SBC、新しい FQDN 名では、ファイアウォールの設定の構成が必要です。 証明書が両方のトランクをサポートしているかどうかを確認する必要があります注意してください。 SAN では、(**sbc1.contoso.com**および**sbc2.contoso.com**) の 2 つの名前またはワイルドカード証明書が存在する必要があります。

![非バイパスのトランクからトランクのバイパスが有効に移行)](media/direct-routing-media-bypass-8.png)

トランクを構成し、移行を実行する方法については、SBC の製造元に問い合わせてからのマニュアルを参照してください。

- AudioCodes
- リボン
- TE ・ システム (AnyNode)    

今回の発表の時点で、次の SBCs が徹底的なテスト/メディア バイ パスで機能する認定は。

- 9000 V7.20A.204.222、SBC では M800B/V7.20A.250.003

-   リボン
    - - xxx 5210 v06.02.xx 
    - 5400、v06.02.xx xxx
    - 5110、v06.02.xx xxx

-   TE システム AnyNode v 3.16.2 


## <a name="see-also"></a>関連項目

[直接ルーティングでのメディア バイ パスを計画します。](direct-routing-plan-media-bypass.md)



