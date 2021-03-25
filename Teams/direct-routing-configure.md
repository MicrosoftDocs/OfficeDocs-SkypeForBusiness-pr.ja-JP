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
description: オンプレミスのテレフォニー インフラストラクチャを Microsoft Teams に接続するために Microsoft Phone System Direct Routing を構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122241"
---
# <a name="configure-direct-routing"></a>ダイレクト ルーティングを構成する

Microsoft Phone System Direct Routing を使用すると、オンプレミスのテレフォニー インフラストラクチャを Microsoft Teams に接続できます。 この記事では、サポートされているオンプレミス セッション ボーダー コントローラー (SBC) を直接ルーティングに接続するために必要な高レベルの手順と、パブリック交換電話ネットワーク (PSTN) に接続するために直接ルーティングを使用する Teams ユーザーを構成する方法について説明します。 この記事では、詳細について関連記事にリンクしています。  

直接ルーティングが組織に適切なソリューションであるかどうかを確認する方法については、「電話システム ダイレクト ルーティング」 [を参照してください](direct-routing-landing-page.md)。 前提条件と展開の計画については、「直接ルーティングを計画する [」を参照してください](direct-routing-plan.md)。

> [!Tip]
> また、次のセッションを見て、直接ルーティングの利点、プランの方法、展開方法について説明します [。Microsoft Teams](https://aka.ms/teams-direct-routing)での直接ルーティング。

この記事で説明する手順を完了するには、管理者は PowerShell コマンドレットに精通している必要があります。 PowerShell の使用の詳細については、「PowerShell を使用するコンピューター [をセットアップする」を](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)Windows PowerShell。 

これらの記事の手順を実行する前に、Microsoft では、SBC ベンダーが推奨するように SBC が既に構成されていることを確認するようにお勧めします。 

- [AudioCodes 展開ドキュメント](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle の展開に関するドキュメント](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [リボンコミュニケーションの展開に関するドキュメント](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode) 展開ドキュメント](https://www.anynode.de/anynode-and-microsoft-teams/)
- [メタスイッチの展開に関するドキュメント](https://www.metaswitch.com/products/core-network/perimeta-sbc)

サポートされている SPC の完全なリストについては、「ダイレクト ルーティング用に認定されたセッション ボーダー コントローラーのリスト [」を参照してください](direct-routing-border-controllers.md)。

Microsoft Phone System を構成し、ユーザーが直接ルーティングを使用するには、次の手順を実行します。 

- **手順 1.** [SBC を Microsoft Phone System に接続し、接続を検証する](direct-routing-connect-the-sbc.md)
- **手順 2.** [直接ルーティング、音声、ボイスメールのユーザーを有効にする](direct-routing-enable-users.md)
- **手順 3.** [音声ルーティングを構成する](direct-routing-voice-routing.md)
- **手順 4.** [数値を別の形式に翻訳する](direct-routing-translate-numbers.md) 

複数のテナントに対して SBC を構成する場合は、「複数のテナントに対して SBC を構成する」も [参照する必要があります](direct-routing-sbc-multiple-tenants.md)。


## <a name="related-topics"></a>関連項目

[電話システムのダイレクト ルーティング](direct-routing-landing-page.md)

[ダイレクト ルーティングを計画する](direct-routing-plan.md)