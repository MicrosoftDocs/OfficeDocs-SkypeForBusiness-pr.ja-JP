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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft Phone システムのダイレクトルーティングを構成して、オンプレミスのテレフォニーインフラストラクチャを Microsoft Teams に接続する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f12eb67fd63a3d1bbed3ddcd0c4fadce16529083
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904829"
---
# <a name="configure-direct-routing"></a>ダイレクト ルーティングを構成する

Microsoft 電話システムのダイレクトルーティングを使用すると、オンプレミスのテレフォニーインフラストラクチャを Microsoft Teams に接続することができます。 この記事では、サポートされているオンプレミスのセッションボーダーコントローラー (SBC) とダイレクトルーティングを接続するために必要な上位レベルの手順を示します。また、ダイレクトルーティングを使用して公衆交換電話網 (PSTN) に接続するように Teams ユーザーを構成する方法について説明します。 この記事では、詳細について関連する記事へのリンクを示します。  

直接ルーティングが組織の適切なソリューションであるかどうかについては、「[電話システムのダイレクトルーティング](direct-routing-landing-page.md)」を参照してください。 前提条件と展開の計画については、「[直接ルーティングを計画](direct-routing-plan.md)する」を参照してください。

> [!Tip]
> また、次のセッションを見て、直接ルーティングの利点、計画方法、展開方法について学習することもできます。 [Microsoft Teams での直接ルーティング](https://aka.ms/teams-direct-routing)。

この記事で説明されている手順を実行するには、管理者が PowerShell コマンドレットについて理解している必要があります。 PowerShell の使用方法の詳細については、「 [Windows powershell 用にコンピューターをセットアップする](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。 

以下の記事の手順を実行する前に、お客様の sbc が SBC ベンダーの推奨として既に構成されていることを確認することをお勧めします。 

- [AudioCodes の展開に関するドキュメント](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 展開に関するドキュメント](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [リボンの通信展開に関するドキュメント](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE システム (anynode) の展開ドキュメント](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Metaswitch の展開ドキュメント](https://www.metaswitch.com/products/core-network/perimeta-sbc)

サポートされている SBCs の完全な一覧については、「[直接ルーティング用に認定されたセッション境界コントローラーの一覧](direct-routing-border-controllers.md)」をご覧ください。

Microsoft 電話システムを構成し、ユーザーが直接ルーティングを使用できるようにするには、次の手順を実行します。 

- **手順1** [SBC と Microsoft 電話システムを接続して接続を検証する](direct-routing-connect-the-sbc.md)
- **手順2** [ユーザーが直接ルーティング、音声、ボイスメールを使用できるようにする](direct-routing-enable-users.md)
- **手順3** [音声ルーティングを構成する](direct-routing-voice-routing.md)
- **手順4。** [数値を別の形式に変換する](direct-routing-translate-numbers.md) 

複数のテナントに対して SBC を構成する場合は、「[複数のテナントの sbc を構成](direct-routing-sbc-multiple-tenants.md)する」もご覧ください。


## <a name="related-topics"></a>関連項目

[電話システムのダイレクト ルーティング](direct-routing-landing-page.md)

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

