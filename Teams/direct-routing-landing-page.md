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
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 直接ルーティングの詳細と、必要な展開についての意思決定については、こちらを参照してください。
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c988670a17a9ba2f803c11740d97404de52d4d5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497304"
---
# <a name="phone-system-direct-routing"></a>電話システムのダイレクト ルーティング

[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。 Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。 [会議および電話会議](deploy-meetings-microsoft-teams-landing-page.md)を展開した可能性があります。 これで、クラウド音声のワークロードを追加する準備ができました。電話システムのダイレクトルーティングを使用して、PSTN (公衆交換電話網) 接続用の独自のテレフォニーキャリアを使用することにしました。 直接ルーティングを使用すると、ほぼすべてのテレフォニーキャリアで電話システムを使うことができます。

この記事では、組織のニーズに基づいて、直接ルーティングを行う場合の主要な展開と、検討する必要があるその他の考慮事項について説明します。 また、Microsoft のクラウド ボイス サービスの詳細については、「[Microsoft Teams でのクラウド ボイス](cloud-voice-landing-page.md)」を参照してください。

## <a name="learn-more-about-direct-routing"></a>直接ルーティングの詳細については、こちらを参照してください

次の記事では、電話システムのダイレクトルーティングを構成して使用する方法について詳しく説明します。 直接ルーティングを構成するには、PSTN ルーティングの設計を理解している必要があります。 直接ルーティングを計画して構成する方法については、以下の記事を参照してください。

- [ダイレクト ルーティングを計画する](direct-routing-plan.md) 
- [ダイレクト ルーティングを構成する](direct-routing-configure.md)
- [ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト](direct-routing-border-controllers.md)
- [ダイレクト ルーティングの監視とトラブルシューティング](direct-routing-monitor-and-troubleshoot.md)

さらに、必要に応じて、次の記事も参照してください。

-  [複数のテナントにセッション ボーダー コントローラーを構成する](direct-routing-sbc-multiple-tenants.md)
-  [ダイレクト ルーティングに移行する](direct-routing-migrating.md)
-  [PSTN 接続を使用するハイブリッド環境でのユーザー アカウント](direct-routing-user-accounts-in-a-hybrid-environment.md)
- 直接ルーティングの詳細については、次のセッションをご覧ください。 [Microsoft Teams での直接ルーティング](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

これは、直接ルーティングについて考慮するべき主要な決定事項です。 

|確認事項|アクション |
| :------------|:-------|
|どのユーザーが直接ルーティングを有効にしますか? | 詳細については、「 [ユーザーが直接ルーティングサービスを有効にする](direct-routing-configure.md)」を参照してください。 |
直接ルーティングのために必要なライセンスはありますか? | 詳細については、「 [ライセンスとその他の要件](direct-routing-plan.md#licensing-and-other-requirements)」を参照してください。
|||

### <a name="session-border-controller-sbc-considerations"></a>セッションボーダーコントローラー (SBC) に関する考慮事項

直接ルーティングでは、独自のセッションボーダーコントローラー (SBC) を直接電話システムに接続します。  認定された SBCs の一覧については、 [サポートされているセッション境界コントローラー](direct-routing-border-controllers.md)を参照してください。

|確認事項|アクション |
|:------------|:-------|
| SBCs はどこで展開されますか? | 詳細については、「[直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。 | 
複数のテナントがある場合 | 詳細については、「 [複数のテナントのセッション境界コントローラーを構成](direct-routing-sbc-multiple-tenants.md)する」を参照してください。|
|||

### <a name="voice-routing-considerations"></a>音声ルーティングに関する考慮事項

特定の SBCs への通話をルーティングするように電話システムを構成する必要があります。

|確認事項|アクション |
|:------------|:-------|
| 作成する必要がある音声ルーティングポリシー、PSTN 使用状況、および音声ルート | 音声ルーティング情報については、「 [ボイスルーティングを構成する](direct-routing-configure.md)」をご覧ください。
| 定義した音声ルーティングポリシーにはどのユーザーが割り当てられますか。 | 「 [音声ルーティングを構成する](direct-routing-configure.md)」の例を参照してください。 |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>TeamsUpgradePolicy を使用して、チームクライアントで着信通話を確実に行う

直接ルーティングは、Microsoft Teams でのみサポートされます。 直接ルーティングを使用して PSTN 通話を受信するには、TeamsUpgradePolicy を構成して、Teams で確実に着信を受信できるようにする必要があります。 ユーザーは、チーム専用モードである必要があります。これには、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てることができます。 

|確認事項|アクション |
|:------------|:-------|
|チーム専用モードの意味を教えてください。 | 詳細については、「 [Skype For business で Teams を使用する組織向けの移行と相互運用性](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)に関するガイダンス」を参照してください。|
|||

## <a name="additional-deployment-considerations"></a>その他の展開に関する考慮事項

組織のニーズと構成に基づいて、次のことを検討してください。

| 確認事項| アクション |
| :------------|:-------|
| ハイブリッド接続が構成されている既存の Skype for Business Server 展開がありますか? |  ハイブリッド環境でのユーザーアカウントのプロビジョニングと管理の方法については、「 [PSTN 接続を使用したハイブリッド環境のユーザーアカウント](direct-routing-user-accounts-in-a-hybrid-environment.md)」を参照してください。| 
| 通話プランまたは Skype for Business オンプレミス環境からの直接ルーティングに移行していますか? | 既存の環境からの直接ルーティングへの移行の詳細については、「 [ダイレクトルーティングへの移行](direct-routing-migrating.md)」を参照してください。 |
|||
