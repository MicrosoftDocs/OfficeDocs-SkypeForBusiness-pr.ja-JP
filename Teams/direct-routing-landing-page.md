---
title: ダイレクト ルーティング
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: filippse
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: ダイレクト ルーティングを使用したTeams 電話システムについて説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fe723ee8347ea96c87cb0a9e85f7794c5e50e01
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518709"
---
# <a name="direct-routing"></a>ダイレクト ルーティング

[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。 Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。 [会議および電話会議](deploy-meetings-microsoft-teams-landing-page.md)を展開した可能性があります。 音声ワークロードを追加する準備ができました。これで、ダイレクト ルーティングで電話システムを使用して、公衆交換電話網 (PSTN) 接続に独自のテレフォニー通信事業者を使用することにしました。 ダイレクト ルーティングを使用すると、実質的に任意のテレフォニーキャリアで電話システムを使用できます。

この記事では、組織のニーズに基づいて、ダイレクト ルーティングの主要な展開に関する決定に加え、検討する必要がある追加の考慮事項について説明します。 Microsoft の音声サービスの詳細については、「 [音声ソリューションの計画](cloud-voice-landing-page.md) 」も参照してください。

## <a name="learn-more-about-direct-routing"></a>ダイレクト ルーティングの詳細

次の記事では、ダイレクト ルーティングの構成と使用について詳しく説明します。 ダイレクト ルーティングを構成するには、PSTN ルーティングの設計について理解する必要があります。 ダイレクト ルーティングを計画および構成する方法については、次のすべての記事を参照してください。

- [ダイレクト ルーティングを計画する](direct-routing-plan.md) 
- [ダイレクト ルーティングを構成する](direct-routing-configure.md)
- [ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト](direct-routing-border-controllers.md)
- [ダイレクト ルーティングの監視とトラブルシューティング](direct-routing-monitor-and-troubleshoot.md)

さらに、要件に応じて、次の記事を読む必要があります。

-  [複数のテナントにセッション ボーダー コントローラーを構成する](direct-routing-sbc-multiple-tenants.md)
-  [ダイレクト ルーティングに移行する](direct-routing-migrating.md)
-  [PSTN 接続を使用するハイブリッド環境でのユーザー アカウント](direct-routing-user-accounts-in-a-hybrid-environment.md)
- ダイレクト ルーティング: [Microsoft Teamsでのダイレクト ルーティング](https://aka.ms/teams-direct-routing)の詳細については、次のセッションを参照してください。

## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

これらは、ダイレクト ルーティングで考慮すべき主要な決定事項です。 

|確認事項|アクション |
| :------------|:-------|
|ダイレクト ルーティングを有効にするユーザーはどれですか? | 詳細については、「 [ダイレクト ルーティング サービスのユーザーを有効にする」を](direct-routing-configure.md)参照してください。 |
ダイレクト ルーティングに必要なライセンスはありますか? | 詳細については、「 [ライセンスとその他の要件」を](direct-routing-plan.md#licensing-and-other-requirements)参照してください。
|||

### <a name="session-border-controller-sbc-considerations"></a>セッション ボーダー コントローラー (SBC) に関する考慮事項

ダイレクト ルーティングでは、独自のセッション ボーダー コントローラー (SBC) を電話システムに直接接続します。 認定された SBC の一覧については、「 [サポートされているセッション ボーダー コントローラー](direct-routing-border-controllers.md)」を参照してください。

|確認事項|アクション |
|:------------|:-------|
| SBC を展開する場所と方法 | 詳細については、「[ダイレクト ルーティングの構成」を参照してください](direct-routing-configure.md)。 | 
複数のテナントはありますか? | 詳細については、「 [複数のテナントのセッション ボーダー コントローラーを構成する](direct-routing-sbc-multiple-tenants.md)」を参照してください。|
|||

### <a name="voice-routing-considerations"></a>音声ルーティングに関する考慮事項

呼び出しを特定の SBC にルーティングするように電話システムを構成する必要があります。

|確認事項|アクション |
|:------------|:-------|
| どのような音声ルーティング ポリシー、PSTN 使用法、音声ルートを作成する必要がありますか? | 音声ルーティングの情報については、「 [音声ルーティングの構成」を](direct-routing-configure.md)参照してください。
| どのユーザーが、定義する音声ルーティング ポリシーに割り当てられますか? | [音声ルーティングの構成](direct-routing-configure.md)の例を参照してください。 |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>TeamsUpgradePolicy を使用して、着信呼び出しがTeams クライアントに到着することを確認する

ダイレクト ルーティングは、Microsoft Teamsでのみサポートされます。 ダイレクト ルーティングを介して PSTN 通話を受信するには、Teamsで着信呼び出しを確実に受信するように TeamsUpgradePolicy を構成する必要があります。 ユーザーは TeamsOnly モードである必要があります。ユーザーは TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てることで実行できます。 

|確認事項|アクション |
|:------------|:-------|
|TeamsOnly モードとはどういう意味ですか? | 詳細については、「[TeamsとSkype for Businessを使用する組織の移行と相互運用性に関するガイダンス」を](./migration-interop-guidance-for-teams-with-skype.md)参照してください。|
|||


