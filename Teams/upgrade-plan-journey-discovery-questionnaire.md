---
title: Microsoft Teamsアップグレード |環境評価、検出に関する質問
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: このガイダンスを使用して、Teamsにアップグレードするための現在の環境を適切に評価するための要件について説明します。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f947141a092d103f04adae07f0bdb60c8a2e0f66
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62418310"
---
# <a name="discovery-questionnaire---evaluate-your-environment"></a>検出アンケート - 環境を評価する

次の一連の表は、[Teamsにアップグレードする前に環境を評価](upgrade-plan-journey-evaluate-environment.md)するのに役立つ質問の一覧です。

- [組織の詳細をMicrosoft 365またはOffice 365する](#microsoft-365-or-office-365-organization-details)
- [既存のコラボレーション プラットフォームの概要](#existing-collaboration-platform-summary)
- [コラボレーション プラットフォームのデプロイの詳細](#collaboration-platform-deployment-details)
- [Microsoft 365またはOffice 365 サービスへのネットワークとアクセス](#networking-and-access-to-microsoft-365-or-office-365-services)
- [エンドポイント](#endpoints)
- [操作](#operations)
- [導入と準備](#adoption-and-readiness)

## <a name="microsoft-365-or-office-365-organization-details"></a>組織の詳細をMicrosoft 365またはOffice 365する

アンケートを操作する際は、アクティブなMicrosoft 365またはOffice 365組織を使用することを非常に推奨します。 Microsoft 365またはOffice 365組織をまだアクティブ化または構成していない場合は、「[ビジネス向けのMicrosoft 365のセットアップを計画する](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)」を参照してください。

次の表を使用して、Microsoft 365またはOffice 365組織に関する情報をキャプチャします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | 運用Microsoft 365またはOffice 365組織に注意する <br>[回答] 列の名前と ID <br/>複数のテナントがある場合 <br>組織に関連付けられている <br>すべての ID をメモします。 | テナント名: <br/>テナント ID:| |
> | テナントはどのリージョンにデプロイされますか?| | |
> | これらのテナントMicrosoft 365か、マルチテナントOffice 365か <br>専用。 | <input type="checkbox"> 雑居<br/> <input type="checkbox"> 専用 | |
> | 現在使用中の Microsoft Online 製品はどれですか? <br/>各ユーザーに対して有効になっているユーザーの数に注意してください <br>[コメント] 列のサービス。 | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype for Business <br>&nbsp; &nbsp; &nbsp;オンライン <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox">Yammer <br/> <input type="checkbox"> 他| |
> | Skypeに対して有効になっているライセンス レベル <br>Business Online ユーザー | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 <br/> <input type="checkbox"> スタンドアロン | ユーザーの数 <br>SKU ごとに次の手順を実行します。 |
> | 現在の Active Directory フォレストとは <br>環境内の機能レベル <br/>複数のフォレストがある場合は、詳細をメモします <br>[コメント] 列に表示されます。 | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | ディレクトリに使用しているもの <br>今すぐ同期しますか? |<input type="checkbox"> 同期なし (クラウドのみ) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp; &nbsp; &nbsp;接続 <br/> <input type="checkbox"> Other (Specify in the <br>&nbsp;&nbsp; &nbsp;コメント列。)| |
> | フェデレーション ID は現在展開されていますか? <br/>(Active Directory フェデレーション サービス (AD FS)または <br>サード パーティ) | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | フェデレーション ID を使用している場合は、 <br>フェデレーション インフラストラクチャ? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox"> サード パーティフェデレーション <br>&nbsp;&nbsp; &nbsp;ゲートウェイ <br>&nbsp; &nbsp; &nbsp;(Note the details in the <br>&nbsp;&nbsp; &nbsp;コメント列。) | |
> | 現在アクティブなMicrosoft 365またはOffice 365を管理している場合 <br>テナントは、お客様の SMTP/SIP ドメインです。 <br>テナントに関連付けられているターゲット ユーザー | <input type="checkbox">N/A – Microsoft 365またはOffice 365なし <br>&nbsp;&nbsp; &nbsp;テナントが配置されている <br/> <input type="checkbox"> いいえ。ユーザーの SMTP/SIP <br>&nbsp;&nbsp; &nbsp;ドメインが関連付けられていない <br>&nbsp;&nbsp; &nbsp;内の任意のテナントと <br>&nbsp;&nbsp; &nbsp;Microsoft 365またはOffice 365 <br/> <input type="checkbox"> はい。ユーザーの SMTP/SIP <br>&nbsp;&nbsp; &nbsp;ドメインが関連付けられている <br>&nbsp;&nbsp; &nbsp;既存のテナントを使用する <br>&nbsp;&nbsp; &nbsp;Microsoft 365またはOffice 365 | |
> | ユーザー UPN はプライマリ SMTP アドレスと一致しますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ <br/> <input type="checkbox"> 一貫性 | |

## <a name="existing-collaboration-platform-summary"></a>既存のコラボレーション プラットフォームの概要

次の表を使用して、既存のコラボレーション プラットフォームのデプロイに関する情報をキャプチャします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Microsoft Teams は展開されていますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | Skype for Business は展開されていますか? <br/>オンプレミスとハイブリッドのデプロイの場合は、必ず <br>バージョンと累積的な更新プログラム (CU) に注意してください <br>[コメント] 列の詳細。 | <input type="checkbox">はい、Microsoft 365、またはOffice 365 <br/> <input type="checkbox">はい、ハイブリッド (Microsoft 365またはOffice 365) <br/> <input type="checkbox"> はい(オンプレミス) <br/> <input type="checkbox"> はい、オンライン、専用 <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> はい、ホストされている、専用 <br>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox"> はい、ホスト、共有 (サード パーティ) <br/> <input type="checkbox"> いいえ、その他 | |
> | Exchange は展開されていますか? <br/>オンプレミスとハイブリッドのデプロイの場合は、必ず <br>コメントにバージョンと CU の詳細を書き留める <br>列。 | <input type="checkbox">はい、Microsoft 365、またはOffice 365 <br/> <input type="checkbox">はい、ハイブリッド (Microsoft 365またはOffice 365) <br/> <input type="checkbox"> はい(オンプレミス) <br/> <input type="checkbox"> はい、オンライン、専用 <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> はい、ホストされている、専用 <br>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox"> はい、ホストされている、共有されている <br>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox"> いいえ、その他 | |
> | SharePoint は展開されていますか? <br/>オンプレミスとハイブリッドのデプロイの場合は、必ず <br>コメントにバージョンと CU の詳細を書き留める <br>列。 | <input type="checkbox">はい、Microsoft 365、またはOffice 365 <br/> <input type="checkbox">はい、ハイブリッド (Microsoft 365またはOffice 365) <br/> <input type="checkbox"> はい(オンプレミス) <br/> <input type="checkbox"> はい、オンライン、専用 <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> はい、ホストされている、専用 <br>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox"> はい、ホストされている、共有されている <br>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox"> いいえ、その他 | |
> | Microsoft 365またはOffice 365 OneDrive for Businessはデプロイされていますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | 他のサード パーティプラットフォームがデプロイされていますか? <br>現在使用中ですか? その場合は、次のユーザーの数に注意してください。 <br>これらのプラットフォームとコメントの使用状況の詳細 <br>列。 | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> たるみ <br/> <input type="checkbox"> その他 (コメントで指定する) <br>&nbsp;&nbsp; &nbsp;column.) | ユーザーの数: <br/>詳細：|
> | これらのサード パーティからユーザーを移動することを計画していますか? <br>プラットフォームをTeamsにしますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | 現在のテレフォニーと会議ソリューションとは <br>このイニシアチブのスコープに含まれるユーザーの数を確認してください。 | | |
> | このイニシアチブの対象となるオフィスに [直接ルーティングをサポートする SBC](direct-routing-plan.md#supported-session-border-controllers-sbcs) はありますか? <br>[はい] の場合は、[コメント] 列の詳細に注意してください。| <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ ||

## <a name="collaboration-platform-deployment-details"></a>コラボレーション プラットフォームのデプロイの詳細

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (該当する場合)

該当する場合は、次のサンプル 表を使用して、Teamsデプロイの詳細をキャプチャします。 Teamsをデプロイしていない場合は、このセクションをスキップしてください。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | どの種類のユーザーが Teams で有効になっていますか? | <input type="checkbox"> 組織内のすべてのユーザー <br/> <input type="checkbox"> 特定のユーザー/ユーザー グループ <br>&nbsp;&nbsp; &nbsp;([コメント] 列で指定) ||
> | どのTeams機能とモダリティが使用されていますか? | <input type="checkbox"> チャネルベースの会話 <br/> <input type="checkbox"> プライベート チャット <br/> <input type="checkbox"> ゲスト アクセス <br/> <input type="checkbox"> チャネル会議 <br/> <input type="checkbox"> プライベート会議 <br/> <input type="checkbox"> プライベート通話 <br/> <input type="checkbox"> アドホック チャネルの会議 <br/> <input type="checkbox"> 会議のビデオ <br/> <input type="checkbox"> 会議での画面共有 <br/> <input type="checkbox"> 電話会議 <br/><input type="checkbox"> アプリケーション (アプリ)<br> &nbsp;&nbsp; &nbsp;<input type="checkbox">タブ<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">ボット <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">コネクタ<br><input type="checkbox"> カスタム クラウド ストレージの統合 <br>&nbsp;&nbsp; &nbsp; Dropbox、Box、ShareFile、Google ドライブ、Egnyte <br/> <input type="checkbox"> チャネル電子メールの統合 <br/> <input type="checkbox"> その他 ([コメント] 列で指定します)。 | |
> | Teamsにデプロイしたアプリケーションは何ですか? | | |
> | 特定的に禁止している Teams の機能はありますか? <br/>[はい] の場合は、[コメント] 列の詳細に注意してください。 | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ ||
> | どの Teams クライアントが使用されていますか? | <input type="checkbox"> Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox">Windows Mobile | |
> | チームを作成するためのアクセス許可があるのは誰ですか? | <input type="checkbox"> 組織内のすべてのユーザー <br>&nbsp;&nbsp; &nbsp;(これは既定の設定です) <br/> <input type="checkbox"> 特定のユーザー <br>&nbsp;&nbsp; &nbsp;([コメント] 列で指定します)。 | |
> | Teams でセキュリティおよびコンプライアンスの機能を使用していますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (該当する場合)

該当する場合は、次のサンプル 表を使用して、Skype for Business Online デプロイの詳細をキャプチャします。 オンライン展開Skype for Business展開していない場合は、このセクションをスキップしてください。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Skypeに対して有効になっているユーザーの種類 <br>Business Online の場合 | <input type="checkbox"> 組織内のすべてのユーザー <br/> <input type="checkbox"> 特定のユーザー/ユーザー グループ <br>&nbsp;&nbsp; &nbsp;([コメント] 列で指定) | |
> | 現在どのようなモダリティと機能があるか <br>現在使用中ですか? | <input type="checkbox"> インスタント メッセージングとプレゼンス (IM/P)<br/> <input type="checkbox"> 会議 <br/> <input type="checkbox"> フェデレーション <br/> <input type="checkbox"> 会議の記録 <br/> <input type="checkbox"> Microsoft 電話会議 <br/> <input type="checkbox"> サード パーティの電話会議 <br>&nbsp;&nbsp; &nbsp;([コメント] 列の詳細に注意してください)。 <br/> <input type="checkbox"> 通話プラン (以前の PSTN 通話) <br/> <input type="checkbox"> 組織の自動応答 <br/> <input type="checkbox"> キューの呼び出し | |
> | 特定のSkypeをブロックしましたか? <br>Business Online の機能 <br>[はい] の場合は、[コメント] 列の詳細に注意してください。 | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | どの方法を使用しているか、または使用する予定か <br>電話システム (旧称 Cloud PBX) を <br>PSTN? <br/>適用するすべてを選択します。 | <input type="checkbox"> 通話プラン (以前の PSTN 通話) <br/> <input type="checkbox"> オンプレミスの PSTN 接続 (既存の PSTN 接続を活用する) <br>&nbsp;&nbsp; &nbsp;Skype for Business 2015 または Lync Server 2013 <br>&nbsp;&nbsp; &nbsp;deployment) <br/> <input type="checkbox"> オンプレミス PSTN 接続 (クラウド コネクタを使用) | |
> | マイクロソフトに移行した電話番号はありますか? <br/>これは通話プランとオーディオに適用されます <br>会議機能。 | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business オンプレミス (該当する場合)

該当する場合は、次のサンプル テーブルを使用して、Skype for Businessデプロイの詳細をキャプチャします。 オンプレミスSkype for Business展開していない場合は、このセクションをスキップしてください。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Lync またはSkype for Businessの現在のバージョン <br>オンプレミスにデプロイされていますか? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 <br/> <input type="checkbox">Skype for Business クラウド コネクタ エディション | |
> | Skype for Business Online とのハイブリッドは構成されていますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | この環境はサード パーティによってホストおよび管理されていますか? <br/>[はい] の場合は、[コメント] 列の詳細に注意してください。 | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | 現在使用されているモダリティと機能 <br>本日は。 | <input type="checkbox"> インスタント メッセージングとプレゼンス (IM/P) <br/> <input type="checkbox"> 会議 <br/> <input type="checkbox"> フェデレーション <br/> <input type="checkbox"> 会議の記録 <br/> <input type="checkbox"> 常設チャット/グループ チャット <br/> <input type="checkbox"> Microsoft 電話会議 <br>&nbsp;&nbsp; &nbsp;(以前は会議でダイヤルイン) <br>&nbsp;&nbsp; &nbsp;オンプレミスの Lync Server または <br>&nbsp;&nbsp; &nbsp;Skype for Businessデプロイ <br/> <input type="checkbox"> サード パーティの電話会議 <br>&nbsp;&nbsp; &nbsp;([コメント] 列の詳細に注意してください) <br/> <input type="checkbox">オンプレミス PSTN を使用したエンタープライズ VoIP <br>&nbsp;&nbsp; &nbsp;接続 <br/> <input type="checkbox"> 通話プラン (以前の PSTN 通話) 経由 <br>&nbsp;&nbsp; &nbsp;Skype for Business Online を使用したハイブリッド | |
> | 展開済みの Edge Server のバージョンはいくつですか? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 | |
> | Lync または Skype for Business Edge が展開されていますか? <br>複数のデータセンターに入る場合 <br/>[はい] の場合は、[コメント] 列の詳細に注意してください。 | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | Edge ロールが現在提供するサービスを選択します。 | <input type="checkbox"> 外部ユーザー アクセス (企業ユーザー) <br/> <input type="checkbox"> リモート ユーザー アクセス (匿名外部 <br>&nbsp;&nbsp; &nbsp;会議の参加者) <br/> <input type="checkbox"> フェデレーション <br/> <input type="checkbox"> メディア リレー | |
> | 次の音声通話機能のうち、どれを使用しますか <br>現在、依存関係がありますか? <br/>コメント内のその他の依存関係に注意してください <br>列。 | <input type="checkbox"> ビジー状態のオプション <br/> <input type="checkbox"> コール パーク <br/> <input type="checkbox"> 通話ピックアップまたはグループ通話ピックアップ <br/> <input type="checkbox"> 共通エリアの電話、または "ホット デスク" <br/> <input type="checkbox"> 応答グループまたはハント グループ <br/> <input type="checkbox"> 共有線の外観 <br/> <input type="checkbox"> プライベート行 <br/> <input type="checkbox"> ボイスメール <br/> <input type="checkbox"> 仕事を介して通話する <br/> <input type="checkbox"> 緊急または情報の番号 <br>&nbsp;&nbsp; &nbsp;(911、811、411) <br/> <input type="checkbox"> 内線番号のダイヤル <br/> <input type="checkbox"> 自動応答 <br/> <input type="checkbox"> サブスクライバー アクセス <br/> <input type="checkbox"> アナログ デバイス <br/> <input type="checkbox"> Fax <br/> <input type="checkbox"> 呼び出し元 ID のマスクまたは変更 <br/> <input type="checkbox"> 場所ベースのルーティング <br/> <input type="checkbox"> 最小コストのルーティング <br/> <input type="checkbox"> エレベーターの電話 | |

## <a name="networking-and-access-to-microsoft-365-or-office-365-services"></a>Microsoft 365またはOffice 365 サービスへのネットワークとアクセス

次の表を使用して、組織のネットワークの詳細と、ユーザーがMicrosoft 365またはOffice 365 サービスに接続されている (または接続される) 方法をキャプチャします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | 移行のスコープ内のユーザーを実行する方法 (または方法) <br>オフィスにいるときにTeamsにアクセスできますか? <br/>適用するすべてを選択します。 | <input type="checkbox"> ルーティングされた NAT 接続 <br/> <input type="checkbox"> プロキシ サーバー <br/> <input type="checkbox"> パブリック Wi-Fi <br/> <input type="checkbox"> マネージド (パブリックではない) Wi-Fi <br/> <input type="checkbox"> ExpressRoute (Microsoft ピアリング) ||
> | Microsoft 365またはOffice 365へのアクセスがプロキシ サーバー経由である場合は、次の手順に進みます。 <br>プロキシをバイパスする方法はありますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | ExpressRoute は現在使用されていますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ <br/> <input type="checkbox"> いいえ。ただし、計画中です | |
> | ネットワーク準備状況評価を実行しましたか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | 接続時にユーザーが VPN を使用する必要がある <br>企業リソースをリモートで使用しますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | VPN が使用されている場合、トラフィックを除外Teamsできます。 <br>Microsoft 365またはOffice 365 サービスに直接アクセスするための VPN? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | お使いのネットワークは QoS をサポートしていますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | オーディオトラフィックとビデオ トラフィックTeams優先順位を付けることができますか? <br>高品質のエクスペリエンスを推進するには? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | リージョン内のすべての場所にインターネット エグレスが含まれているか、 <br>または、リージョン全体に対してインターネットエグレスが一元化されていますか? | <input type="checkbox"> インターネットへの地域アクセス <br/> <input type="checkbox"> インターネットへの一元的なアクセス | |

## <a name="endpoints"></a>エンドポイント

次の表を使用して、使用中のクライアントとエンドポイントの詳細をキャプチャします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | ユーザーが使用しているデスクトップ OS は何ですか? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac ([コメント] 列でバージョンを指定します)。 <br/> <input type="checkbox"> Linux ([コメント] 列でディストリビューションを指定します)。 <br/> <input type="checkbox"> その他 ([コメント] 列の詳細に注意してください)。 | |
> | デプロイされるMicrosoft Officeのバージョン <br>これらのデバイスに接続しますか? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office for Mac 2011 <br/> <input type="checkbox">Office for Mac 2016 <br/> <input type="checkbox"> その他 ([コメント] 列の詳細に注意してください)。 | |
> | どのOfficeデプロイ テクノロジが使用されているか <br>組織内の | <input type="checkbox"> MSI <br/> <input type="checkbox"> クイック実行 | |
> | 許可およびサポートされているモバイルとは <br>使用中のプラットフォーム <br/>適用するすべてを選択します。 | <input type="checkbox">Windows <br/> <input type="checkbox"> モバイル <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> その他 ([コメント] 列の詳細に注意してください)。 | |
> | モバイル デバイスはどのように提供されますか? <br/>適用するすべてを選択します。 | <input type="checkbox"> 企業のデバイス <br/> <input type="checkbox"> 自分のデバイスを持ち込む | |
> | ユーザーが現在アクセスするために使用しているデバイス <br>音声および会議サービス <br>(携帯電話、ヘッドセット、電話、ビデオ)? | | |

## <a name="operations"></a>操作

次の表を使用して、環境の運用上の側面の詳細をキャプチャします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Lync Server の運用モデルは何ですか。 <br>Skype for Business Server、Microsoft 365、またはOffice 365デプロイ <br>本日は。 | | |
> | 現在のサポートの取り決めの概要を説明できますか? <br>Lync Server、Skype for Business Server、Microsoft 365、またはOffice 365? | | |
> | 複数の国または地域にデプロイする場合は、 <br>各国/地域に独自の IT/テレフォニーがありますか? <br>スタッフが一緒に作業するか、それとも一元的に管理されますか? | <input type="checkbox"> 地域の運用とサポート <br/> <input type="checkbox"> 一元化された操作とサポート | |
> | [通話品質の手法](quality-of-experience-review-guide.md)に従っていますか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ | |
> | 個人またはチームを組織に割り当てたか <br>コラボレーション プラットフォームの品質チャンピオン ロール <br>使用中ですか? | <input type="checkbox"> はい <br/> <input type="checkbox"> いいえ ||
> | Lync Server を監視する方法をSkype <br>Business Server、Microsoft 365、またはOffice 365の展開 | | |
> | 通話品質の問題を経験しましたか? | <input type="checkbox"> はい<br/> <input type="checkbox"> いいえ | |
> | トレーニングを提供する方法とタイミング <br>新しいサービスと機能に関するヘルプデスク | | |

## <a name="adoption-and-readiness"></a>導入と準備

次の表を使用して、自分の組織での現在の導入と準備状況を記録してください。

>
> | 質問 | 回答 | コメント |
> |---|---|---|
> | 現在のアクティブな使用状況は何ですか? <br>Skype for Business? | **__** アクティブなユーザーの合計数と有効なユーザーの割合 | |
> | 組織の使用方法 <br>Skype for Business? | 1 対 1 の会話 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">IM <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">呼び出す <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">共有<br> 会議 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">会議<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">共有<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">呼び出す | |
> | 組織にユーザー導入があるか <br>と Change Management チーム? | <input type="checkbox"> はい<br/> <input type="checkbox"> いいえ | |
> | 現在、テクノロジの成功を測定する方法 <br>Skype for Businessのようなロールアウト | | |
> | ユーザー ベースに占める割合は何パーセントですか? <br>Skype for Business採用されましたか? | | |
> | Skype for Business についてのユーザーの感想を教えてください。 | <input type="checkbox"> よし <br/> <input type="checkbox"> 中立 <br/> <input type="checkbox"> 悪い | |
> | ロールアウトについて最もよく説明されているのは、次のうちどれです <br>Skype for Businessに使用される戦略 <br>展開。 | <input type="checkbox"> 広範な範囲: 電子メール キャンペーンと <br>&nbsp;&nbsp; &nbsp;トレーニングへのリンク <br/> <input type="checkbox"> 拡張: 広範な範囲に加え、さまざまな <br>&nbsp;&nbsp; &nbsp;意識向上キャンペーン (ポスター、 <br>&nbsp;&nbsp; &nbsp;イベント、チャンピオン)、トレーニング <br>&nbsp;&nbsp; &nbsp;(ビデオ、ユーザー ガイド、対人) <br/> <input type="checkbox"> 調整済み: 展開済み、およびターゲット設定済み <br>&nbsp;&nbsp; &nbsp;ペルソナによるメッセージングとトレーニング <br/> <input type="checkbox"> 他 <br>&nbsp;&nbsp; &nbsp;([コメント] 列の詳細に注意してください)。 | |


