---
title: ダイレクト ルーティングを構成する
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: オンプレミスのテレフォニー インフラストラクチャをネットワーク に接続するために Microsoft ダイレクト ルーティングを構成する方法Teams 電話システム。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b72a51008e2a5d55b57809ab5e8ae989f4ed3ec7
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518579"
---
# <a name="configure-direct-routing"></a>ダイレクト ルーティングを構成する

ダイレクト ルーティングを使用すると、オンプレミスのテレフォニー インフラストラクチャをネットワークにMicrosoft Teams。 この記事では、サポートされているオンプレミスのセッション ボーダー コントローラー (SBC) を直接ルーティングに接続するために必要な大きな手順と、直接ルーティングを使用して公衆交換電話網 (PSTN) に接続するために Teams ユーザーを構成する方法を示します。 この記事では、関連する記事にリンクして詳細を確認します。  

直接ルーティングが組織に適切なソリューションであるかどうかを確認するには、「PSTN 接続オプション [」を参照してください](pstn-connectivity.md)。 前提条件とデプロイの計画については、「直接ルーティングを計画 [する」を参照してください](direct-routing-plan.md)。

この記事で説明する手順を完了するには、管理者が PowerShell コマンドレットに精通している必要があります。 PowerShell の使い方の詳細については、「コンピューターのセットアップ」[を参照Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。 

これらの記事の手順を実行する前に、SBC ベンダーによって推奨される SBC が既に構成されていることを確認するようにお勧めします。 

- [AudioCodes デプロイのドキュメント](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle デプロイのドキュメント](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [リボンコミュニケーションの展開に関するドキュメント](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode) のデプロイに関するドキュメント](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Metaswitch のデプロイに関するドキュメント](https://www.metaswitch.com/products/core-network/perimeta-sbc)

サポートされている SBC の完全な一覧については、「直接ルーティングの [認定を受けたセッション ボーダー コントローラー」を参照してください](direct-routing-border-controllers.md)。

直接ルーティング電話システムを構成し、ユーザーが直接ルーティングを使用するには、次の手順に従います。 

- **手順 1.** [Connectを使用して SBC を電話システムし、接続を検証する](direct-routing-connect-the-sbc.md)
- **手順 2.** [ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする](direct-routing-enable-users.md)
- **手順 3.** [通話ルーティングを構成する](direct-routing-voice-routing.md)
- **手順 4.** [数値を別の形式に変換する](direct-routing-translate-numbers.md) 

複数のテナントに対して SBC を構成する場合は、「複数のテナントに対して SBC を構成する」 [も参照してください](direct-routing-sbc-multiple-tenants.md)。


## <a name="related-topics"></a>関連項目

[音声ソリューションを計画する](cloud-voice-landing-page.md)

[PSTN 接続オプション](pstn-connectivity.md)

[ダイレクト ルーティングを計画する](direct-routing-plan.md)