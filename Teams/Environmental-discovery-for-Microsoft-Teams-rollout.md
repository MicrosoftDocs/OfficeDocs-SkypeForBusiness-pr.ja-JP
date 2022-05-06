---
title: 環境の互換性 - Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Skype for BusinessからMicrosoft Teamsまでの道のりを計画するときに、詳細な環境検出を実行する方法。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fdaafeb9042f8b76b40c797109740af5c93ef077
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635051"
---
# <a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Microsoft Teamsロールアウトの環境検出

探索は、Microsoft Teamsへの道のりを計画するときに行う最初の重要な手順の 1 つです。

環境の詳細な検出を実行して、その現在の状態をよりよく理解し、問題を明らかにしたり、Teams ロールアウトの実行に対する可能性のある障害をさらに明らかにしたりします。

## <a name="discovery-questionnaire"></a>検出アンケート

次のサンプル アンケートでは、一連の質問について説明し、組織が電話会議と通話プラン機能を使用して電話システムを正常に展開する準備が整っていることを確認Teams。

既存のコラボレーション インフラストラクチャ、Microsoft 365、Office 365組織、ネットワーク、エンドポイント、運用、導入と準備に関連するすべての事項は、環境検出アンケートの一部として含まれています。

アンケートは複数のセクションに分割され、いくつかの主要な分野でのTeams展開に対する組織の準備状況を確認します。 プロジェクト チームと協力して、必要な情報をできるだけ詳細に提供し、計画アクティビティを容易にします。

> [!TIP]
> まず、アンケートをMicrosoft Wordドキュメントにコピーします。 すべての質問に答えて、すべての詳細をキャプチャします。

### <a name="project-team"></a>Project チーム

Teams ロールアウト プロジェクトの主要な利害関係者に関する詳細情報をキャプチャします。 1 人のユーザーがプロジェクト全体で複数のロールを果たすことができることに注意してください。

> | 役割 | 名前、電子メール アドレス、電話番号 | 場所、タイム ゾーン | 注釈 |
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
> | Business Unit 潜在顧客 | | | |

## <a name="microsoft-365-or-office-365-organization-details"></a>組織の詳細をMicrosoft 365またはOffice 365する

このアンケートに取り組む際は、アクティブなMicrosoft 365またはOffice 365組織を持っていることをお勧めします。 Microsoft 365またはOffice 365組織をまだアクティブ化または構成していない場合は、「[ビジネス向けのMicrosoft 365のセットアップを計画する](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)」を参照してください。

次の表を使用して、Microsoft 365またはOffice 365組織に関する情報をキャプチャします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | 運用環境のMicrosoft 365に注意してください<br/>または組織の名前と ID をOffice 365する<br/>[回答] 列に表示されます。 その他の情報がある場合<br/>に関連付けられている 1 つ以上のテナント<br/>組織で、すべての ID をメモします。 | テナント名: <br/>テナント ID:| |
> | テナントはどのリージョンにデプロイされますか?| | |
> | これらのMicrosoft 365または <br/>テナントをOffice 365します。 Multitenant か <br/>または専用ですか? | <input type="checkbox"> 雑居<br/> <input type="checkbox"> 専用 | |
> | 現在使用中の Microsoft Online 製品はどれですか? <br/>各ユーザーに対して有効になっているユーザーの数に注意してください <br/>[コメント] 列のサービス。 | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype for Business <br/>&nbsp; &nbsp; &nbsp;オンライン <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox">Yammer <br/> <input type="checkbox"> 他| |
> | Skypeに対して有効になっているライセンス レベル <br/>Business Online ユーザー | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | ユーザーの数 <br/>SKU ごとに次の手順を実行します。 |
> | 現在の Active Directory フォレストとは <br/>環境内の機能レベル <br/>複数のフォレストがある場合は、詳細をメモします <br/>[コメント] 列に表示されます。 | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | ディレクトリに使用しているもの <br/>今すぐ同期しますか? |<input type="checkbox"> 同期なし (クラウドのみ) <br/> <input type="checkbox">Azure Active Directory <br/>&nbsp; &nbsp; &nbsp;接続 <br/> <input type="checkbox"> Other (Specify in the <br/>&nbsp;&nbsp; &nbsp;コメント列。)| |
> | フェデレーション ID は現在展開されていますか? <br/>(Active Directory フェデレーション サービス (AD FS)または <br/>サード パーティ) | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | フェデレーション ID を使用している場合は、 <br/>フェデレーション インフラストラクチャ? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox"> サード パーティフェデレーション <br/>&nbsp;&nbsp; &nbsp;gateway (詳細に注意してください) <br/>&nbsp;&nbsp; &nbsp;[コメント] 列に表示されます)。 | |
> | 現在アクティブなMicrosoft 365を管理している場合<br/>またはテナントOffice 365、次の SMTP/SIP ドメインです。 <br/>テナントに関連付けられているターゲット ユーザー | <input type="checkbox">N/A – Microsoft 365または<br/>&nbsp;&nbsp; &nbsp;Office 365テナントを配置する <br/> <input type="checkbox"> いいえ。ユーザーの SMTP/SIP <br/>&nbsp;&nbsp; &nbsp;ドメインが関連付けられていない <br/>&nbsp;&nbsp; &nbsp;内の任意のテナントと <br/>&nbsp;&nbsp; &nbsp;Microsoft 365またはOffice 365<br/> <input type="checkbox"> はい。ユーザーの SMTP/SIP <br/>&nbsp;&nbsp; &nbsp;ドメインが関連付けられている <br/>&nbsp;&nbsp; &nbsp;既存のテナントを含む <br/>&nbsp;&nbsp; &nbsp;Microsoft 365またはOffice 365 | |
> | ユーザー UPN はプライマリ SMTP アドレスと一致しますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ <br/> <input type="checkbox"> 一貫性 | |

## <a name="existing-collaboration-platform-summary"></a>既存のコラボレーション プラットフォームの概要

次の表を使用して、既存のコラボレーション プラットフォームのデプロイに関する情報をキャプチャします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Microsoft Teams は展開されていますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | Skype for Business は展開されていますか? <br/>オンプレミスとハイブリッドのデプロイの場合は、必ず <br/>バージョンと累積的な更新プログラム (CU) に注意してください <br/>[コメント] 列の詳細。 | <input type="checkbox">はい、Microsoft 365、または <br/>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox"> はい、ハイブリッド (と <br/>&nbsp;&nbsp; &nbsp;Microsoft 365または <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> はい(オンプレミス) <br/> <input type="checkbox"> はい、オンライン、専用 <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> はい、ホストされている、専用 <br/>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox"> はい、ホストされている、共有されている <br/>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox"> いいえ、その他 | |
> | Exchange は展開されていますか? <br/>オンプレミスとハイブリッドのデプロイの場合は、必ず <br/>コメントにバージョンと CU の詳細を書き留める <br/>列。 | <input type="checkbox">はい、Microsoft 365 <br/> <input type="checkbox"> はい、ハイブリッド (と <br/>&nbsp;&nbsp; &nbsp;Microsoft 365または <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> はい(オンプレミス) <br/> <input type="checkbox"> はい、オンライン、専用 <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> はい、ホストされている、専用 <br/>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox"> はい、ホストされている、共有されている <br/>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox"> いいえ、その他 | |
> | SharePoint は展開されていますか? <br/>オンプレミスとハイブリッドのデプロイの場合は、必ず <br/>コメントにバージョンと CU の詳細を書き留める <br/>列。 | <input type="checkbox">はい、Microsoft 365 <br/> <input type="checkbox"> はい、ハイブリッド (と <br/>&nbsp;&nbsp; &nbsp;Microsoft 365または <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> はい(オンプレミス) <br/> <input type="checkbox"> はい、オンライン、専用 <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> はい、ホストされている、専用 <br/>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox"> はい、ホストされている、共有されている <br/>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox"> いいえ、その他 | |
> | OneDrive for Businessデプロイされますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | 他のサード パーティプラットフォームがデプロイされていますか? <br/>現在使用中ですか? その場合は、次のユーザーの数に注意してください。 <br/>これらのプラットフォームと、以下の使用の詳細 <br/>[コメント] 列。 | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> たるみ <br/> <input type="checkbox"> Other (Specify in the <br/>&nbsp;&nbsp; &nbsp;コメント列。) | ユーザーの数: <br/>詳細：|
> | これらのサード パーティからユーザーを移動することを計画していますか? <br/>プラットフォームをTeamsにしますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | 現在のテレフォニーと会議ソリューションとは <br/>このイニシアチブのスコープに含まれるユーザーの数を確認してください。 | | |
> | [直接ルーティングをサポートする SBC](./direct-routing-plan.md#supported-session-border-controllers-sbcs) を展開していますか? <br/>このイニシアチブの対象となるオフィスの場合は、 [はい] の場合<br/>コメント列の詳細に注意してください。| <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ ||

## <a name="collaboration-platform-deployment-details"></a>コラボレーション プラットフォームのデプロイの詳細

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (該当する場合)

該当する場合は、次のサンプル 表を使用して、Teamsデプロイの詳細をキャプチャします。 Teamsをデプロイしていない場合は、このセクションをスキップしてください。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | どの種類のユーザーが Teams で有効になっていますか? | <input type="checkbox"> 組織内のすべてのユーザー <br/> <input type="checkbox"> 特定のユーザー/ユーザー グループ <br/>&nbsp;&nbsp; &nbsp;([コメント] 列で指定します)。 ||
> | どのTeams機能とモダリティが使用されていますか? | <input type="checkbox"> チャネルベースの会話 <br/> <input type="checkbox"> プライベート チャット <br/> <input type="checkbox"> ゲスト アクセス <br/> <input type="checkbox"> チャネル会議 <br/> <input type="checkbox"> プライベート会議 <br/> <input type="checkbox"> プライベート通話 <br/> <input type="checkbox"> アドホック チャネルの会議 <br/> <input type="checkbox"> 会議のビデオ <br/> <input type="checkbox"> 会議での画面共有 <br/> <input type="checkbox"> 電話会議 <br/><input type="checkbox"> アプリケーション (アプリ)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox">タブ<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">ボット <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">コネクタ<br/><input type="checkbox"> カスタム クラウド ストレージの統合 <br/>&nbsp;&nbsp; &nbsp; Dropbox、Box、ShareFile、Google <br/>&nbsp;&nbsp; &nbsp;ドライブ、Egnyte <br/> <input type="checkbox"> チャネル電子メールの統合 <br/> <input type="checkbox"> その他 ([コメント] 列で指定します)。 | |
> | Teamsにデプロイしたアプリケーションは何ですか? | | |
> | 特定的に禁止している Teams の機能はありますか? <br/>[はい] の場合は、[コメント] 列の詳細に注意してください。 | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ ||
> | どの Teams クライアントが使用されていますか? | <input type="checkbox"> Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox">Windows Mobile | |
> | チームを作成するためのアクセス許可があるのは誰ですか? | <input type="checkbox"> 組織内のすべてのユーザー <br/>&nbsp;&nbsp; &nbsp;(これは既定の設定です) <br/> <input type="checkbox"> 特定のユーザー <br/>&nbsp;&nbsp; &nbsp;([コメント] 列で指定します)。 | |
> | Teams でセキュリティおよびコンプライアンスの機能を使用していますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (該当する場合)

該当する場合は、次のサンプル 表を使用して、Skype for Business Online デプロイの詳細をキャプチャします。 オンライン展開Skype for Business展開していない場合は、このセクションをスキップしてください。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Skypeに対して有効になっているユーザーの種類 <br/>Business Online の場合 | <input type="checkbox"> 組織内のすべてのユーザー <br/> <input type="checkbox"> 特定のユーザー/ユーザー グループ <br/>&nbsp;&nbsp; &nbsp;([コメント] 列で指定します)。 | |
> | 現在どのようなモダリティと機能があるか <br/>現在使用中ですか? | <input type="checkbox"> インスタント メッセージングとプレゼンス (IM/P)<br/> <input type="checkbox"> 会議 <br/> <input type="checkbox"> フェデレーション <br/> <input type="checkbox"> 会議の記録 <br/> <input type="checkbox"> Microsoft 電話会議 <br/> <input type="checkbox"> サード パーティの電話会議 (注)<br/>&nbsp;&nbsp; &nbsp;[コメント] 列の詳細)。 <br/> <input type="checkbox"> 通話プラン (以前の PSTN 通話) <br/> <input type="checkbox"> 組織の自動応答 <br/> <input type="checkbox"> キューの呼び出し | |
> | 特定のSkypeをブロックしましたか? <br/>Business Online の機能 <br/>[はい] の場合は、[コメント] 列の詳細に注意してください。 | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | どの方法を使用しているか、または使用する予定か <br/>電話システム (旧称 Cloud PBX) を <br/>PSTN? <br/>適用するすべてを選択します。 | <input type="checkbox"> 通話プラン (以前の PSTN 通話) <br/> <input type="checkbox"> オンプレミス PSTN 接続 <br/>&nbsp;&nbsp; &nbsp;(既存のSkypeを活用して <br/>&nbsp;&nbsp; &nbsp;Business 2015 または Lync Server <br/>&nbsp;&nbsp; &nbsp;2013 デプロイ) <br/> <input type="checkbox"> オンプレミス PSTN 接続 <br/>&nbsp;&nbsp; &nbsp;(Cloud Connector を使用) | |
> | マイクロソフトに移行した電話番号はありますか? <br/>これは通話プランとオーディオに適用されます <br/>会議機能。 | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business オンプレミス (該当する場合)

該当する場合は、次のサンプル テーブルを使用して、Skype for Businessデプロイの詳細をキャプチャします。 オンプレミスSkype for Business展開していない場合は、このセクションをスキップしてください。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Lync またはSkype for Businessのバージョン <br/> 現在、オンプレミスにデプロイされていますか? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 <br/><input type="checkbox">Skype for Business クラウド コネクタ <br/>&nbsp;&nbsp; &nbsp;版 | |
> | Skype for Business Online とのハイブリッドは構成されていますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | この環境は、3 番目の環境によってホストおよび管理されていますか? <br/>パーティー。 [はい] の場合は、 <br/>[コメント] 列。 | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | 現在使用されているモダリティと機能 <br/>本日は。 | <input type="checkbox"> インスタント メッセージングとプレゼンス (IM/P) <br/> <input type="checkbox"> 会議 <br/> <input type="checkbox"> フェデレーション <br/> <input type="checkbox"> 会議の記録 <br/> <input type="checkbox"> 常設チャット/グループ チャット <br/> <input type="checkbox"> Microsoft 電話会議 <br/>&nbsp;&nbsp; &nbsp;(以前は会議でダイヤルイン) <br/>&nbsp;&nbsp; &nbsp;オンプレミスの Lync Server または <br/>&nbsp;&nbsp; &nbsp;Skype for Businessデプロイ <br/> <input type="checkbox"> サード パーティの電話会議 <br/>&nbsp;&nbsp; &nbsp;(コメントの詳細に注意してください) <br/>&nbsp;&nbsp; &nbsp;column.) <br/> <input type="checkbox">オンプレミスを使用したエンタープライズ VoIP <br/>&nbsp; &nbsp; &nbsp;PSTN 接続 <br/> <input type="checkbox"> 通話プラン (以前の PSTN 通話) 経由 <br/>&nbsp;&nbsp; &nbsp;Skype for Business Online を使用したハイブリッド | |
> | 展開済みの Edge Server のバージョンはいくつですか? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019| |
> | Lync または Skype for Business Edge をお持ちか <br/>複数のデータセンターにデプロイされていますか? <br/>[はい] の場合は、[コメント] 列の詳細に注意してください。 | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | Edge ロールが現在提供するサービスを選択します。 | <input type="checkbox"> 外部ユーザー アクセス (企業ユーザー) <br/> <input type="checkbox"> リモート ユーザー アクセス (匿名) <br/>&nbsp;&nbsp; &nbsp;外部会議参加者) <br/> <input type="checkbox"> フェデレーション <br/> <input type="checkbox"> メディア リレー | |
> | 次の音声通話機能のうち、どれを使用しますか <br/>現在、依存関係がありますか? <br/>コメント内のその他の依存関係に注意してください <br/>列。 | <input type="checkbox"> ビジー状態のオプション <br/> <input type="checkbox"> コール パーク <br/> <input type="checkbox"> 通話ピックアップまたはグループ通話ピックアップ <br/> <input type="checkbox"> 共通エリアの電話、または "ホット デスク" <br/> <input type="checkbox"> 応答グループまたはハント グループ <br/> <input type="checkbox"> 共有線の外観 <br/> <input type="checkbox"> プライベート行 <br/> <input type="checkbox"> ボイスメール <br/> <input type="checkbox"> 仕事を介して通話する <br/> <input type="checkbox"> 緊急または情報の番号 <br/>&nbsp;&nbsp; &nbsp;(911、811、411) <br/> <input type="checkbox"> 内線番号のダイヤル <br/> <input type="checkbox"> 自動応答 <br/> <input type="checkbox"> サブスクライバー アクセス <br/> <input type="checkbox"> アナログ デバイス <br/> <input type="checkbox"> Fax <br/> <input type="checkbox"> 呼び出し元 ID のマスクまたは変更 <br/> <input type="checkbox"> 場所ベースのルーティング <br/> <input type="checkbox"> 最小コストのルーティング <br/> <input type="checkbox"> エレベーターの電話 | |

## <a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Microsoft 365サービスとOffice 365 サービスへのネットワークとアクセス

次の表を使用して、組織のネットワークの詳細と、ユーザーがMicrosoft 365およびOffice 365 サービスに接続されている (または接続される) 方法をキャプチャします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | 移行のスコープ内のユーザーを実行する方法 (または方法) <br/>オフィスにいるときにTeamsにアクセスできますか? <br/>適用するすべてを選択します。 | <input type="checkbox"> ルーティングされた NAT 接続 <br/> <input type="checkbox"> プロキシ サーバー <br/> <input type="checkbox"> パブリック Wi-Fi <br/> <input type="checkbox"> マネージド (パブリックではない) Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp;(Microsoft ピアリング) ||
> | Microsoft 365またはOffice 365へのアクセスが<br/>プロキシ サーバーでは、プロキシをバイパスする方法はありますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | ExpressRoute は現在使用されていますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ <br/> <input type="checkbox"> いいえ。ただし、計画中です | |
> | ネットワーク準備状況評価を実行しましたか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | 接続時にユーザーが VPN を使用する必要がある <br/>企業リソースをリモートで使用しますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | VPN が使用されている場合、トラフィックを除外Teamsできます。 <br/>Microsoft 365とOffice 365 サービスに直接アクセスするための VPN? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | お使いのネットワークは QoS をサポートしていますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | オーディオトラフィックとビデオ トラフィックTeams優先順位を付けることができますか? <br/>高品質のエクスペリエンスを推進するには? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | リージョン内のすべての場所にインターネット エグレスが含まれているか、 <br/>または、リージョン全体に対してインターネットエグレスが一元化されていますか? | <input type="checkbox"> インターネットへの地域アクセス <br/> <input type="checkbox"> への一元的なアクセス <br/>&nbsp;&nbsp; &nbsp;インターネット | |

## <a name="endpoints"></a>エンドポイント

次の表を使用して、使用中のクライアントとエンドポイントの詳細をキャプチャします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | ユーザーが使用しているデスクトップ OS は何ですか? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac ([コメント] 列でバージョンを指定します)。 <br/> <input type="checkbox"> Linux ([コメント] 列でディストリビューションを指定します)。 <br/><input type="checkbox"> その他 ([コメント] 列の詳細に注意してください)。 | |
> | デプロイされるMicrosoft Officeのバージョン <br/>これらのデバイスに接続しますか? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office for Mac 2011 <br/> <input type="checkbox">Office for Mac 2016 <br/> <input type="checkbox"> その他 ([コメント] 列の詳細に注意してください)。 | |
> | どのOfficeデプロイ テクノロジが使用されているか <br/>組織内の | <input type="checkbox"> MSI <br/> <input type="checkbox"> クイック実行 | |
> | 許可およびサポートされているモバイルとは <br/>使用中のプラットフォーム <br/>適用するすべてを選択します。 | <input type="checkbox">Windows <br/> <input type="checkbox"> モバイル <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> その他 ([コメント] 列の詳細に注意してください)。 | |
> | モバイル デバイスはどのように提供されますか? <br/>適用するすべてを選択します。 | <input type="checkbox"> 企業のデバイス <br/> <input type="checkbox"> 自分のデバイスを持ち込む | |
> | ユーザーが現在アクセスするために使用しているデバイス <br/>音声および会議サービス <br/>(携帯電話、ヘッドセット、電話、ビデオ)? | | |

## <a name="operations"></a>操作

次の表を使用して、環境の運用上の側面の詳細をキャプチャします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Lync Server の運用モデルは何ですか。 <br/>Skype for Business Server、Microsoft 365デプロイ、 <br/>またはOffice 365のデプロイを今すぐ行いますか? | | |
> | 現在のサポートの取り決めの概要を説明できますか? <br/>Lync Server、Skype for Business Server、Microsoft 365、 <br/>またはOffice 365? | | |
> | 複数の国または地域にデプロイする場合は、 <br/>各国/地域に独自の IT/テレフォニーがありますか? <br/>スタッフが一緒に作業するか、それとも一元的に管理されますか? | <input type="checkbox"> 地域の運用とサポート <br/> <input type="checkbox"> 一元化された操作とサポート | |
> | 通話の品質の方法論に従っていますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | 個人またはチームを組織に割り当てたか <br/>コラボレーション プラットフォームの品質チャンピオン ロール <br/>使用中ですか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ ||
> | Lync Server を監視する方法をSkype <br/>Business Server、Microsoft 365デプロイ、または <br/>デプロイOffice 365? | | |
> | 通話品質の問題を経験しましたか? | <input type="checkbox"> はい<br/> <input type="checkbox"> いいえ | |
> | トレーニングを提供する方法とタイミング <br/>新しいサービスと機能に関するヘルプデスク | | |

## <a name="adoption-and-readiness"></a>導入と準備

次の表を使用して、自分の組織での現在の導入と準備状況を記録してください。

>
> | 質問 | 回答 | コメント |
> |---|---|---|
> | 現在のアクティブな使用状況は何ですか? <br/>Skype for Business? | **__** アクティブなユーザーの合計数と有効なユーザーの割合 | |
> | 組織の使用方法 <br/>Skype for Business? | 1 対 1 の会話 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">IM <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">呼び出す <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">共有<br/> 会議 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">会議<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">共有<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">呼び出す | |
> | 組織にユーザー導入があるか <br/>と Change Management チーム? | <input type="checkbox"> はい<br/> <input type="checkbox"> いいえ | |
> | 現在、テクノロジの成功を測定する方法 <br/>Skype for Businessのようなロールアウト | | |
> | ユーザー ベースに占める割合は何パーセントですか? <br/>Skype for Business採用されましたか? | | |
> | Skype for Business についてのユーザーの感想を教えてください。 | <input type="checkbox"> よし <br/> <input type="checkbox"> 中立 <br/> <input type="checkbox"> 悪い | |
> | ロールアウトについて最もよく説明されているのは、次のうちどれです <br/>Skype for Businessに使用される戦略 <br/>展開。 | <input type="checkbox"> 広範な範囲: 電子メール キャンペーンと <br/>&nbsp;&nbsp; &nbsp;トレーニングへのリンク <br/> <input type="checkbox"> 拡張: 広範な範囲に加え、さまざまな <br/>&nbsp;&nbsp; &nbsp;意識向上キャンペーン (ポスター、 <br/>&nbsp;&nbsp; &nbsp;イベント、チャンピオン)、トレーニング <br/>&nbsp;&nbsp; &nbsp;(ビデオ、ユーザー ガイド、対人) <br/> <input type="checkbox"> 調整済み: 展開済み、およびターゲット設定済み <br/>&nbsp;&nbsp; &nbsp;ペルソナによるメッセージングとトレーニング <br/> <input type="checkbox"> 他 <br/>&nbsp;&nbsp; &nbsp;([コメント] 列の詳細に注意してください)。 | |
