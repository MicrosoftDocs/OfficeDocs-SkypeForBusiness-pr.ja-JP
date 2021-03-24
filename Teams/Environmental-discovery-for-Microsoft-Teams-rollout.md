---
title: 環境の互換性 - Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Skype for Business から Microsoft Teams への旅を計画する場合に、詳しい環境発見を実行する方法について説明します。
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
ms.openlocfilehash: 50c6845eabb56ea270e6eafa699fbba57d0639e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105253"
---
<a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Microsoft Teams の展開に関する環境発見
===================================================

検出は、Microsoft Teams への旅を計画する際に行う最初の重要な手順の 1 つです。

環境の詳細な検出を実行して、現在の状態をよりよく理解し、問題を明らかにしたり、さらにさらに、Teams のロールアウトの実行をブロックする可能性があります。

## <a name="discovery-questionnaire"></a>検出に関するアンケート

以下のサンプル アンケートでは、組織が Teams の通話プラン機能を使用した電話会議と電話システムの展開を成功に向け準備ができていることを確認する一連の質問について説明します。

既存のコラボレーション インフラストラクチャと Microsoft 365 または Office 365 組織、ネットワーク、エンドポイント、運用、導入と準備に関連する事項はすべて、環境調査アンケートの一部として含まれています。

アンケートは複数のセクションに分かれ、いくつかの主要な領域での Teams 展開に対する組織の準備を確認します。 プロジェクト チームと一緒に、必要な情報を可能な限り詳細に提供し、計画作業を容易に行います。

> [!TIP]
> 最初に、質問票を Microsoft Word 文書にコピーします。 すべての質問に回答し、移動に合わせすべての詳細をキャプチャします。

<a name="project-team"></a>プロジェクト チーム
---

Teams ロールアウト プロジェクトの主要な関係者に関する詳細情報を取り込む。 1 人のユーザーがプロジェクト全体で複数の役割を果たします。

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
> | ビジネス ユニット のリード | | | |

<a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365 または Office 365 組織の詳細
---

このアンケートでは、アクティブな Microsoft 365 または Office 365 組織を使用することを強くお勧めします。 Microsoft 365 または Office 365 組織をまだアクティブ化または構成していない場合は、「一ビジネス向け [Microsoft 365](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)のセットアップを計画する」を参照してください。

次の表を使用して、Microsoft 365 または Office 365 組織に関する情報を取得します。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | 実稼働の Microsoft 365 をメモする<br/>または Office 365 の組織名と ID を入力する<br/>を選択します。 その他の情報がある場合<br/>に関連付けられている 1 つ以上のテナント<br/>組織の場合は、すべての ID をメモします。 | テナント名: <br/>テナント ID:| |
> | どの地域にテナントが展開されていますか?| | |
> | Microsoft 365 または <br/>Office 365 テナントを使用します。 マルチテナントの場合 <br/>または Dedicated? | <input type="checkbox"> マルチテナント<br/> <input type="checkbox"> 専用 | |
> | 現在使用中の Microsoft Online 製品はどれですか? <br/>各ユーザーに対して有効になっているユーザーの数に注意してください <br/>サービスを [コメント] 列に表示します。 | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox"> Skype for Business <br/>&nbsp; &nbsp; &nbsp;オンライン <br/> <input type="checkbox"> Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox"> OneDrive for Business <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> その他| |
> | Skype for で有効になっているライセンス レベル <br/>Business Online ユーザーの場合 | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | ユーザー数 <br/>各 SKU に対して次の条件を実行します。 |
> | 現在の Active Directory フォレストとは <br/>環境の機能レベル <br/>複数のフォレストがある場合は、詳細を書き込む <br/>を選択します。 | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox"> Windows Server 2012 <br/> <input type="checkbox"> Windows Server 2012 R2 <br/> <input type="checkbox"> Windows Server 2016| |
> | ディレクトリに何を使ってるの? <br/>今すぐ同期しますか? |<input type="checkbox"> 同期なし (クラウドのみ) <br/> <input type="checkbox"> Azure Active Directory <br/>&nbsp; &nbsp; &nbsp;接続 <br/> <input type="checkbox"> その他 (以下で指定します) <br/>&nbsp;&nbsp; &nbsp;コメント列)。| |
> | フェデレーション ID は現在展開されていますか? <br/>(Active Directory フェデレーション サービスまたは <br/>サード パーティ) | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | フェデレーション ID を使用している場合は、 <br/>フェデレーション インフラストラクチャの場合 | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> サード パーティ フェデレーション <br/>&nbsp;&nbsp; &nbsp; ゲートウェイ (詳細を書き込む) <br/>&nbsp;&nbsp; &nbsp; をクリックします)。 | |
> | 現在アクティブな Microsoft 365 を維持している場合<br/>または Office 365 テナントの SMTP/SIP ドメインは、 <br/>対象ユーザーがテナントに関連付けられている場合 | <input type="checkbox"> N/A – Microsoft 365 または<br/>&nbsp;&nbsp; &nbsp;Office 365 テナントが配置されている <br/> <input type="checkbox"> いいえ、ユーザーの SMTP/SIP <br/>&nbsp;&nbsp; &nbsp; ドメインが関連付けされていない <br/>&nbsp;&nbsp; &nbsp; テナントが <br/>&nbsp;&nbsp; &nbsp;Microsoft 365 または Office 365<br/> <input type="checkbox"> はい、ユーザーの SMTP/SIP <br/>&nbsp;&nbsp; &nbsp; ドメインが関連付けられている <br/>&nbsp;&nbsp; &nbsp; 既存のテナントが <br/>&nbsp;&nbsp; &nbsp;Microsoft 365 または Office 365 | |
> | ユーザーの UPN はプライマリ SMTP アドレスと一致しますか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います <br/> <input type="checkbox"> 矛盾 | |

<a name="existing-collaboration-platform-summary"></a>既存のコラボレーション プラットフォームの概要
---

次の表を使用して、既存のコラボレーション プラットフォームの展開に関する情報を取得します。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Microsoft Teams は展開されていますか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | Skype for Business は展開されていますか? <br/>オンプレミスとハイブリッドの展開の場合は、 <br/>バージョンと累積的な更新プログラム (CU) に注意してください <br/>[コメント] 列の詳細を確認します。 | <input type="checkbox"> はい、Microsoft 365 または <br/>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox"> はい、ハイブリッド (次の場合) <br/>&nbsp;&nbsp; &nbsp;Microsoft 365 または <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> はい、オンプレミス <br/> <input type="checkbox"> はい、オンライン、専用 <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> あり、ホスト、専用 <br/>&nbsp;&nbsp; &nbsp; (サード パーティ) <br/> <input type="checkbox"> あり、ホスト、共有 <br/>&nbsp;&nbsp; &nbsp; (サード パーティ) <br/> <input type="checkbox"> いいえ、その他 | |
> | Exchange は展開されていますか? <br/>オンプレミスとハイブリッドの展開の場合は、 <br/>バージョンと CU の詳細をコメントにメモする <br/>列に入力します。 | <input type="checkbox"> はい、Microsoft 365 <br/> <input type="checkbox"> はい、ハイブリッド (次の場合) <br/>&nbsp;&nbsp; &nbsp;Microsoft 365 または <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> はい、オンプレミス <br/> <input type="checkbox"> はい、オンライン、専用 <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> あり、ホスト、専用 <br/>&nbsp;&nbsp; &nbsp; (サード パーティ) <br/> <input type="checkbox"> あり、ホスト、共有 <br/>&nbsp;&nbsp; &nbsp; (サード パーティ) <br/> <input type="checkbox"> いいえ、その他 | |
> | SharePoint は展開されていますか? <br/>オンプレミスとハイブリッドの展開の場合は、 <br/>バージョンと CU の詳細をコメントにメモする <br/>列に入力します。 | <input type="checkbox"> はい、Microsoft 365 <br/> <input type="checkbox"> はい、ハイブリッド (次の場合) <br/>&nbsp;&nbsp; &nbsp;Microsoft 365 または <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> はい、オンプレミス <br/> <input type="checkbox"> はい、オンライン、専用 <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> あり、ホスト、専用 <br/>&nbsp;&nbsp; &nbsp; (サード パーティ) <br/> <input type="checkbox"> あり、ホスト、共有 <br/>&nbsp;&nbsp; &nbsp; (サード パーティ) <br/> <input type="checkbox"> いいえ、その他 | |
> | OneDrive for Business は展開されていますか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | 他のサード パーティプラットフォームを展開している場合 <br/>今すぐご利用ですか? その場合は、 <br/>これらのプラットフォームと、使用の詳細については、 <br/>コメント列。 | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Slack <br/> <input type="checkbox"> その他 (以下で指定します) <br/>&nbsp;&nbsp; &nbsp;コメント列)。 | ユーザー数: <br/>詳細:|
> | これらのサード パーティからユーザーを移動する予定ですか? <br/>プラットフォームから Teams へ | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | 現在のテレフォニーと会議ソリューションとは <br/>この取り組みの対象であるユーザーの場合は、 | | |
> | ダイレクト ルーティング [をサポートする SBC を展開](./direct-routing-plan.md#supported-session-border-controllers-sbcs) している場合 <br/>この取り組みの対象であるオフィスの場合は、 はい<br/>[コメント] 列に詳細をメモします。| <input type="checkbox"> うん <br/> <input type="checkbox"> 違います ||

<a name="collaboration-platform-deployment-details"></a>コラボレーション プラットフォームの展開の詳細
---

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (該当する場合)

該当する場合は、次のサンプル テーブルを使用して、Teams の展開の詳細をキャプチャします。 Teams を展開していない場合は、このセクションをスキップします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | どの種類のユーザーが Teams で有効になっていますか? | <input type="checkbox"> 組織内のすべてのユーザー <br/> <input type="checkbox"> 特定のユーザー/ユーザー グループ <br/>&nbsp;&nbsp; &nbsp; (コメント列で指定します)。 ||
> | 使用されている Teams の機能とモダリティ | <input type="checkbox"> チャネルベースの会話 <br/> <input type="checkbox"> プライベート チャット <br/> <input type="checkbox"> ゲスト アクセス <br/> <input type="checkbox"> チャネル会議 <br/> <input type="checkbox"> プライベート会議 <br/> <input type="checkbox"> プライベート通話 <br/> <input type="checkbox"> アドホック チャネル meetup <br/> <input type="checkbox"> 会議のビデオ <br/> <input type="checkbox"> 会議での画面共有 <br/> <input type="checkbox"> 電話会議 <br/><input type="checkbox"> アプリケーション (アプリ)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox">タブ<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">ボット <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">コネクタ<br/><input type="checkbox"> カスタム クラウド ストレージの統合 <br/>&nbsp;&nbsp; &nbsp;Dropbox、Box、ShareFile、Google <br/>&nbsp;&nbsp; &nbsp;Drive, Egnyte <br/> <input type="checkbox"> チャネルメールの統合 <br/> <input type="checkbox"> その他 (コメント列で指定します)。 | |
> | Teams に展開したアプリケーション | | |
> | 特定的に禁止している Teams の機能はありますか? <br/>[はい] の場合は、[コメント] 列の詳細をメモします。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います ||
> | どの Teams クライアントが使用されていますか? | <input type="checkbox"> Web <br/> <input type="checkbox"> Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | チームを作成するためのアクセス許可があるのは誰ですか? | <input type="checkbox"> 組織内のすべてのユーザー <br/>&nbsp;&nbsp; &nbsp; (これは既定の設定です) <br/> <input type="checkbox"> 特定のユーザー <br/>&nbsp;&nbsp; &nbsp; (コメント列で指定します)。 | |
> | Teams でセキュリティおよびコンプライアンスの機能を使用していますか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (該当する場合)

該当する場合は、次のサンプル 表を使用して、Skype for Business Online 展開の詳細をキャプチャします。 Skype for Business Online 展開を展開していない場合は、このセクションをスキップします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Skype で有効になっているユーザーの種類 <br/>for Business Online? | <input type="checkbox"> 組織内のすべてのユーザー <br/> <input type="checkbox"> 特定のユーザー/ユーザー グループ <br/>&nbsp;&nbsp; &nbsp; (コメント列で指定します)。 | |
> | 現在のモダリティと機能 <br/>現在ご利用ですか? | <input type="checkbox"> インスタント メッセージングとプレゼンス (IM/P)<br/> <input type="checkbox"> 会議 <br/> <input type="checkbox"> フェデレーション <br/> <input type="checkbox"> 会議の記録 <br/> <input type="checkbox"> Microsoft 電話会議 <br/> <input type="checkbox"> サードパーティ電話会議 (注)<br/>&nbsp;&nbsp; &nbsp; コメント列の詳細を確認します)。 <br/> <input type="checkbox"> 通話プラン (旧 PSTN 通話) <br/> <input type="checkbox"> 組織の自動応答 <br/> <input type="checkbox"> 通話キュー | |
> | Skype for を具体的にブロックしましたか? <br/>Business Online の機能 <br/>[はい] の場合は、[コメント] 列の詳細をメモします。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | 使用している方法、または使用する予定の方法 <br/>電話システム (以前のクラウド PBX) を <br/>PSTN? <br/>適用する項目をすべて選択します。 | <input type="checkbox"> 通話プラン (旧 PSTN 通話) <br/> <input type="checkbox"> オンプレミス PSTN 接続 <br/>&nbsp;&nbsp; &nbsp; (既存の Skype for <br/>&nbsp;&nbsp; &nbsp;Business 2015 または Lync Server <br/>&nbsp;&nbsp; &nbsp; 2013 展開) <br/> <input type="checkbox"> オンプレミス PSTN 接続 <br/>&nbsp;&nbsp; &nbsp; (Cloud Connector を使用) | |
> | マイクロソフトに移行した電話番号はありますか? <br/>これは通話プランと音声に適用されます <br/>会議機能。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |

### <a name="skype-for-business-on-premises-if-applicable"></a>オンプレミスの Skype for Business (該当する場合)

該当する場合は、次のサンプル 表を使用して、Skype for Business 展開の詳細をキャプチャします。 Skype for Business をオンプレミスに展開していない場合は、このセクションをスキップします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Lync または Skype for Business のバージョン <br/> 現在はオンプレミスに展開されていますか? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> Skype for Business Server 2015 <br/> <input type="checkbox"> Skype for Business Server 2019 <br/><input type="checkbox"> Skype for Business Cloud Connector <br/>&nbsp;&nbsp; &nbsp;エディション | |
> | Skype for Business Online とのハイブリッドは構成されていますか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | この環境は 3 番目にホストされ、管理されていますか <br/>パーティー? [はい] の場合は、 <br/>コメント列。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | 現在使用されているモダリティと機能 <br/>本日は。 | <input type="checkbox"> インスタント メッセージングとプレゼンス (IM/P) <br/> <input type="checkbox"> 会議 <br/> <input type="checkbox"> フェデレーション <br/> <input type="checkbox"> 会議の記録 <br/> <input type="checkbox"> 常設チャット/グループ チャット <br/> <input type="checkbox"> Microsoft 電話会議 <br/>&nbsp;&nbsp; &nbsp; (以前のダイヤルイン会議) を開き、 <br/>&nbsp;&nbsp; &nbsp; オンプレミスの Lync Server または <br/>&nbsp;&nbsp; &nbsp;Skype for Business の展開 <br/> <input type="checkbox"> サードパーティ電話会議 <br/>&nbsp;&nbsp; &nbsp; (コメントの詳細に注意してください) <br/>&nbsp;&nbsp; &nbsp; 列に表示されます)。 <br/> <input type="checkbox"> エンタープライズ VoIPを使用する場合 <br/>&nbsp; &nbsp; &nbsp;PSTN 接続 <br/> <input type="checkbox"> 通話プラン (旧 PSTN 通話) <br/>&nbsp;&nbsp; &nbsp;Skype for Business Online とのハイブリッド | |
> | 展開済みの Edge Server のバージョンはいくつですか? | <input type="checkbox"> Office Communications Server 2007 "R1" <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> Skype for Business Server 2015 <br/> <input type="checkbox"> Skype for Business Server 2019| |
> | Lync または Skype for Business Edge をお持ちですか? <br/>複数のデータセンターに展開されている場合 <br/>[はい] の場合は、[コメント] 列の詳細をメモします。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | Edge の役割が現在提供しているサービスを選択します。 | <input type="checkbox"> 外部ユーザー アクセス (企業ユーザー) <br/> <input type="checkbox"> リモート ユーザー アクセス (匿名) <br/>&nbsp;&nbsp; &nbsp; 外部会議の参加者) <br/> <input type="checkbox"> フェデレーション <br/> <input type="checkbox"> メディア リレー | |
> | 次の音声通話機能の中から、どの機能を使うのですか? <br/>現在依存関係がありますか? <br/>コメントに追加の依存関係をメモする <br/>列に入力します。 | <input type="checkbox"> 取り込み中オプション <br/> <input type="checkbox"> コール パーク <br/> <input type="checkbox"> 通話の受け取りまたはグループ通話の受け取り <br/> <input type="checkbox"> 一般的な地域の電話、または "ホットデスク" <br/> <input type="checkbox"> 応答グループまたはハント グループ <br/> <input type="checkbox"> 共有線の外観 <br/> <input type="checkbox"> プライベート行 <br/> <input type="checkbox"> ボイスメール <br/> <input type="checkbox"> 仕事で通話する <br/> <input type="checkbox"> 緊急電話番号または情報番号 <br/>&nbsp;&nbsp; &nbsp; (911、811、411) <br/> <input type="checkbox"> 内線番号のダイヤル <br/> <input type="checkbox"> 自動応答 <br/> <input type="checkbox"> サブスクライバー アクセス <br/> <input type="checkbox"> アナログ デバイス <br/> <input type="checkbox"> FAX <br/> <input type="checkbox"> 発信者番号のマスキングまたは変更 <br/> <input type="checkbox"> 場所ベースのルーティング <br/> <input type="checkbox"> 最小コストルーティング <br/> <input type="checkbox"> 階乗電話 | |

<a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Microsoft 365 および Office 365 サービスへのネットワークとアクセス
---

次の表に、組織のネットワークの詳細と、Microsoft 365 および Office 365 サービスへのユーザーの接続方法 (または接続される方法) を示します。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | ユーザーが移行の対象に入る方法 (または方法) <br/>オフィスで Teams にアクセスしますか? <br/>適用する項目をすべて選択します。 | <input type="checkbox"> ルーティング NAT 接続 <br/> <input type="checkbox"> プロキシ サーバー <br/> <input type="checkbox"> パブリック Wi-Fi <br/> <input type="checkbox"> 管理 (パブリックではない) Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp; (Microsoft ピアリング) ||
> | Microsoft 365 または Office 365 にアクセスするには、<br/>プロキシ サーバーの場合、プロキシをバイパスする方法はありますか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | ExpressRoute は現在使用されていますか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います <br/> <input type="checkbox"> いいえ。ただし、計画中です | |
> | ネットワーク準備評価を実行しましたか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | 接続時に VPN を使用する必要がある場合 <br/>企業のリソースをリモートで使用する場合 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | VPN が使用されている場合、Teams トラフィックを <br/>Microsoft 365 および Office 365 サービスに直接アクセスする VPN | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | お使いのネットワークは QoS をサポートしていますか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | Teams のオーディオ トラフィックとビデオ トラフィックに優先順位を付け可能 <br/>高品質のエクスペリエンスを実現するには、次の方法を使用します。 | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | 地域内のすべての場所にインターネット出口を設定し、 <br/>または、インターネット出口は地域全体で一元管理されていますか? | <input type="checkbox"> インターネットへの地域アクセス <br/> <input type="checkbox"> 一元的にアクセスして、 <br/>&nbsp;&nbsp; &nbsp; インターネット | |

<a name="endpoints"></a>エンドポイント
---

次の表を使用して、使用されているクライアントとエンドポイントの詳細をキャプチャします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | ユーザーが使用しているデスクトップ OS は何ですか? | <input type="checkbox"> Windows XP <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox"> Windows 8 <br/> <input type="checkbox"> Windows 10 <br/> <input type="checkbox"> Mac ([コメント] 列でバージョンを指定します)。 <br/> <input type="checkbox"> Linux ([コメント] 列で配布を指定します)。 <br/><input type="checkbox"> その他 ([コメント] 列の詳細に注意してください)。 | |
> | 展開されているMicrosoft Officeバージョン <br/>をこれらのデバイスに接続しますか? | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox"> Office for Mac 2011 <br/> <input type="checkbox"> Office for Mac 2016 <br/> <input type="checkbox"> その他 ([コメント] 列の詳細に注意してください)。 | |
> | どのOffice展開テクノロジが使用されていますか <br/>を選択してください。 | <input type="checkbox"> MSI <br/> <input type="checkbox"> クイック実行 | |
> | 許可およびサポートされるモバイルの機能 <br/>プラットフォームが使用されていますか? <br/>適用する項目をすべて選択します。 | <input type="checkbox"> Windows <br/> <input type="checkbox"> モバイル <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> その他 ([コメント] 列の詳細に注意してください)。 | |
> | モバイル デバイスはどのように提供されますか? <br/>適用する項目をすべて選択します。 | <input type="checkbox"> 企業のデバイス <br/> <input type="checkbox"> 自分のデバイスを持ち込む | |
> | ユーザーがアクセスに現在使用しているデバイス <br/>音声および会議サービス <br/>(ハンドセット、ヘッドセット、電話、ビデオ)? | | |

<a name="operations"></a>操作
---

次の表を使用して、環境の運用面の詳細を取得します。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Lync Server の操作モデルは何か <br/>Skype for Business Server、Microsoft 365 展開、 <br/>またはOffice 365 の展開を今すぐ行いますか? | | |
> | 現在のサポートの取り決めについて、 <br/>Lync Server、Skype for Business Server、Microsoft 365、 <br/>または Office 365? | | |
> | 複数の国または地域に展開する場合は、 <br/>国/地域ごとに独自の IT/テレフォニーがある場合 <br/>一緒に作業するスタッフ、またはこれを一本的に管理しますか? | <input type="checkbox"> 地域の操作とサポート <br/> <input type="checkbox"> 一元管理された操作とサポート | |
> | 通話の品質の方法論に従っていますか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います | |
> | 個人またはチームを <br/>コラボレーション プラットフォームの品質チャンピオンの役割 <br/>お使いですか? | <input type="checkbox"> うん <br/> <input type="checkbox"> 違います ||
> | Lync Server と Skype for を監視する方法 <br/>Business Server、Microsoft 365 の展開、または <br/>Office 365 の展開 | | |
> | 通話品質の問題を経験しましたか? | <input type="checkbox"> うん<br/> <input type="checkbox"> 違います | |
> | トレーニングを提供する方法と時間 <br/>新しいサービスと機能に関するヘルプデスク | | |

<a name="adoption-and-readiness"></a>導入と準備
---

次の表を使用して、自分の組織での現在の導入と準備状況を記録してください。

>
> | 質問 | 回答 | コメント |
> |---|---|---|
> | 現在アクティブに使用されている <br/>Skype for Business? | **__** % アクティブ ユーザーと有効なユーザーの合計 | |
> | 組織でどのように使用されていますか <br/>Skype for Business? | 1 対 1 の会話 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">IM <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">通話 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">共有<br/> 会議 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">会議<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">共有<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">通話 | |
> | 組織にユーザーの導入がある場合 <br/>変更管理チームの場合は、 | <input type="checkbox"> うん<br/> <input type="checkbox"> 違います | |
> | 現在、テクノロジの成功を測定する方法 <br/>Skype for Business のようなロールアウト | | |
> | ユーザー ベースに占める割合 <br/>Skype for Business の導入 | | |
> | Skype for Business についてのユーザーの感想を教えてください。 | <input type="checkbox"> よし <br/> <input type="checkbox"> ニュートラル <br/> <input type="checkbox"> 悪い | |
> | ロールアウトについて最もよく説明する次の中から <br/>Skype for Business で使用される戦略 <br/>展開 | <input type="checkbox"> 広範な範囲: メール キャンペーン <br/>&nbsp;&nbsp; &nbsp; トレーニングへのリンク <br/> <input type="checkbox"> 展開: 広範な範囲に加えて、さまざまな機能 <br/>&nbsp;&nbsp; &nbsp; に対する認識キャンペーン (ポスター、 <br/>&nbsp;&nbsp; &nbsp; イベント、チャンピオン)、トレーニング <br/>&nbsp;&nbsp; &nbsp; (ビデオ、ユーザー ガイド、対人) <br/> <input type="checkbox"> カスタマイズ: 拡張、および対象指定 <br/>&nbsp;&nbsp; &nbsp; ユーザー別のメッセージングとトレーニング <br/> <input type="checkbox"> その他 <br/>&nbsp;&nbsp; &nbsp; ([コメント] 列の詳細に注意してください)。 | |