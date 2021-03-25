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
description: 構成、必要な主要な展開決定、音声ルーティングに関する考慮事項など、ダイレクト ルーティングの詳細について説明します。
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

[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。 Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。 [会議および電話会議](deploy-meetings-microsoft-teams-landing-page.md)を展開した可能性があります。 これで、クラウド 音声ワークロードを追加する準備が整い、電話システム ダイレクト ルーティングを使用して、独自のテレフォニー通信事業者を公衆交換電話網 (PSTN) 接続に使用することを決定しました。 直接ルーティングを使用すると、事実上すべてのテレフォニー通信事業者で電話システムを使用できます。

この記事では、ダイレクト ルーティングの主要な展開決定と、組織のニーズに基づいて検討する必要がある追加の考慮事項について説明します。 また、Microsoft のクラウド ボイス サービスの詳細については、「[Microsoft Teams でのクラウド ボイス](cloud-voice-landing-page.md)」を参照してください。

## <a name="learn-more-about-direct-routing"></a>ダイレクト ルーティングの詳細

電話システム ダイレクト ルーティングの構成と使用の詳細については、次の記事を参照してください。 直接ルーティングを構成するには、PSTN ルーティングの設計を理解する必要があります。 ダイレクト ルーティングを計画および構成する方法については、次のすべての記事をお読みください。

- [ダイレクト ルーティングを計画する](direct-routing-plan.md) 
- [ダイレクト ルーティングを構成する](direct-routing-configure.md)
- [ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト](direct-routing-border-controllers.md)
- [ダイレクト ルーティングの監視とトラブルシューティング](direct-routing-monitor-and-troubleshoot.md)

さらに、要件に応じて、次の記事をお読みになる場合があります。

-  [複数のテナントにセッション ボーダー コントローラーを構成する](direct-routing-sbc-multiple-tenants.md)
-  [ダイレクト ルーティングに移行する](direct-routing-migrating.md)
-  [PSTN 接続を使用するハイブリッド環境でのユーザー アカウント](direct-routing-user-accounts-in-a-hybrid-environment.md)
- 直接ルーティングの詳細については、次のセッションをご覧ください [:Microsoft Teams での直接ルーティング](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

これらは、ダイレクト ルーティングに関して考慮すべき主要な決定です。 

|確認事項|操作 |
| :------------|:-------|
|ダイレクト ルーティングを有効にするユーザー | 詳細については、「ダイレクト ルーティング サービス [でユーザーを有効にする」を参照してください](direct-routing-configure.md)。 |
ダイレクト ルーティングに必要なライセンスはありますか? | 詳細については、「ライセンスと [他の要件」を参照してください](direct-routing-plan.md#licensing-and-other-requirements)。
|||

### <a name="session-border-controller-sbc-considerations"></a>セッション ボーダー コントローラー (SBC) に関する考慮事項

直接ルーティングを使用すると、独自のセッション ボーダー コントローラー (SBC) を電話システムに直接接続できます。  認定された SPC の一覧については、「サポートされるセッション ボーダー コントローラー [」を参照してください](direct-routing-border-controllers.md)。

|確認事項|操作 |
|:------------|:-------|
| SBC を展開する場所と方法 | 詳細については、「ダイレクト ルーティングの [構成」を参照してください。](direct-routing-configure.md) | 
複数のテナントがありますか? | 詳細については、「複数のテナント [のセッション ボーダー コントローラーを構成する」を参照してください](direct-routing-sbc-multiple-tenants.md)。|
|||

### <a name="voice-routing-considerations"></a>音声ルーティングに関する考慮事項

通話を特定の SPC にルーティングするには、電話システムを構成する必要があります。

|確認事項|操作 |
|:------------|:-------|
| 作成する必要がある音声ルーティング ポリシー、PSTN の使用状況、および音声ルート | 音声ルーティングの情報については、「音声ルーティングを [構成する」を参照してください](direct-routing-configure.md)。
| 定義した音声ルーティング ポリシーに割り当てられるユーザー | 「音声ルーティングの構成」の [例を参照してください](direct-routing-configure.md)。 |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>TeamsUpgradePolicy を使用して、着信通話が Teams クライアントに着信する

直接ルーティングは、Microsoft Teams でのみサポートされます。 直接ルーティングを通じて PSTN 通話を受信するには、Teams で着信通話を確実に受信するために TeamsUpgradePolicy を構成する必要があります。 ユーザーは TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当て、Teams Only モードである必要があります。 

|確認事項|操作 |
|:------------|:-------|
|Teams Only モードとは何ですか? | 詳細については、Skype for Business と共に Teams を使用する組織の移行と相互 [運用性のガイダンスを参照してください](./migration-interop-guidance-for-teams-with-skype.md)。|
|||

## <a name="additional-deployment-considerations"></a>展開に関するその他の考慮事項

組織のニーズと構成に基づいて、次の点を考慮してください。

| 確認事項| 操作 |
| :------------|:-------|
| ハイブリッド接続が構成された既存の Skype for Business Server 展開がありますか? |  ハイブリッド環境のユーザー アカウントのプロビジョニングと管理方法については、「PSTN 接続を使用したハイブリッド環境のユーザー アカウント」 [を参照してください](direct-routing-user-accounts-in-a-hybrid-environment.md)。| 
| 通話プランまたは Skype for Business オンプレミス環境から直接ルーティングに移行していますか? | 既存の環境からのダイレクト ルーティングへの移行の詳細については、「ダイレクト ルーティングへの移行 [」を参照してください](direct-routing-migrating.md)。 |
|||