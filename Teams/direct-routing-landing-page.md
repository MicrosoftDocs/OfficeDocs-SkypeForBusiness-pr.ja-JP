---
title: 電話システムのダイレクト ルーティング
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 構成、必要なコア デプロイの決定、音声ルーティングに関する考慮事項など、ダイレクト ルーティングの詳細について説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4298cc34122d6b3bb7d9f9bb1f8698aec864426f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122211"
---
# <a name="phone-system-direct-routing"></a>電話システムのダイレクト ルーティング

[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。 Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。 [会議および電話会議](deploy-meetings-microsoft-teams-landing-page.md)を展開した可能性があります。 これでクラウド音声ワークロードを追加する準備が整い、電話システム ダイレクト ルーティングを使用して、公衆交換電話網 (PSTN) 接続に独自のテレフォニー 通信事業者を使用することを決定しました。 ダイレクト ルーティングでは、事実上すべてのテレフォニー 電話システムを使用できます。

この記事では、直接ルーティングの主要なデプロイの決定と、組織のニーズに基づいて考慮する必要がある追加の考慮事項について説明します。 また、Microsoft のクラウド ボイス サービスの詳細については、「[Microsoft Teams でのクラウド ボイス](cloud-voice-landing-page.md)」を参照してください。

## <a name="learn-more-about-direct-routing"></a>ダイレクト ルーティングの詳細を確認する

次の記事では、ダイレクト ルーティングの構成と使用の詳細電話システム説明します。 直接ルーティングを構成するには、PSTN ルーティング設計について理解する必要があります。 直接ルーティングを計画および構成する方法については、次のすべての記事を参照してください。

- [ダイレクト ルーティングを計画する](direct-routing-plan.md) 
- [ダイレクト ルーティングを構成する](direct-routing-configure.md)
- [ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト](direct-routing-border-controllers.md)
- [ダイレクト ルーティングの監視とトラブルシューティング](direct-routing-monitor-and-troubleshoot.md)

さらに、要件に応じて、次の記事を読む必要があります。

-  [複数のテナントにセッション ボーダー コントローラーを構成する](direct-routing-sbc-multiple-tenants.md)
-  [ダイレクト ルーティングに移行する](direct-routing-migrating.md)
-  [PSTN 接続を使用するハイブリッド環境でのユーザー アカウント](direct-routing-user-accounts-in-a-hybrid-environment.md)
- ダイレクト ルーティングの詳細については、次のセッションをご[Microsoft Teams覧](https://aka.ms/teams-direct-routing)ください。

## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

これらは、ダイレクト ルーティングに関して考慮すべき主要な決定です。 

|確認事項|アクション |
| :------------|:-------|
|ダイレクト ルーティングを有効にするユーザー | 詳細については、「ダイレクト ルーティング サービスの [ユーザーを有効にする」を参照してください](direct-routing-configure.md)。 |
ダイレクト ルーティングに必要なライセンスはありますか。 | 詳細については、「ライセンスと他 [の要件」を参照してください](direct-routing-plan.md#licensing-and-other-requirements)。
|||

### <a name="session-border-controller-sbc-considerations"></a>セッション ボーダー コントローラー (SBC) に関する考慮事項

直接ルーティングを使用すると、独自のセッション ボーダー コントローラー (SBC) を直接接続して、電話システム。  認定された SBC の一覧については、「サポートされているセッション ボーダー コントローラー [」を参照してください](direct-routing-border-controllers.md)。

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

ダイレクト ルーティングは、直接ルーティングがサポートされているMicrosoft Teams。 直接ルーティングを介して PSTN 通話を受信するには、TeamsUpgradePolicy を構成して、着信通話が着信通話で受信Teams。 ユーザーは、TeamsUpgradePolicy Teams UpgradeToTeams" インスタンスを割り当て、ユーザーを [のみ] モードにする必要があります。 

|確認事項|アクション |
|:------------|:-------|
|[のみ] Teamsとはどういう意味ですか? | 詳細については、「移行と相互運用性に関する[Skype for Business Teamsガイダンス](./migration-interop-guidance-for-teams-with-skype.md)」を参照してください。|
|||

## <a name="additional-deployment-considerations"></a>その他のデプロイに関する考慮事項

組織のニーズと構成に基づいて、次の点を考慮してください。

| 確認事項| アクション |
| :------------|:-------|
| ハイブリッド接続が構成された既存Skype for Business Serverデプロイはありますか。 |  ハイブリッド環境のユーザー アカウントがどのようにプロビジョニングおよび管理されるのかについては、「PSTN 接続を使用したハイブリッド環境のユーザー アカウント」 [を参照してください](direct-routing-user-accounts-in-a-hybrid-environment.md)。| 
| 通話プランまたはオンプレミス環境から直接ルーティングに移行Skype for Business移行していますか。 | 既存の環境からのダイレクト ルーティングへの移行の詳細については、「ダイレクト ルーティングへの移行 [」を参照してください](direct-routing-migrating.md)。 |
|||