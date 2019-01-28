---
title: 電話システムの直接のルーティング
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: crowe
search.appverid: MET150
description: 直接ルーティングのランディング ・ ページ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 47c2e225090c6d58db2184113dd43995847f9409
ms.sourcegitcommit: 3a0b90af8eb3c10579b9eea7837c60a19a577881
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2019
ms.locfileid: "29595416"
---
# <a name="phone-system-direct-routing"></a>電話システムの直接のルーティング

[開始](get-started-with-teams-quick-start.md)が完了しました。 出てくるチーム[チャット、チーム、チャネル、& のアプリケーション](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体にわたって。 かもしれません[& 会議の会議](deploy-meetings-microsoft-teams-landing-page.md)を導入しました。 クラウド音声のワークロードを追加する準備が整いましたし、公衆交換電話網 (PSTN) 接続の電話システムの直接のルーティングを使用してテレフォニーのキャリアを使用すると判断しました。 直接ルーティングでは、ほぼすべてのテレフォニーのキャリアで電話システムを使用できます。

この資料を構成すること、組織のニーズに基づいて直接ルーティングの場合と同様に考慮すべき事項の中核となる配置の決定について説明します。  マイクロソフトのクラウドの音声サービスの詳細については[マイクロソフトのチームでのクラウドの音声](cloud-voice-landing-page.md)を参照することもあります。

## <a name="learn-more-about-direct-routing"></a>直接ルーティングの詳細については


次の資料を構成して、電話システムの直接のルーティングを使用の詳細を提供します。 直接ルーティングを構成するには、PSTN のルーティングの設計を理解する必要があります。 すべて計画し、直接ルーティングを構成する方法を理解するのにはこれらの記事の内容を読み取る必要があります。

- [ダイレクト ルーティングを計画する](direct-routing-plan.md) 
- [直接ルーティングを構成する](direct-routing-configure.md)
- [ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト](direct-routing-border-controllers.md)
- [監視し、直接ルーティングのトラブルシューティングを行う](direct-routing-monitor-and-troubleshoot.md)

さらに、お客様の要件に応じて次の記事を参照することもできます。

-  [複数のテナントについてセッション ボーダー コントローラーを構成する](direct-routing-sbc-multiple-tenants.md)
-  [直接ルーティングへの移行します。](direct-routing-migrating.md)
-  [PSTN 接続を使用するハイブリッド環境でのユーザー アカウント](direct-routing-user-accounts-in-a-hybrid-environment.md)
- 直接ルーティングの詳細については、次のセッションを監視する:[マイクロソフトのチームに直接ルーティング](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>コアの配置の決定

これらは、直接ルーティングについて検討すべき主要な意思決定です。 


|確認してください。|アクション |
| :------------|:-------|
|ユーザーは有効に直接ルーティングします。 | 詳細については、[ユーザーの直接のルーティング サービスを有効にする](direct-routing-configure.md#enable-users-for-direct-routing-service)を参照してください。 |
直接ルーティングに必要なライセンスがあるか | 詳細については、[使用許諾契約とその他の要件](direct-routing-plan.md#licensing-and-other-requirements)を参照してください。
|||

### <a name="session-border-controller-sbc-considerations"></a>セッション ボーダー コント ローラー (SBC) に関する考慮事項

直接ルーティングでは、電話システムに直接、独自のセッション ボーダー コント ローラー (SBC) を接続します。  認定 SBCs のリストは、[サポートされているセッション ボーダー コント ローラー](direct-routing-border-controllers.md)を参照してください。

|確認してください。|アクション |
|:------------|:-------|
| 場所と方法 SBCs を展開しますか。 | 詳細については、[直接ルーティングの構成](direct-routing-configure.md)を参照してください。 | 
複数のテナントがあるか | 詳細については、[複数のテナントのセッション ボーダー コント ローラーの構成](direct-routing-sbc-multiple-tenants.md)を参照してください。|
|||

### <a name="voice-routing-considerations"></a>音声ルーティングに関する考慮事項

特定の半角英数字に呼び出しをルーティングする電話システムを構成する必要があります。

|確認してください。|アクション |
|:------------|:-------|
| どのような音声ルーティング ポリシー、PSTN 使用法、およびボイス ルートが必要を作成しますか。 | 音声のルーティング情報は、[音声ルーティングの構成](direct-routing-configure.md#configure-voice-routing)を参照してください。
| 音声ルーティング ポリシーを定義するユーザーが割り当てられますか。 | [音声ルーティングの構成](direct-routing-configure.md#configure-voice-routing)の例を参照してください。 |
|||

### <a name="calling-and-interop-policies"></a>呼び出し元および相互運用機能のポリシー

直接ルーティングは、マイクロソフトのチームでのみサポートされます。 開始、または直接ルーティングでは、PSTN の呼び出しを受信、チームでの着信呼び出しが受信されるように必要なポリシーを構成する必要があります。 チームのみのモードのユーザーを構成するか、優先する呼び出し元クライアントとして、TeamsCallingPolicy と、TeamsInteropPolicy を割り当てることによってチームを構成すると、優先するクライアントの呼び出しのチームを設定するのにはユーザーを構成できます。

|確認してください。|アクション |
|:------------|:-------|
|呼び出しの優先するクライアントとしてチームを設定する方法 | 詳細については、[マイクロソフトのチームを優先設定は、ユーザーのクライアントを呼び出す](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users)を参照してください。|
|||

## <a name="additional-deployment-considerations"></a>追加の配置に関する考慮事項

、次を考慮することが、組織のニーズに基づいて構成します。

| 確認してください。| アクション |
| :------------|:-------|
| ビジネス サーバー配置の既存の Skype ハイブリッド接続が構成されていますか。 |  ハイブリッド環境でユーザー アカウントを準備する方法を理解し、管理するには、 [PSTN への接続を持つハイブリッド環境でユーザー アカウント](direct-routing-user-accounts-in-a-hybrid-environment.md)を参照してください。| 
| 移行して直接ルーティングの計画を呼び出すと、Skype のビジネス、オンプレミス環境にからでしょうか。 | 直接ルーティングするのには既存の環境からの移行について理解を深めるには、[直接ルーティングへの移行](direct-routing-migrating.md)を参照してください。 |
|||
