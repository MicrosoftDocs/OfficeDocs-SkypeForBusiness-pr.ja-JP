---
title: ダイレクト ルーティングを構成する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
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
description: オンプレミスのテレフォニー インフラストラクチャをMicrosoft 電話システム ダイレクト ルーティングを構成する方法について説明Microsoft Teams。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122241"
---
# <a name="configure-direct-routing"></a>ダイレクト ルーティングを構成する

Microsoft 電話システム ダイレクト ルーティングを使用すると、オンプレミスのテレフォニー インフラストラクチャをネットワークにMicrosoft Teams。 この記事では、サポートされているオンプレミスのセッション ボーダー コントローラー (SBC) を直接ルーティングに接続するために必要な大きな手順と、直接ルーティングを使用して公衆交換電話網 (PSTN) に接続するために Teams ユーザーを構成する方法を示します。 この記事では、関連する記事にリンクして詳細を確認します。  

ダイレクト ルーティングが組織に適切なソリューションであるかどうかを確認するには、「ダイレクト ルーティング」を電話システム[参照してください](direct-routing-landing-page.md)。 前提条件とデプロイの計画については、「直接ルーティングを計画 [する」を参照してください](direct-routing-plan.md)。

> [!Tip]
> ダイレクト ルーティングの利点、その計画方法、デプロイ方法については、次のセッションをご[Microsoft Teams覧](https://aka.ms/teams-direct-routing)ください。

この記事で説明する手順を完了するには、管理者が PowerShell コマンドレットに精通している必要があります。 PowerShell の使用の詳細については、「コンピューターをセットアップする」[を](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)参照Windows PowerShell。 

これらの記事の手順を実行する前に、SBC ベンダーによって推奨される SBC が既に構成されていることを確認するようにお勧めします。 

- [AudioCodes デプロイのドキュメント](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle デプロイのドキュメント](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [リボンコミュニケーションの展開に関するドキュメント](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode) のデプロイに関するドキュメント](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Metaswitch のデプロイに関するドキュメント](https://www.metaswitch.com/products/core-network/perimeta-sbc)

サポートされている SBC の完全な一覧については、「ダイレクト ルーティングの認定を受けたセッション ボーダー コントローラーの一覧 [」を参照してください](direct-routing-border-controllers.md)。

Microsoft 電話 システムを構成し、ユーザーが直接ルーティングを使用するには、次の手順に従います。 

- **手順 1.** [Connect システムを使用して SBC Microsoft 電話し、接続を検証する](direct-routing-connect-the-sbc.md)
- **手順 2.** [ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする](direct-routing-enable-users.md)
- **手順 3.** [音声ルーティングを構成する](direct-routing-voice-routing.md)
- **手順 4.** [数値を別の形式に変換する](direct-routing-translate-numbers.md) 

複数のテナントに対して SBC を構成する場合は、複数のテナントの SBC の構成に関する記事 [も参照してください](direct-routing-sbc-multiple-tenants.md)。


## <a name="related-topics"></a>関連トピック

[電話システムのダイレクト ルーティング](direct-routing-landing-page.md)

[ダイレクト ルーティングを計画する](direct-routing-plan.md)