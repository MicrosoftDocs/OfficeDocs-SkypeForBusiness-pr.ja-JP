---
title: Microsoft Teams のアップグレード |環境の評価、検出に関する質問
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: このガイダンスを使用して、Teams にアップグレードするために現在の環境を適切に評価するための要件について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b031b768bf918107cd60563e2e31b8d71b9018cc
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158771"
---
# <a name="discovery-questionnaire---evaluate-your-environment"></a>探索アンケート-環境を評価する

次の一連の表では、 [Teams にアップグレードする前に環境を評価](upgrade-plan-journey-evaluate-environment.md)するのに役立ちます。

- [Microsoft 365 または Office 365 組織の詳細](#microsoft-365-or-office-365-organization-details)
- [既存のコラボレーションプラットフォームの概要](#existing-collaboration-platform-summary)
- [コラボレーションプラットフォームの展開の詳細](#collaboration-platform-deployment-details)
- [Microsoft 365 または Office 365 サービスへのネットワークとアクセス](#networking-and-access-to-microsoft-365-or-office-365-services)
- [エンドポイント](#endpoints)
- [操作](#operations)
- [導入と準備](#adoption-and-readiness)

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365 または Office 365 組織の詳細

アンケートの作業には、アクティブな Microsoft 365 または Office 365 組織があることを強くお勧めします。 Microsoft 365 または Office 365 の組織をまだアクティブ化していない場合、または構成していない場合は、「 [microsoft 365 for business のセットアップを計画](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)する」を参照してください。

次の表を使用して、Microsoft 365 または Office 365 組織に関する情報を取得します。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Microsoft 365 または Office 365 の運用環境を確認する <br>[回答] 列の名前と ID <br/>複数のテナントがある場合 <br>組織に関連付けられている <br>すべての Id をメモします。 | テナント名: <br/>テナント ID:| |
> | テナントはどの地域で展開されますか?| | |
> | これらは Microsoft 365 または Office 365 のテナントですか <br>ド? | <input type="checkbox">テナント<br/> <input type="checkbox">ド | |
> | 現在使用中の Microsoft Online 製品はどれですか? <br/>各ユーザーに対して有効になっているユーザーの数を確認する <br>[コメント列のサービスを選びます。 | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype for Business <br>&nbsp; &nbsp; &nbsp;オンライン <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">他の| |
> | Skype 用に有効になっているライセンスレベル <br>ビジネスオンラインユーザーの場合 | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 <br/> <input type="checkbox">版 | ユーザー数 <br>各 SKU の場合: |
> | 現在の Active Directory フォレストとは <br>環境の機能レベル <br/>複数のフォレストがある場合は、詳細を確認する <br>コメント列。 | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | ディレクトリについて <br>今すぐ同期していますか? |<input type="checkbox">同期なし (クラウドのみ) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;接続 <br/> <input type="checkbox">その他 ( <br>&nbsp;&nbsp; &nbsp;コメント列。)| |
> | フェデレーション ID は現在展開されていますか? <br/>(Active Directory フェデレーションサービスまたは <br>サードパーティ) | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | フェデレーション id を使用している場合、 <br>フェデレーションインフラストラクチャ | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">サードパーティのフェデレーション <br>&nbsp;&nbsp; &nbsp; ゲートウェイ <br>&nbsp;&nbsp; &nbsp; (詳細については、 <br>&nbsp;&nbsp; &nbsp;コメント列。) | |
> | 現在アクティブな Microsoft 365 または Office 365 を保持している場合 <br>テナントは、の SMTP/SIP ドメインです。 <br>テナントに関連付けられているターゲットユーザー | <input type="checkbox">該当なし– Microsoft 365 または Office 365 <br>&nbsp;&nbsp; &nbsp; 場所のテナント <br/> <input type="checkbox">いいえ、ユーザーの SMTP/SIP <br>&nbsp;&nbsp; &nbsp; ドメインが関連付けられていません <br>&nbsp;&nbsp; &nbsp; テナントが <br>&nbsp;&nbsp; &nbsp;Microsoft 365 または Office 365 <br/> <input type="checkbox">はい、ユーザーの SMTP/SIP <br>&nbsp;&nbsp; &nbsp; ドメインが関連付けられている <br>&nbsp;&nbsp; &nbsp; 既存のテナント <br>&nbsp;&nbsp; &nbsp; Microsoft 365 または Office 365 の場合 | |
> | ユーザー Upn はプライマリ SMTP アドレスと一致しますか? | <input type="checkbox">うん <br/> <input type="checkbox">違います <br/> <input type="checkbox">一貫 | |

## <a name="existing-collaboration-platform-summary"></a>既存のコラボレーションプラットフォームの概要

既存のコラボレーションプラットフォームの展開に関する情報を取得するには、次の表を参照してください。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Microsoft Teams は展開されていますか? | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | Skype for Business は展開されていますか? <br/>オンプレミスおよびハイブリッド展開については、 <br>バージョンと累積更新プログラム (CU) を確認します。 <br>[コメント列の詳細情報を表示します。 | <input type="checkbox">はい、Microsoft 365 または Office 365 <br/> <input type="checkbox">○、ハイブリッド (Microsoft 365 または Office 365 を使用) <br/> <input type="checkbox">○、オンプレミス <br/> <input type="checkbox">はい、オンライン、専用 <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">○、Hosted、専用 <br>&nbsp;&nbsp; &nbsp; (サードパーティ) <br/> <input type="checkbox">○、Hosted、shared (サードパーティ) <br/> <input type="checkbox">いいえ、その他 | |
> | Exchange は展開されていますか? <br/>オンプレミスおよびハイブリッド展開については、 <br>バージョンと CU の詳細については、コメントを確認してください。 <br>項目. | <input type="checkbox">はい、Microsoft 365 または Office 365 <br/> <input type="checkbox">○、ハイブリッド (Microsoft 365 または Office 365 を使用) <br/> <input type="checkbox">○、オンプレミス <br/> <input type="checkbox">はい、オンライン、専用 <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">○、Hosted、専用 <br>&nbsp;&nbsp; &nbsp; (サードパーティ) <br/> <input type="checkbox">○、Hosted、shared <br>&nbsp;&nbsp; &nbsp; (サードパーティ) <br/> <input type="checkbox">いいえ、その他 | |
> | SharePoint は展開されていますか? <br/>オンプレミスおよびハイブリッド展開については、 <br>バージョンと CU の詳細については、コメントを確認してください。 <br>項目. | <input type="checkbox">はい、Microsoft 365 または Office 365 <br/> <input type="checkbox">○、ハイブリッド (Microsoft 365 または Office 365 を使用) <br/> <input type="checkbox">○、オンプレミス <br/> <input type="checkbox">はい、オンライン、専用 <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">○、Hosted、専用 <br>&nbsp;&nbsp; &nbsp; (サードパーティ) <br/> <input type="checkbox">○、Hosted、shared <br>&nbsp;&nbsp; &nbsp; (サードパーティ) <br/> <input type="checkbox">いいえ、その他 | |
> | Microsoft 365 または Office 365 OneDrive for business が展開されていますか? | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | その他のサードパーティ製プラットフォームが導入されていますか? <br>今すぐ使用していますか? その場合は、ユーザーの数をメモします。 <br>これらのプラットフォームとコメントの使用状況の詳細 <br>項目. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">総 <br/> <input type="checkbox">その他 (コメントの指定) <br>&nbsp;&nbsp; &nbsp; 列) | ユーザー数: <br/>説明|
> | これらのサードパーティからのユーザーの移行を計画していますか? <br>Teams のプラットフォーム | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | 現在のテレフォニーと会議ソリューションとは <br>このイニシアチブのスコープに参加しているユーザーの数 | | |
> | このイニシアチブの対象となるオフィスに対して、[ダイレクトルーティングをサポートしている SBCs](direct-routing-plan.md#supported-session-border-controllers-sbcs)をお持ちですか? <br>[はい] の場合は、[コメント] 列の詳細を確認します。| <input type="checkbox">うん <br/> <input type="checkbox">違います ||

## <a name="collaboration-platform-deployment-details"></a>コラボレーションプラットフォームの展開の詳細

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (該当する場合)

該当する場合は、以下のサンプルの表を使用して、チームの展開の詳細を把握してください。 Teams を展開していない場合は、このセクションをスキップしてください。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | どの種類のユーザーが Teams で有効になっていますか? | <input type="checkbox">組織内のすべてのユーザー <br/> <input type="checkbox">特定のユーザー/ユーザーグループ <br>&nbsp;&nbsp; &nbsp; ([コメント] 列で指定します) ||
> | どの Teams 機能とモダリティが使用されていますか? | <input type="checkbox">チャネルベースの会話 <br/> <input type="checkbox">プライベートチャット <br/> <input type="checkbox">ゲストアクセス <br/> <input type="checkbox">チャネル会議 <br/> <input type="checkbox">プライベート会議 <br/> <input type="checkbox">プライベート通話 <br/> <input type="checkbox">アドホックチャネル meetup <br/> <input type="checkbox">会議のビデオ <br/> <input type="checkbox">会議での画面共有 <br/> <input type="checkbox">電話会議 <br/><input type="checkbox">アプリケーション (アプリ)<br> &nbsp;&nbsp; &nbsp;<input type="checkbox">タブ<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">ボット <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">コネクタ<br><input type="checkbox">カスタムクラウドストレージの統合 <br>&nbsp;&nbsp; &nbsp;Dropbox、Box、[ファイル]、[Google Drive]、[Egnyte] (近日公開) <br/> <input type="checkbox">チャネルメールの統合 <br/> <input type="checkbox">その他 ([コメント] 列で指定します) | |
> | チームにどのようなアプリケーションを展開していますか? | | |
> | 特定的に禁止している Teams の機能はありますか? <br/>[はい] の場合は、[コメント] 列の詳細を確認します。 | <input type="checkbox">うん <br/> <input type="checkbox">違います ||
> | どの Teams クライアントが使用されていますか? | <input type="checkbox">Web <br/> <input type="checkbox">窓 <br/> <input type="checkbox">For <br/> <input type="checkbox">I/o <br/> <input type="checkbox">用 <br/> <input type="checkbox">Windows Mobile | |
> | チームを作成するためのアクセス許可があるのは誰ですか? | <input type="checkbox">組織内のすべてのユーザー <br>&nbsp;&nbsp; &nbsp; (既定の設定) <br/> <input type="checkbox">特定のユーザー <br>&nbsp;&nbsp; &nbsp; ([コメント] 列で指定します)。 | |
> | Teams でセキュリティおよびコンプライアンスの機能を使用していますか? | <input type="checkbox">うん <br/> <input type="checkbox">違います | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (該当する場合)

該当する場合は、以下のサンプルの表を使用して、Skype for Business Online の展開の詳細をキャプチャします。 Skype for Business Online の展開を展開していない場合は、このセクションをスキップしてください。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Skype で有効になるユーザーの種類 <br>Business Online の場合 | <input type="checkbox">組織内のすべてのユーザー <br/> <input type="checkbox">特定のユーザー/ユーザーグループ <br>&nbsp;&nbsp; &nbsp; ([コメント] 列で指定します) | |
> | 現在のモダリティと機能 <br>現在使用中ですか? | <input type="checkbox">インスタントメッセージとプレゼンス (IM/P)<br/> <input type="checkbox">会合 <br/> <input type="checkbox">フェデレーション <br/> <input type="checkbox">会議のレコーディング <br/> <input type="checkbox">Microsoft 電話会議 <br/> <input type="checkbox">サードパーティの電話会議 <br>&nbsp;&nbsp; &nbsp; ([コメント] 列の詳細に注意してください)。 <br/> <input type="checkbox">通話プラン (以前の PSTN 通話) <br/> <input type="checkbox">組織の自動応答 <br/> <input type="checkbox">通話キュー | |
> | Skype for を個別にブロックしています <br>ビジネスオンライン機能 <br>[はい] の場合は、[コメント] 列の詳細を確認します。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | 使用する方法または使用計画 <br>電話システム (以前のクラウド PBX) をに接続する <br>PSTN の場合 <br/>該当するものをすべて選択します。 | <input type="checkbox">通話プラン (以前の PSTN 通話) <br/> <input type="checkbox">オンプレミスの PSTN 接続 (既存のの活用 <br>&nbsp;&nbsp; &nbsp;Skype for Business 2015 または Lync Server 2013 <br>&nbsp;&nbsp; &nbsp; 展開) <br/> <input type="checkbox">オンプレミスの PSTN 接続 (クラウドコネクタを使用) | |
> | マイクロソフトに移行した電話番号はありますか? <br/>これは、プランと音声通話に適用されます。 <br>会議機能。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business オンプレミス (該当する場合)

該当する場合は、以下のサンプルの表を使用して、Skype for Business 展開の詳細情報を取得します。 オンプレミスの Skype for Business を展開していない場合は、このセクションをスキップしてください。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | 現在の Lync または Skype for Business のバージョン <br>オンプレミスで展開されていますか? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 <br/> <input type="checkbox">Skype for Business Cloud Connector エディション | |
> | Skype for Business Online とのハイブリッドは構成されていますか? | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | この環境はサードパーティによってホストおよび管理されていますか? <br/>[はい] の場合は、[コメント] 列の詳細を確認します。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | 現在使用中のモダリティと機能 <br>本日は。 | <input type="checkbox">インスタントメッセージとプレゼンス (IM/P) <br/> <input type="checkbox">会合 <br/> <input type="checkbox">フェデレーション <br/> <input type="checkbox">会議のレコーディング <br/> <input type="checkbox">常設チャット/グループチャット <br/> <input type="checkbox">Microsoft 電話会議 <br>&nbsp;&nbsp; &nbsp; (以前は電話会議にダイヤルイン) <br>&nbsp;&nbsp; &nbsp; オンプレミスの Lync サーバーまたは <br>&nbsp;&nbsp; &nbsp;Skype for Business の展開 <br/> <input type="checkbox">サードパーティの電話会議 <br>&nbsp;&nbsp; &nbsp; ([コメント] 列の詳細に注意してください)。 <br/> <input type="checkbox">オンプレミスの PSTN を使用したエンタープライズボイス <br>&nbsp;&nbsp; &nbsp; 接続 <br/> <input type="checkbox">通話プラン (以前の PSTN 通話) を使用 <br>&nbsp;&nbsp; &nbsp;Skype for Business Online とのハイブリッド | |
> | 展開済みの Edge Server のバージョンはいくつですか? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 | |
> | Lync または Skype for Business Edge が展開されているか <br>複数のデータセンターの場合 <br/>[はい] の場合は、[コメント] 列の詳細を確認します。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | エッジの役割が今日提供するサービスを選択します。 | <input type="checkbox">外部ユーザーアクセス (企業ユーザー) <br/> <input type="checkbox">リモートユーザーアクセス (匿名外部) <br>&nbsp;&nbsp; &nbsp; 会議の参加者) <br/> <input type="checkbox">フェデレーション <br/> <input type="checkbox">メディアリレー | |
> | 次の音声通話機能のうち、どれを使用していますか? <br>現在、依存関係がありますか? <br/>コメント内の他の依存関係に注意してください <br>項目. | <input type="checkbox">取り込み中のオプション <br/> <input type="checkbox">コールパーク <br/> <input type="checkbox">通話のピックアップまたはグループ通話のピックアップ <br/> <input type="checkbox">一般的なエリア電話または "ホット desking" <br/> <input type="checkbox">応答グループまたはハントグループ <br/> <input type="checkbox">共有の線の外観 <br/> <input type="checkbox">プライベート行 <br/> <input type="checkbox">留守番 <br/> <input type="checkbox">勤務先から通話 <br/> <input type="checkbox">緊急電話番号または情報番号 <br>&nbsp;&nbsp; &nbsp; (911、811、411) <br/> <input type="checkbox">内線番号のダイヤル <br/> <input type="checkbox">自動応答 <br/> <input type="checkbox">サブスクライバーアクセス <br/> <input type="checkbox">アナログデバイス <br/> <input type="checkbox">/Fax <br/> <input type="checkbox">発信者番号通知または変更 <br/> <input type="checkbox">位置情報に基づくルーティング <br/> <input type="checkbox">最小コストのルーティング <br/> <input type="checkbox">エレベーター電話 | |

## <a name="networking-and-access-to-microsoft-365-or-office-365-services"></a>Microsoft 365 または Office 365 サービスへのネットワークとアクセス

次の表を使用して、組織のネットワークの詳細を把握し、ユーザーが Microsoft 365 または Office 365 サービスに接続されているかどうかを確認します。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | ユーザーが移行の対象となるユーザーに対して、どのようにするか (または方法) <br>office を使用しているときにチームにアクセスする <br/>該当するものをすべて選択します。 | <input type="checkbox">ルーティングされた NAT 接続 <br/> <input type="checkbox">プロキシサーバー <br/> <input type="checkbox">パブリック Wi-fi <br/> <input type="checkbox">管理 (公開されていない) Wi-fi <br/> <input type="checkbox">ExpressRoute (Microsoft ピアリング) ||
> | Microsoft 365 または Office 365 へのアクセスがプロキシサーバーを介して行われている場合は、 <br>プロキシをバイパスする方法を教えてください。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | ExpressRoute は現在使用されていますか? | <input type="checkbox">うん <br/> <input type="checkbox">違います <br/> <input type="checkbox">いいえ、計画されています | |
> | ネットワーク準備評価を実行しましたか? | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | ユーザーはに接続するときに VPN の使用を要求されていますか? <br>企業リソースをリモートで確認する | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | VPN が使用されている場合は、チームのトラフィックをから除外することができます。 <br>Microsoft 365 または Office 365 サービスに直接アクセスする VPN | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | お使いのネットワークは QoS をサポートしていますか? | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | チームの音声とビデオのトラフィックの優先順位を付けることができる <br>高品質のエクスペリエンスを実現するには | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | 地域内のすべての場所でインターネットが出口を持つ。 <br>または、地域全体でインターネットの出口を一元管理していますか? | <input type="checkbox">インターネットへの地域アクセス <br/> <input type="checkbox">インターネットへの一元アクセス | |

## <a name="endpoints"></a>エンドポイント

次の表を使用して、使用中のクライアントとエンドポイントの詳細をキャプチャします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | ユーザーが使用しているデスクトップ OS は何ですか? | <input type="checkbox">Windows XP の場合 <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac ([コメント] 列でバージョンを指定します。) <br/> <input type="checkbox">Linux ([コメント] 列で配布を指定します。) <br/> <input type="checkbox">その他 ([コメント] 列の詳細に注意してください)。 | |
> | 展開されている Microsoft Office のバージョン <br>これらのデバイスをお持ちですか? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office for Mac 2011 <br/> <input type="checkbox">Office for Mac 2016 <br/> <input type="checkbox">その他 ([コメント] 列の詳細に注意してください)。 | |
> | 使用中の Office 展開テクノロジ <br>組織内の場合 | <input type="checkbox">MSI <br/> <input type="checkbox">クイック実行 | |
> | 許可されている携帯電話とサポートされているモバイル <br>使用中のプラットフォーム <br/>該当するものをすべて選択します。 | <input type="checkbox">窓 <br/> <input type="checkbox">モバイル <br/> <input type="checkbox">I/o <br/> <input type="checkbox">用 <br/> <input type="checkbox">その他 ([コメント] 列の詳細に注意してください)。 | |
> | モバイル デバイスはどのように提供されますか? <br/>該当するものをすべて選択します。 | <input type="checkbox">企業のデバイス <br/> <input type="checkbox">自分のデバイスを活用する | |
> | ユーザーが現在アクセスに使用しているデバイス <br>音声および会議サービス <br>(ハンドセット、ヘッドセット、電話、ビデオ)? | | |

## <a name="operations"></a>操作

次の表を使用して、環境の運用状況の詳細を把握してください。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Lync Server のオペレーションモデルとは <br>Skype for Business Server、Microsoft 365、または Office 365 の展開 <br>本日は。 | | |
> | 現在のサポートの配置の概要 <br>Lync Server、Skype for Business Server、Microsoft 365、または Office 365 ですか? | | |
> | 複数の国または地域に展開している場合は、 <br>各国または地域には専用の IT とテレフォニーがありますか? <br>共同作業するスタッフ、または一元管理されているスタッフ | <input type="checkbox">地域の運用とサポート <br/> <input type="checkbox">一元管理とサポート | |
> | [通話品質の方法](quality-of-experience-review-guide.md)に従っていますか? | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | 個人またはチームを <br>共同作業プラットフォームの品質チャンピオンの役割 <br>使用中ですか? | <input type="checkbox">うん <br/> <input type="checkbox">違います ||
> | Lync Server、Skype for Business を監視する方法を教えてください。 <br>Business Server、Microsoft 365、または Office 365 の展開 | | |
> | 通話品質の問題を経験しましたか? | <input type="checkbox">うん<br/> <input type="checkbox">違います | |
> | トレーニングをいつどのように行うか <br>新しいサービスや機能のヘルプデスク | | |

## <a name="adoption-and-readiness"></a>導入と準備

次の表を使用して、自分の組織での現在の導入と準備状況を記録してください。

>
> | 質問 | 回答 | コメント |
> |---|---|---|
> | 現在のアクティブな使用状況 <br>Skype for Business の場合 | **__** % のアクティブユーザーと有効なユーザーの合計 | |
> | 組織での使用方法 <br>Skype for Business の場合 | 1 対 1 の会話 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">IM <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">問い合わせる <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">共用<br> 会議 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">会議<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">共用<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">問い合わせる | |
> | 組織のユーザーによる導入 <br>管理チームを変更しますか? | <input type="checkbox">うん<br/> <input type="checkbox">違います | |
> | 現在、テクノロジの成功を測定する方法 <br>Skype for Business などのロールアウト | | |
> | ユーザの基本となる割合 <br>Skype for Business を採用していますか? | | |
> | Skype for Business についてのユーザーの感想を教えてください。 | <input type="checkbox">よし <br/> <input type="checkbox">ニュートラル <br/> <input type="checkbox">無効 | |
> | ロールアウトについて最も適切な説明 <br>Skype for Business で使用される戦略 <br>デプロイメント? | <input type="checkbox">広範なリーチ: のメールキャンペーン <br>&nbsp;&nbsp; &nbsp; トレーニングへのリンク <br/> <input type="checkbox">拡張: 広範なリーチおよびさまざまな種類 <br>&nbsp;&nbsp; &nbsp; 認知キャンペーン (ポスター、 <br>&nbsp;&nbsp; &nbsp; イベント、エキスパート)、トレーニング <br>&nbsp;&nbsp; &nbsp; (ビデオ、ユーザーガイド、ユーザー) <br/> <input type="checkbox">調整済み: 拡張された正の目標 <br>&nbsp;&nbsp; &nbsp; メッセージとトレーニング (ペルソナ) <br/> <input type="checkbox">他の <br>&nbsp;&nbsp; &nbsp; ([コメント] 列の詳細に注意してください)。 | |

