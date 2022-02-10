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
description: ダイレクト ルーティングのTeams 電話システムについて説明します。
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

[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。 Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。 [会議および電話会議](deploy-meetings-microsoft-teams-landing-page.md)を展開した可能性があります。 これで音声ワークロードを追加する準備が整い、直接ルーティングで 電話システム を使用して、公衆交換電話網 (PSTN) 接続に独自のテレフォニー 通信事業者を使用することを決定しました。 ダイレクト ルーティングでは、事実上すべてのテレフォニー 電話システムを使用できます。

この記事では、直接ルーティングの主要なデプロイの決定と、組織のニーズに基づいて考慮する必要があるその他の考慮事項について説明します。 Microsoft の音声サービス [の詳細については、「音声ソリューションを](cloud-voice-landing-page.md) 計画する」も参照してください。

## <a name="learn-more-about-direct-routing"></a>ダイレクト ルーティングの詳細を確認する

次の記事では、ダイレクト ルーティングの構成と使用の詳細について説明します。 直接ルーティングを構成するには、PSTN ルーティング設計について理解する必要があります。 直接ルーティングを計画および構成する方法を理解するには、次のすべての記事を読む必要があります。

- [ダイレクト ルーティングを計画する](direct-routing-plan.md) 
- [ダイレクト ルーティングを構成する](direct-routing-configure.md)
- [ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト](direct-routing-border-controllers.md)
- [ダイレクト ルーティングの監視とトラブルシューティング](direct-routing-monitor-and-troubleshoot.md)

さらに、要件に応じて次の記事を読む必要がある場合があります。

-  [複数のテナントにセッション ボーダー コントローラーを構成する](direct-routing-sbc-multiple-tenants.md)
-  [ダイレクト ルーティングに移行する](direct-routing-migrating.md)
-  [PSTN 接続を使用するハイブリッド環境でのユーザー アカウント](direct-routing-user-accounts-in-a-hybrid-environment.md)
- ダイレクト ルーティングの詳細については、次のセッションをご [Microsoft Teams覧](https://aka.ms/teams-direct-routing)ください。

## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

これらは、ダイレクト ルーティングに関して考慮すべき主要な決定です。 

|確認事項|アクション |
| :------------|:-------|
|ダイレクト ルーティングを有効にするユーザー | 詳細については、「ダイレクト ルーティング サービスの [ユーザーを有効にする」を参照してください](direct-routing-configure.md)。 |
ダイレクト ルーティングに必要なライセンスはありますか。 | 詳細については、「ライセンスと他 [の要件」を参照してください](direct-routing-plan.md#licensing-and-other-requirements)。
|||

### <a name="session-border-controller-sbc-considerations"></a>セッション ボーダー コントローラー (SBC) に関する考慮事項

直接ルーティングを使用すると、独自のセッション ボーダー コントローラー (SBC) を直接接続して、電話システム。 認定された SBC の一覧については、「サポートされているセッション ボーダー コントローラー [」を参照してください](direct-routing-border-controllers.md)。

|確認事項|アクション |
|:------------|:-------|
| SBC をデプロイする場所と方法 | 詳細については、「ダイレクト ルーティングの [構成」を参照してください。](direct-routing-configure.md) | 
複数のテナントがありますか? | 詳細については、「複数のテナント [のセッション ボーダー コントローラーを構成する」を参照してください](direct-routing-sbc-multiple-tenants.md)。|
|||

### <a name="voice-routing-considerations"></a>音声ルーティングに関する考慮事項

呼び出しを特定の SBC にルーティング電話システムを構成する必要があります。

|確認事項|アクション |
|:------------|:-------|
| 作成する必要がある音声ルーティング ポリシー、PSTN 使用法、音声ルート | 音声ルーティングの情報については、「音声ルーティングの [構成」を参照してください](direct-routing-configure.md)。
| 定義する音声ルーティング ポリシーに割り当てられるユーザー | 「音声ルーティングの構成」 [の例を参照してください](direct-routing-configure.md)。 |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>TeamsUpgradePolicy を使用して、Teamsクライアントに着信通話が着信する

ダイレクト ルーティングは、直接ルーティングがサポートされているMicrosoft Teams。 直接ルーティングを介して PSTN 通話を受信するには、TeamsUpgradePolicy を構成して、着信通話が着信通話で受信Teams。 ユーザーは TeamsOnly モードである必要があります。このモードでは、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てる必要があります。 

|確認事項|アクション |
|:------------|:-------|
|TeamsOnly モードとはどういう意味ですか? | 詳細については、「移行と相互運用性に関するガイダンス」を参照して、Teams[を使用Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)。|
|||


