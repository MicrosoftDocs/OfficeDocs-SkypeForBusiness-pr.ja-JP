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
description: オンプレミステレフォニー インフラストラクチャをTeams 電話システムに接続するように Microsoft Direct Routing を構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b72a51008e2a5d55b57809ab5e8ae989f4ed3ec7
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518579"
---
# <a name="configure-direct-routing"></a>ダイレクト ルーティングを構成する

ダイレクト ルーティングを使用すると、オンプレミスのテレフォニー インフラストラクチャをMicrosoft Teamsに接続できます。 この記事では、サポートされているオンプレミス セッション ボーダー コントローラー (SBC) をダイレクト ルーティングに接続するために必要な大まかな手順と、ダイレクト ルーティングを使用して公衆交換電話網 (PSTN) に接続するようにTeamsユーザーを構成する方法について説明します。 この記事は、関連する記事にリンクして詳細を確認します。  

直接ルーティングが組織に適したソリューションであるかどうかの詳細については、「 [PSTN 接続オプション](pstn-connectivity.md)」を参照してください。 前提条件とデプロイの計画については、「 [ダイレクト ルーティングの計画](direct-routing-plan.md)」を参照してください。

この記事で説明する手順を完了するには、管理者が PowerShell コマンドレットについて理解している必要があります。 PowerShell の使用の詳細については、「[Windows PowerShell用にコンピューターをセットアップする」を参照してください](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。 

これらの記事の手順を実行する前に、SBC ベンダーが推奨するように SBC が既に構成されていることを確認することをお勧めします。 

- [AudioCodes のデプロイに関するドキュメント](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle デプロイのドキュメント](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [リボン 通信の展開に関するドキュメント](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode) の展開に関するドキュメント](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Metaswitch デプロイのドキュメント](https://www.metaswitch.com/products/core-network/perimeta-sbc)

サポートされている SBC の完全な一覧については、「 [ダイレクト ルーティング用に認定されたセッション ボーダー コントローラー](direct-routing-border-controllers.md)」を参照してください。

電話システムを構成し、ユーザーがダイレクト ルーティングを使用できるようにするには、次の手順に従います。 

- **手順 1.** [電話システムで SBC をConnectし、接続を検証する](direct-routing-connect-the-sbc.md)
- **手順 2.** [ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする](direct-routing-enable-users.md)
- **手順 3.** [通話ルーティングを構成する](direct-routing-voice-routing.md)
- **手順 4.** [数値を別の形式に変換する](direct-routing-translate-numbers.md) 

複数のテナントに対して SBC を構成する場合は、「複数のテナントの [SBC を構成する](direct-routing-sbc-multiple-tenants.md)」も参照してください。


## <a name="related-topics"></a>関連項目

[音声ソリューションを計画する](cloud-voice-landing-page.md)

[PSTN 接続オプション](pstn-connectivity.md)

[ダイレクト ルーティングを計画する](direct-routing-plan.md)