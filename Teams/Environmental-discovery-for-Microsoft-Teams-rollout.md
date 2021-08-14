---
title: 環境の互換性 - Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 新しい環境から環境への道のりを計画する場合に、詳細なSkype for Business実行Microsoft Teams。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d0c5339fd2782ffaa268705aee161256c9aa04e4
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234312"
---
# <a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>新しいロールアウトの環境Microsoft Teams検出

検出は、開発プロセスを計画するときに実行する最初の重要な手順の 1 Microsoft Teams。

環境の詳細な検出を実行して、現在の状態をよりよく理解し、問題を明らかにしたり、さらに、Teams ロールアウトの実行をブロックする可能性があります。

## <a name="discovery-questionnaire"></a>検出アンケート

以下のサンプル アンケートでは、組織が Teams の通話プラン機能を使用して電話会議と 電話システム を正常に展開する準備ができていることを確認する一連の質問について説明します。

既存のコラボレーション インフラストラクチャと Microsoft 365 または Office 365 組織、ネットワーク、エンドポイント、運用、導入および準備に関する事項はすべて、環境検出アンケートの一部として含まれています。

アンケートは複数のセクションに分かれ、組織が複数の主要な領域に展開Teams準備を確認します。 プロジェクト チームと一緒に、計画作業を容易にするために、必要な情報を可能な限り詳細に提供します。

> [!TIP]
> 最初に、アンケートを別のドキュメントにMicrosoft Wordできます。 すべての質問に回答し、移動中にすべての詳細をキャプチャしてみてください。

### <a name="project-team"></a>Project チーム

ロールアウト プロジェクトの主要な関係者に関する詳細情報Teams取り込む。 1 人のユーザーがプロジェクト全体で複数の役割を果たします。

> | 役割 | 名前、メール アドレス、電話番号 | 場所、タイム ゾーン | コメント |
> |---|---|---|---|
> | エグゼクティブ スポンサー | | | |
> | プロジェクト リード | | | |
> | コラボレーション リード/アーキテクト | | | |
> | コンサルタント | | | |
> | プロジェクト マネージャー | | | |
> | 変更管理/導入の専門家 | | | |
> | ネットワーク リード | | | |
> | セキュリティ リード | | | |
> | テレフォニー リード | | | |
> | デスクトップ リード | | | |
> | サポート/ヘルプ デスク リード | | | |
> | 展開リード | | | |
> | サービス所有者 | | | |
> | 施設リード | | | |
> | ビデオ チーム リード | | | |
> | ビジネス ユニットのリード | | | |

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365またはOffice 365の詳細

このアンケートを使用する場合は、アクティブなMicrosoft 365またはOffice 365組織を作成することを強くお勧めします。 組織のライセンス認証または構成をまだ行っていないMicrosoft 365組織Office 365、「一Microsoft 365のセットアップを[計画する」を参照してください](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)。

次の表を使用して、組織または組織のMicrosoft 365をOffice 365します。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | 実稼働環境のMicrosoft 365<br/>または Office 365の名前と ID<br/>を選択します。 その他の情報がある場合<br/>に関連付けられている 1 つ以上のテナント<br/>すべての ID を書き込む必要があります。 | テナント名: <br/>テナント ID:| |
> | どのリージョンにテナントがデプロイされていますか。| | |
> | これらのデータの種類をMicrosoft 365 <br/>Office 365テナントを選択します。 マルチテナントか <br/>または Dedicated? | <input type="checkbox"> マルチテナント<br/> <input type="checkbox"> 専用 | |
> | 現在使用中の Microsoft Online 製品はどれですか? <br/>各ユーザーに対して有効になっているユーザーの数に注意してください。 <br/>[コメント] 列の [サービス] を選択します。 | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype for Business <br/>&nbsp; &nbsp; &nbsp;オンライン <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePointオンライン <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox">Yammer <br/> <input type="checkbox"> その他| |
> | ユーザーに対して有効になっているライセンス レベルSkype <br/>Business Online ユーザー | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | ユーザー数 <br/>各 SKU に対して次の条件を実行します。 |
> | 現在の Active Directory フォレストとは <br/>環境内の機能レベル <br/>複数のフォレストがある場合は、詳細を書き込む <br/>[コメント] 列に表示されます。 | <input type="checkbox">WindowsServer 2000 <br/> <input type="checkbox">WindowsServer 2003 <br/> <input type="checkbox">WindowsServer 2008<br/> <input type="checkbox">WindowsServer 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012R2 <br/> <input type="checkbox">Windows Server 2016| |
> | ディレクトリに使用している機能 <br/>同期を今すぐ行う場合 |<input type="checkbox"> 同期なし (クラウドのみ) <br/> <input type="checkbox">Azure Active Directory <br/>&nbsp; &nbsp; &nbsp;接続 <br/> <input type="checkbox"> その他 (以下で指定します。 <br/>&nbsp;&nbsp; &nbsp;[コメント] 列)。| |
> | フェデレーション ID は現在展開されていますか? <br/>(Active Directory フェデレーション サービスまたは <br/>サード パーティ) | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | フェデレーション ID を使用している場合は、 <br/>フェデレーション インフラストラクチャ | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox"> サード パーティのフェデレーション <br/>&nbsp;&nbsp; &nbsp; ゲートウェイ (詳細を書き込む) <br/>&nbsp;&nbsp; &nbsp; [コメント] 列に表示されます)。 | |
> | 現在アクティブな状態を維持しているMicrosoft 365<br/>または Office 365、 は の SMTP/SIP ドメインです。 <br/>テナントに関連付けられている対象ユーザー | <input type="checkbox">N/A – no Microsoft 365 or<br/>&nbsp;&nbsp; &nbsp; Office 365テナントを作成する <br/> <input type="checkbox"> いいえ、ユーザーの SMTP/SIP <br/>&nbsp;&nbsp; &nbsp; ドメインが関連付けされていない <br/>&nbsp;&nbsp; &nbsp; すべてのテナントを含む <br/>&nbsp;&nbsp; &nbsp; Microsoft 365またはOffice 365<br/> <input type="checkbox"> はい、ユーザーの SMTP/SIP <br/>&nbsp;&nbsp; &nbsp; ドメインが関連付けられている <br/>&nbsp;&nbsp; &nbsp; 既存のテナントを含む <br/>&nbsp;&nbsp; &nbsp; Microsoft 365またはOffice 365 | |
> | ユーザー UPN はプライマリ SMTP アドレスと一致しますか。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います <br/> <input type="checkbox"> 一貫性がない | |

## <a name="existing-collaboration-platform-summary"></a>既存のコラボレーション プラットフォームの概要

次の表を使用して、既存のコラボレーション プラットフォームのデプロイに関する情報を取得します。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Microsoft Teams は展開されていますか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | Skype for Business は展開されていますか? <br/>オンプレミスとハイブリッドのデプロイの場合は、 <br/>バージョンと累積的な更新プログラム (CU) を書き込む <br/>[コメント] 列の詳細を確認します。 | <input type="checkbox">はい、Microsoft 365 または <br/>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox"> はい、ハイブリッド (と <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 または <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> はい、オンプレミス <br/> <input type="checkbox"> はい、オンライン、専用 <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> はい、ホスト、専用 <br/>&nbsp;&nbsp; &nbsp; (サード パーティ) <br/> <input type="checkbox"> はい、ホスト、共有 <br/>&nbsp;&nbsp; &nbsp; (サード パーティ) <br/> <input type="checkbox"> いいえ、その他 | |
> | Exchange は展開されていますか? <br/>オンプレミスとハイブリッドのデプロイの場合は、 <br/>バージョンと CU の詳細をコメントに書き込む <br/>列。 | <input type="checkbox">はい、Microsoft 365 <br/> <input type="checkbox"> はい、ハイブリッド (と <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 または <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> はい、オンプレミス <br/> <input type="checkbox"> はい、オンライン、専用 <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> はい、ホスト、専用 <br/>&nbsp;&nbsp; &nbsp; (サード パーティ) <br/> <input type="checkbox"> はい、ホスト、共有 <br/>&nbsp;&nbsp; &nbsp; (サード パーティ) <br/> <input type="checkbox"> いいえ、その他 | |
> | SharePoint は展開されていますか? <br/>オンプレミスとハイブリッドのデプロイの場合は、 <br/>バージョンと CU の詳細をコメントに書き込む <br/>列。 | <input type="checkbox">はい、Microsoft 365 <br/> <input type="checkbox"> はい、ハイブリッド (と <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 または <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> はい、オンプレミス <br/> <input type="checkbox"> はい、オンライン、専用 <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> はい、ホスト、専用 <br/>&nbsp;&nbsp; &nbsp; (サード パーティ) <br/> <input type="checkbox"> はい、ホスト、共有 <br/>&nbsp;&nbsp; &nbsp; (サード パーティ) <br/> <input type="checkbox"> いいえ、その他 | |
> | デプロイOneDrive for Businessですか。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | 他のサード パーティプラットフォームがデプロイされていますか <br/>今日使用していますか? その場合は、 <br/>これらのプラットフォームと、 <br/>[コメント] 列。 | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Slack <br/> <input type="checkbox"> その他 (以下で指定します。 <br/>&nbsp;&nbsp; &nbsp;[コメント] 列)。 | ユーザー数: <br/>詳細:|
> | これらのサード パーティからユーザーを移動する予定ですか? <br/>プラットフォームをTeams。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | 現在のテレフォニーと会議ソリューションとは <br/>このイニシアティブの対象であるユーザーの数。 | | |
> | 直接ルーティング [をサポートする SBC がデプロイ](./direct-routing-plan.md#supported-session-border-controllers-sbcs) されていますか <br/>このイニシアティブの対象であるオフィスの場合は、 [はい] の場合は、<br/>[コメント] 列の詳細をメモします。| <input type="checkbox"> うん <br/> <input type="checkbox"> 違います ||

## <a name="collaboration-platform-deployment-details"></a>コラボレーション プラットフォームのデプロイの詳細

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (該当する場合)

該当する場合は、以下のサンプル 表を使用してTeamsデプロイの詳細をキャプチャします。 デプロイしていない場合は、このTeamsスキップしてください。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | どの種類のユーザーが Teams で有効になっていますか? | <input type="checkbox"> 組織内のすべてのユーザー <br/> <input type="checkbox"> 特定のユーザー/ユーザー グループ <br/>&nbsp;&nbsp; &nbsp; ([コメント] 列でを指定します)。 ||
> | どのTeamsやモダリティが使用されていますか? | <input type="checkbox"> チャネルベースの会話 <br/> <input type="checkbox"> プライベート チャット <br/> <input type="checkbox"> ゲスト アクセス <br/> <input type="checkbox"> チャネル会議 <br/> <input type="checkbox"> プライベート会議 <br/> <input type="checkbox"> プライベート通話 <br/> <input type="checkbox"> アドホック チャネル meetup <br/> <input type="checkbox"> 会議のビデオ <br/> <input type="checkbox"> 会議での画面共有 <br/> <input type="checkbox"> 電話会議 <br/><input type="checkbox"> アプリケーション (アプリ)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox">タブ<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">ボット <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">コネクタ<br/><input type="checkbox"> カスタム クラウド ストレージの統合 <br/>&nbsp;&nbsp; &nbsp; Dropbox、Box、ShareFile、Google <br/>&nbsp;&nbsp; &nbsp;ドライブ、Egnyte <br/> <input type="checkbox"> チャネルメールの統合 <br/> <input type="checkbox"> その他 ([コメント] 列で指定します)。 | |
> | デプロイしたアプリケーションは何Teams? | | |
> | 特定的に禁止している Teams の機能はありますか? <br/>[はい] の場合は、[コメント] 列の詳細をメモします。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います ||
> | どの Teams クライアントが使用されていますか? | <input type="checkbox"> Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox">Windowsモバイル | |
> | チームを作成するためのアクセス許可があるのは誰ですか? | <input type="checkbox"> 組織内のすべてのユーザー <br/>&nbsp;&nbsp; &nbsp; (これは既定の設定です) <br/> <input type="checkbox"> 特定のユーザー <br/>&nbsp;&nbsp; &nbsp; ([コメント] 列でを指定します)。 | |
> | Teams でセキュリティおよびコンプライアンスの機能を使用していますか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (該当する場合)

該当する場合は、次のサンプル 表を使用して、Skype for Business Online デプロイの詳細をキャプチャします。 オンライン デプロイをデプロイしていないSkype for Business、このセクションをスキップしてください。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | ユーザーに対して有効になっているユーザーの種類Skype <br/>Business Online の場合 | <input type="checkbox"> 組織内のすべてのユーザー <br/> <input type="checkbox"> 特定のユーザー/ユーザー グループ <br/>&nbsp;&nbsp; &nbsp; ([コメント] 列でを指定します)。 | |
> | 現在どのようなモダリティと特徴が使用されていますか <br/>現在使用されていますか? | <input type="checkbox"> インスタント メッセージングとプレゼンス (IM/P)<br/> <input type="checkbox"> 会議 <br/> <input type="checkbox"> フェデレーション <br/> <input type="checkbox"> 会議の記録 <br/> <input type="checkbox"> Microsoft 電話会議 <br/> <input type="checkbox"> サード パーティの電話会議 (注)<br/>&nbsp;&nbsp; &nbsp; [コメント] 列の詳細)。 <br/> <input type="checkbox"> 通話プラン (旧 PSTN 通話) <br/> <input type="checkbox"> 組織の自動応答 <br/> <input type="checkbox"> キューの呼び出し | |
> | 特定のアプリケーションをSkypeしましたか? <br/>Business Online の機能 <br/>[はい] の場合は、[コメント] 列の詳細をメモします。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | 使用している方法または使用する予定の方法 <br/>(電話システムクラウド PBX) に接続する <br/>PSTN? <br/>適用する項目をすべて選択します。 | <input type="checkbox"> 通話プラン (旧 PSTN 通話) <br/> <input type="checkbox"> オンプレミス PSTN 接続 <br/>&nbsp;&nbsp; &nbsp; (既存のソリューションをSkype) <br/>&nbsp;&nbsp; &nbsp;Business 2015 または Lync Server <br/>&nbsp;&nbsp; &nbsp; 2013 デプロイ) <br/> <input type="checkbox"> オンプレミス PSTN 接続 <br/>&nbsp;&nbsp; &nbsp; (Cloud Connector を使用) | |
> | マイクロソフトに移行した電話番号はありますか? <br/>これは通話プランと音声に適用されます。 <br/>会議機能。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business (該当する場合)

該当する場合は、次のサンプル 表を使用してSkype for Businessデプロイの詳細をキャプチャします。 オンプレミスにデプロイしていない場合Skype for Businessこのセクションをスキップします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Lync または Lync のバージョンSkype for Business <br/> 現在はオンプレミスにデプロイされていますか? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 <br/><input type="checkbox">Skype for BusinessCloud Connector <br/>&nbsp;&nbsp; &nbsp;エディション | |
> | Skype for Business Online とのハイブリッドは構成されていますか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | この環境は 3 番目の環境によってホストおよび管理されていますか <br/>party? [はい] の場合は、 <br/>[コメント] 列。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | 現在使用されているモダリティと特徴 <br/>本日は。 | <input type="checkbox"> インスタント メッセージングとプレゼンス (IM/P) <br/> <input type="checkbox"> 会議 <br/> <input type="checkbox"> フェデレーション <br/> <input type="checkbox"> 会議の記録 <br/> <input type="checkbox"> 常設チャット/グループ チャット <br/> <input type="checkbox"> Microsoft 電話会議 <br/>&nbsp;&nbsp; &nbsp; (以前のダイヤルイン会議) <br/>&nbsp;&nbsp; &nbsp; オンプレミスの Lync Server または <br/>&nbsp;&nbsp; &nbsp; Skype for Businessデプロイ <br/> <input type="checkbox"> サード パーティの電話会議 <br/>&nbsp;&nbsp; &nbsp; (コメントの詳細に注意してください) <br/>&nbsp;&nbsp; &nbsp; column.) <br/> <input type="checkbox">エンタープライズ VoIPを使用する場合 <br/>&nbsp; &nbsp; &nbsp;PSTN 接続 <br/> <input type="checkbox"> 通話プラン (旧 PSTN 通話) <br/>&nbsp;&nbsp; &nbsp;ハイブリッドと Skype for Business Online | |
> | 展開済みの Edge Server のバージョンはいくつですか? | <input type="checkbox">OfficeCommunications Server 2007 "R1" <br/> <input type="checkbox">OfficeCommunications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019| |
> | Lync または Skype for Business Edge をお持ちですか <br/>複数のデータセンターにデプロイされていますか? <br/>[はい] の場合は、[コメント] 列の詳細をメモします。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | Edge ロールが現在提供しているサービスを選択します。 | <input type="checkbox"> 外部ユーザー アクセス (企業ユーザー) <br/> <input type="checkbox"> リモート ユーザー アクセス (匿名) <br/>&nbsp;&nbsp; &nbsp; 外部会議の参加者) <br/> <input type="checkbox"> フェデレーション <br/> <input type="checkbox"> メディア リレー | |
> | 次の音声通話機能のどちらを使用する <br/>現在依存関係がありますか? <br/>コメントに追加の依存関係をメモする <br/>列。 | <input type="checkbox"> 取り込み中のオプション <br/> <input type="checkbox"> コール パーク <br/> <input type="checkbox"> 集荷またはグループ通話の集荷を呼び出す <br/> <input type="checkbox"> 一般的なエリアの電話、または "ホット デスク" <br/> <input type="checkbox"> 応答グループまたはハント グループ <br/> <input type="checkbox"> 共有線の外観 <br/> <input type="checkbox"> プライベート行 <br/> <input type="checkbox"> ボイスメール <br/> <input type="checkbox"> 仕事で通話する <br/> <input type="checkbox"> 緊急電話番号または情報番号 <br/>&nbsp;&nbsp; &nbsp; (911、811、411) <br/> <input type="checkbox"> 内線番号のダイヤル <br/> <input type="checkbox"> 自動応答 <br/> <input type="checkbox"> サブスクライバーアクセス <br/> <input type="checkbox"> アナログ デバイス <br/> <input type="checkbox"> FAX <br/> <input type="checkbox"> 発信者番号のマスクまたは変更 <br/> <input type="checkbox"> 場所ベースのルーティング <br/> <input type="checkbox"> 最小コストのルーティング <br/> <input type="checkbox"> エレベーターの電話 | |

## <a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>ネットワークとサービスへのMicrosoft 365アクセスOffice 365サービス

次の表を使用して、組織のネットワークの詳細と、ユーザーが他のサービスやサービスに接続Microsoft 365取得Office 365します。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | 移行の対象ユーザーの方法 (または方法) <br/>オフィスTeamsにアクセスできますか? <br/>適用する項目をすべて選択します。 | <input type="checkbox"> ルーティング NAT 接続 <br/> <input type="checkbox"> プロキシ サーバー <br/> <input type="checkbox"> パブリック Wi-Fi <br/> <input type="checkbox"> マネージド (パブリックではない) Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp; (Microsoft ピアリング) ||
> | アクセスがMicrosoft 365またはOffice 365を使用している場合は、<br/>プロキシ サーバー。プロキシをバイパスする方法はありますか。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | ExpressRoute は現在使用されていますか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います <br/> <input type="checkbox"> いいえ。ただし、計画中です | |
> | ネットワーク準備評価を実行しましたか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | 接続時に VPN を使用する必要があるユーザー <br/>企業リソースをリモートで使用する場合 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | VPN が使用されている場合、トラフィックTeamsから除外できます。 <br/>サービスに直接Microsoft 365アクセスOffice 365 VPN。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | お使いのネットワークは QoS をサポートしていますか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | 音声トラフィックとビデオ トラフィックTeams優先順位を付け可能 <br/>高品質のエクスペリエンスを実現するには、 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | リージョン内のすべての場所にインターネットエグレスを設定し、 <br/>または、インターネット送信はリージョン全体で一元化されていますか。 | <input type="checkbox"> インターネットへの地域アクセス <br/> <input type="checkbox"> に対する一元的なアクセス <br/>&nbsp;&nbsp; &nbsp; internet | |

## <a name="endpoints"></a>エンドポイント

次の表を使用して、使用されているクライアントとエンドポイントの詳細をキャプチャします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | ユーザーが使用しているデスクトップ OS は何ですか? | <input type="checkbox">WindowsXP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac ([コメント] 列でバージョンを指定します)。 <br/> <input type="checkbox"> Linux ([コメント] 列でディストリビューションを指定します)。 <br/><input type="checkbox"> その他 ([コメント] 列の詳細に注意してください)。 | |
> | デプロイされているMicrosoft Officeバージョン <br/>これらのデバイスに接続する場合は、 | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office for Mac 2011 <br/> <input type="checkbox">Office for Mac 2016 <br/> <input type="checkbox"> その他 ([コメント] 列の詳細に注意してください)。 | |
> | どのOfficeテクノロジが使用されていますか <br/>お客様の組織で | <input type="checkbox"> MSI <br/> <input type="checkbox"> クイック実行 | |
> | 許可およびサポートされているモバイルは何か <br/>使用されているプラットフォーム <br/>適用する項目をすべて選択します。 | <input type="checkbox">Windows <br/> <input type="checkbox"> モバイル <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> その他 ([コメント] 列の詳細に注意してください)。 | |
> | モバイル デバイスはどのように提供されますか? <br/>適用する項目をすべて選択します。 | <input type="checkbox"> 企業デバイス <br/> <input type="checkbox"> 自分のデバイスを持ち込む | |
> | ユーザーが現在アクセスに使用しているデバイス <br/>音声および会議サービス <br/>(ハンドセット、ヘッドセット、電話、ビデオ)? | | |

## <a name="operations"></a>操作

次の表を使用して、環境の運用面の詳細をキャプチャします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Lync Server の運用モデルは何か。 <br/>Skype for Business Server、Microsoft 365デプロイ、 <br/>または現在Office 365デプロイを開始しますか? | | |
> | 現在のサポートの配置の概要を説明できます。 <br/>Lync Server、Skype for Business Server、Microsoft 365、 <br/>または Office 365? | | |
> | 複数の国または地域にデプロイする場合は、 <br/>国/地域ごとに独自の IT/テレフォニーが用意されていますか。 <br/>使用するスタッフ、または一般に管理されますか。 | <input type="checkbox"> 地域での操作とサポート <br/> <input type="checkbox"> 一元化された操作とサポート | |
> | 通話の品質の方法論に従っていますか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | 個人またはチームを <br/>コラボレーション プラットフォームの品質チャンピオン ロール <br/>使用中ですか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います ||
> | Lync Server を監視する方法、Skypeする方法 <br/>Business Server、Microsoft 365デプロイ、または <br/>Office 365する場合 | | |
> | 通話品質の問題を経験しましたか? | <input type="checkbox"> うん<br/> <input type="checkbox"> 違います | |
> | トレーニングを提供する方法と時間 <br/>新しいサービスと機能に関するヘルプデスク | | |

## <a name="adoption-and-readiness"></a>導入と準備

次の表を使用して、自分の組織での現在の導入と準備状況を記録してください。

>
> | 質問 | 回答 | コメント |
> |---|---|---|
> | 現在アクティブに使用されているのは何か <br/>Skype for Business? | **__** % アクティブ ユーザーと有効なユーザーの合計 | |
> | 組織でどのように使用されていますか <br/>Skype for Business? | 1 対 1 の会話 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">IM <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">呼び出し <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">共有<br/> 会議 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">会議<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">共有<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">呼び出し | |
> | 組織にユーザーの導入がある場合 <br/>および Change Management チーム | <input type="checkbox"> うん<br/> <input type="checkbox"> 違います | |
> | 現在、テクノロジの成功を測定する方法 <br/>ロールアウト ( Skype for Business? | | |
> | ユーザー ベースの割合 <br/>が採用Skype for Business。 | | |
> | Skype for Business についてのユーザーの感想を教えてください。 | <input type="checkbox"> よし <br/> <input type="checkbox"> ニュートラル <br/> <input type="checkbox"> Bad | |
> | ロールアウトについて最もよく説明する次の中から次の手順を実行します。 <br/>使用する戦略Skype for Business <br/>deployment? | <input type="checkbox"> 広範なリーチ: 電子メール キャンペーン <br/>&nbsp;&nbsp; &nbsp; トレーニングへのリンク <br/> <input type="checkbox"> 拡張: 広範な範囲に加え、さまざまな機能 <br/>&nbsp;&nbsp; &nbsp; 意識向上キャンペーン (ポスター、 <br/>&nbsp;&nbsp; &nbsp; イベント、チャンピオン)、トレーニング <br/>&nbsp;&nbsp; &nbsp; (ビデオ、ユーザー ガイド、対人) <br/> <input type="checkbox"> カスタマイズ: 拡張、および対象指定 <br/>&nbsp;&nbsp; &nbsp; ペルサによるメッセージングとトレーニング <br/> <input type="checkbox"> その他 <br/>&nbsp;&nbsp; &nbsp; ([コメント] 列の詳細に注意してください)。 | |
