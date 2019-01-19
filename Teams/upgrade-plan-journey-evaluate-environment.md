---
title: マイクロソフト チームのアップグレードします。環境の評価、検出の質問
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: このガイドを使用して、チームにアップグレードするため、現在の環境を正しく評価するための要件について説明します。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: b978bd5fb8c4f62899e9765efaec4ce74383e1d3
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349469"
---
![技術的な準備段階に重点を置いて、旅アップグレードの段階](media/upgrade-banner-tech-readiness.png "技術的な準備段階に重点を置いて、旅アップグレードの段階")

この資料は、ユーザーの準備段階と並行して、完了したアクティビティ、アップグレード、旅の技術的な準備段階の一部です。 次に進む前に前の段階からこれらの活動を完了していることを確認します。

- [プロジェクトの利害関係者が参加しています。](upgrade-enlist-stakeholders.md)
- [プロジェクト スコープの定義](https://aka.ms/SkypetoTeams-Scope)
- [ビジネスとチームの共存と Skype の相互運用性を理解します。](https://aka.ms/SkypeToTeams-Coexist)
- [アップグレード、旅を選択](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="evaluate-your-environment-before-upgrading-to-teams"></a>チームにアップグレードする前に、環境を評価します。

この資料では、適切に運用チームの現在の環境を評価するための要件の概要を示します。 によってお客様の環境を評価するには、リスクと、全体的な配置に影響を与えるための要件を特定します。 これらの項目を事前に識別することによって、ドライブの成功のための計画を調整できます。

## <a name="introduction-to-the-discovery-questionnaire"></a>探索アンケートの概要

客観的キー結果 (OKRs) を達成するためには、以前に主要なサービスの決定を行った。 次のステップは、IT インフラストラクチャ、ネットワーク、および組織がソリューションを実装する準備ができていることを確認する操作に関連するすべての側面を評価するために環境の検出を実行するのには。 探索は、非常に最初に、主要な手順を計画する際、旅のチームの。 環境の検出は、ネットワークのチームへのアップグレードをサポートできるようにするネットワーク対応の評価を含める必要があります。 問題を明らかにして、現在の状態を理解するために環境の詳細な検索を実行するか、さらに重要な-、チームのロールアウトの実行に使用可能なブロック。

環境の評価と導入準備評価の一部として、技術的なリスクを識別し、特定された各リスクの軽減計画を開発します。 リスク レジスタでは、この情報を組み込む必要があります。

既存コラボレーション インフラストラクチャと Office 365 テナント、ネットワーク、エンドポイント、操作、および採用および準備に関連するすべての問題は、環境探索のアンケートの一部として含まれています。 アンケートは、いくつかの主要な領域で、チームの展開は、組織の準備を確認するのには複数のセクションに分かれています。 計画の活動を容易にするためにできるだけ詳細な情報を入力するのにはプロジェクト チームで作業します。

> [!TIP]
> アンケートを Microsoft Word 文書にコピーすることによって開始できます。 すべての質問に回答し、間を移動すると、すべての詳細をキャプチャしようとします。

## <a name="project-team"></a>プロジェクト チーム

プロジェクト チームの適切な人が関与したことを確認します。 [参加プロジェクトの stakekholders](upgrade-enlist-stakeholders.md)で完了した手順を確認します。

## <a name="office-365-tenant-details"></a>Office 365 テナントの詳細

このアンケートを使用する際、作業中の Office 365 テナントがあることを強くお勧めします。 アクティブ化または、Office 365 テナントをまだ構成していない、[企業向けの Office 365 のセットアップの計画](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)を参照してください。

Office 365 テナントに関する情報をキャプチャするのにには、次の表を使用します。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | 生産 Office 365 テナントに注意してください。 <br>名前と、[応答] 列の ID <br/>複数のテナントがある場合 <br>組織に関連付けられています。 <br>すべての Id に注意してください。 | テナントの名前。 <br/>テナント ID:| |
> | どのような地域では、テナント配置でしょうか。| | |
> | これらのテナントの Office 365 のマルチ テナントや <br>専用でしょうか。 | <input type="checkbox">マルチ テナント<br/> <input type="checkbox">専用 | |
> | 現在使用中の Microsoft Online 製品はどれですか? <br/>ごとに有効になっているユーザーの数に注意してください。 <br>[コメント] 列でサービスします。 | <input type="checkbox">マイクロソフト チーム <br/> <input type="checkbox">ビジネス用の Skype <br>&nbsp; &nbsp; &nbsp;オンライン <br/> <input type="checkbox">Exchange オンライン <br/> <input type="checkbox">SharePoint オンライン <br/> <input type="checkbox">ビジネスの OneDrive <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">その他の| |
> | Skype にどのようなライセンスのレベルが有効になっています。 <br>ユーザーのオンライン ビジネスですか。 | <input type="checkbox">E1 と G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4 と第 4 世代の E5 <br/> <input type="checkbox">スタンドアロン | ユーザーの数 <br>各 SKU には。 |
> | 現在の Active Directory フォレストとは <br>環境での機能レベルですか。 <br/>複数のフォレストがある場合は、詳細情報を注意してください。 <br>[コメント] 列にします。 | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | ディレクトリの内容を使用しています <br>今日の同期でしょうか。 |<input type="checkbox">未同期 (クラウドのみ) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;の接続 <br/> <input type="checkbox">他の (で指定します <br>&nbsp;&nbsp; &nbsp;[コメント] 列です)。| |
> | フェデレーション ID は現在展開されていますか? <br/>(Active Directory フェデレーション サービスまたは <br>サード ・ パーティ製) | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | フェデレートされた識別情報を使用する場合とは、 <br>フェデレーション インフラストラクチャですか。 | <input type="checkbox">Windows 2008 R2 の AD FS <br/> <input type="checkbox">Windows 2012 の AD FS <br/> <input type="checkbox">Windows 2012 R2 の AD FS <br/> <input type="checkbox">Windows 2016 の AD FS <br/> <input type="checkbox">サード ・ パーティ製のフェデレーション <br>&nbsp;&nbsp; &nbsp;ゲートウェイ <br>&nbsp;&nbsp; &nbsp;(詳細については、注意してください、 <br>&nbsp;&nbsp; &nbsp;[コメント] 列です)。 | |
> | 現在作業中の Office 365 を管理している場合 <br>テナントは、SMTP とのドメインが、 <br>テナントに関連付けられているユーザーを対象となるでしょうか。 | <input type="checkbox">なし – ない Office 365 <br>&nbsp;&nbsp; &nbsp;のテナント <br/> <input type="checkbox">いいえ、ユーザーの SMTP と SIP <br>&nbsp;&nbsp; &nbsp;ドメインに関連付けられていません。 <br>&nbsp;&nbsp; &nbsp;ですべてのテナントに <br>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox">[はい]、ユーザーの SMTP と SIP <br>&nbsp;&nbsp; &nbsp;ドメインに関連付けられています。 <br>&nbsp;&nbsp; &nbsp;、既存のテナントで <br>&nbsp;&nbsp; &nbsp;Office 365 で | |
> | ユーザーの Upn は、プライマリ SMTP アドレスに一致してでしょうか。 | <input type="checkbox">うん <br/> <input type="checkbox">違います <br/> <input type="checkbox">一貫性がないです。 | |

## <a name="existing-collaboration-platform-summary"></a>既存のコラボレーション プラットフォームの概要

既存のコラボレーション プラットフォームの展開に関する情報をキャプチャするのにには、次の表を使用します。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Microsoft Teams は展開されていますか? | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | Skype for Business は展開されていますか? <br/>設置型およびハイブリッド型の展開を確認 <br>バージョンおよび累積的な更新プログラム (CU) を確認します。 <br>[コメント] 列の詳細です。 | <input type="checkbox">はい、Office 365 <br/> <input type="checkbox">はい、(Office 365) を持つハイブリッド <br/> <input type="checkbox">はい、設置型 <br/> <input type="checkbox">はい、オンライン専用 <br>&nbsp;&nbsp; &nbsp;(マイクロソフト) <br/> <input type="checkbox">はい、ホストされている、専用の <br>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox">はい、ホストされている、共有 (サード パーティ) <br/> <input type="checkbox">いいえ、他の | |
> | Exchange は展開されていますか? <br/>設置型およびハイブリッド型の展開を確認 <br>バージョンとコメントでの CU の詳細に注意します。 <br>列。 | <input type="checkbox">はい、Office 365 <br/> <input type="checkbox">はい、(Office 365) を持つハイブリッド <br/> <input type="checkbox">はい、設置型 <br/> <input type="checkbox">はい、オンライン専用 <br>&nbsp;&nbsp; &nbsp;(マイクロソフト) <br/> <input type="checkbox">はい、ホストされている、専用の <br>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox">はい、ホストされている、共有 <br>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox">いいえ、他の | |
> | SharePoint は展開されていますか? <br/>設置型およびハイブリッド型の展開を確認 <br>バージョンとコメントでの CU の詳細に注意します。 <br>列。 | <input type="checkbox">はい、Office 365 <br/> <input type="checkbox">はい、(Office 365) を持つハイブリッド <br/> <input type="checkbox">はい、設置型 <br/> <input type="checkbox">はい、オンライン専用 <br>&nbsp;&nbsp; &nbsp;(マイクロソフト) <br/> <input type="checkbox">はい、ホストされている、専用の <br>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox">はい、ホストされている、共有 <br>&nbsp;&nbsp; &nbsp;(サード パーティ) <br/> <input type="checkbox">いいえ、他の | |
> | Office 365 の OneDrive は、ビジネスの展開のですか。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | 展開その他のサードパーティのプラットフォームがあります。 <br>現在使用中ですか。 その場合は、ユーザーの数を注意してください。 <br>これらのプラットフォームと、コメントの使用方法の詳細 <br>列。 | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">余裕期間 <br/> <input type="checkbox">他の (コメントの場合に指定します。 <br>&nbsp;&nbsp; &nbsp;列)。 | ユーザーの数: <br/>詳細:|
> | これらのサード ・ パーティからユーザーを移動する予定します。 <br>チームをするためのプラットフォームですか。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | 現在のテレフォニーと会議のソリューションとは <br>このイニシアティブのスコープ内にあるユーザーですか。 | | |
> | [直接ルーティングをサポートする SBCs](direct-routing-plan.md#supported-session-border-controllers-sbcs)オフィスでは、このイニシアチブのスコープ内に配置していますか。 <br>[はい]、[コメント] 列に詳細に注意してください。| <input type="checkbox">うん <br/> <input type="checkbox">違います ||

## <a name="collaboration-platform-deployment-details"></a>コラボレーション プラットフォームの配置の詳細

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (該当する場合)

該当する場合、次のサンプル テーブルを使用して、チームの配置の詳細をキャプチャします。 チームを配置していない場合は、このセクションをスキップします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | どの種類のユーザーが Teams で有効になっていますか? | <input type="checkbox">組織内のすべてのユーザー <br/> <input type="checkbox">特定のユーザーまたはユーザー グループ <br>&nbsp;&nbsp; &nbsp;([コメント] 列を指定してください) ||
> | どのチーム機能や様相は、使用中ですか。 | <input type="checkbox">チャネル ・ ベースの会話 <br/> <input type="checkbox">プライベート チャット <br/> <input type="checkbox">ゲスト アクセス <br/> <input type="checkbox">チャネル会議 <br/> <input type="checkbox">秘密の会議 <br/> <input type="checkbox">プライベート通話 <br/> <input type="checkbox">アドホック チャネル meetup <br/> <input type="checkbox">会議のビデオ <br/> <input type="checkbox">会議で共有画面 <br/> <input type="checkbox">オーディオ会議 <br/><input type="checkbox">アプリケーション (アプリケーション)<br> &nbsp;&nbsp; &nbsp; <input type="checkbox">タブ<br>&nbsp;&nbsp; &nbsp; <input type="checkbox">ボット <br>&nbsp;&nbsp; &nbsp; <input type="checkbox">コネクタ<br><input type="checkbox">カスタム クラウド ストレージの統合 <br>&nbsp;&nbsp; &nbsp; (ボックス、ドロップ ボックス、ShareFile、Google ドライブ) <br/> <input type="checkbox">チャネル電子メールの統合 <br/> <input type="checkbox">その他 (コメント] 列に指定します。) | |
> | チームにどのようなアプリケーションを展開しているでしょうか。 | | |
> | 特定的に禁止している Teams の機能はありますか? <br/>[はい]、[コメント] 列に詳細に注意してください。 | <input type="checkbox">うん <br/> <input type="checkbox">違います ||
> | どの Teams クライアントが使用されていますか? | <input type="checkbox">Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox">Mac <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | チームを作成するためのアクセス許可があるのは誰ですか? | <input type="checkbox">組織内のすべてのユーザー <br>&nbsp;&nbsp; &nbsp;(これは既定の設定です) <br/> <input type="checkbox">特定の人 <br>&nbsp;&nbsp; &nbsp;(コメント] 列に指定します)。 | |
> | Teams でセキュリティおよびコンプライアンスの機能を使用していますか? | <input type="checkbox">うん <br/> <input type="checkbox">違います | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (該当する場合)

該当する場合、次のサンプル テーブルを使用して、Skype をオンライン ビジネスの展開の詳細をキャプチャします。 Skype のオンライン ビジネスの展開を配置していない場合は、このセクションをスキップします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Skype にどのような種類のユーザーが有効になっています。 <br>オンラインのビジネスですか。 | <input type="checkbox">組織内のすべてのユーザー <br/> <input type="checkbox">特定のユーザーまたはユーザー グループ <br>&nbsp;&nbsp; &nbsp;([コメント] 列を指定してください) | |
> | 現在はどのような形式と機能 <br>現在使用中ですか。 | <input type="checkbox">インスタント メッセージングとプレゼンス (IM P)<br/> <input type="checkbox">会議 <br/> <input type="checkbox">フェデレーション <br/> <input type="checkbox">ミーティングのレコーディング <br/> <input type="checkbox">Microsoft オーディオ会議 <br/> <input type="checkbox">サード ・ パーティ製のオーディオ会議 <br>&nbsp;&nbsp; &nbsp;(詳細については、[コメント] 列に注意してください)。 <br/> <input type="checkbox">通話プラン (以前の PSTN の呼び出し) <br/> <input type="checkbox">組織の自動応答 <br/> <input type="checkbox">呼び出しキュー | |
> | 具体的にブロックしたすべての Skype <br>ビジネス オンライン機能でしょうか。 <br>[はい]、[コメント] 列に詳細に注意してください。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | 使用するかを使用する計画は、どのような方法 <br>電話システム (以前はクラウド PBX) に接続します。 <br>PSTN でしょうか。 <br/>該当するものすべてを選択します。 | <input type="checkbox">通話プラン (以前の PSTN の呼び出し) <br/> <input type="checkbox">設置 (利用する既存の PSTN への接続 <br>&nbsp;&nbsp; &nbsp;ビジネス 2015年または Lync Server 2013 の Skype <br>&nbsp;&nbsp; &nbsp;展開) <br/> <input type="checkbox">設置 PSTN への接続 (クラウドのコネクタを使用して) | |
> | マイクロソフトに移行した電話番号はありますか? <br/>これは、計画を呼び出すと、オーディオに適用 <br>会議の機能です。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype ビジネスの設置 (存在する場合)

該当する場合は、次のサンプル テーブルを使用してビジネス展開するため、Skype の詳細をキャプチャします。 設置型のビジネスを Skype を配置していない場合は、このセクションをスキップします。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | 現在 Lync またはビジネス用の Skype のバージョン <br>導入、設置型とは | <input type="checkbox">Office Communications Server 2007「R1」 <br/> <input type="checkbox">Office 通信 Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">ビジネス サーバー 2015 の Skype <br/> <input type="checkbox">Skype ビジネス サーバー 2019 <br/> <input type="checkbox">Skype ビジネス クラウド コネクタ ・ エディションの | |
> | Skype for Business Online とのハイブリッドは構成されていますか? | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | この環境ホストされ、サードパーティによって管理されているでしょうか。 <br/>[はい]、[コメント] 列に詳細に注意してください。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | 形式と機能は現在使用中 <br>本日は。 | <input type="checkbox">インスタント メッセージングとプレゼンス (IM P) <br/> <input type="checkbox">会議 <br/> <input type="checkbox">フェデレーション <br/> <input type="checkbox">ミーティングのレコーディング <br/> <input type="checkbox">永続的なチャット グループ チャット/ <br/> <input type="checkbox">Microsoft オーディオ会議 <br>&nbsp;&nbsp; &nbsp;(以前ダイヤルイン会議) で、 <br>&nbsp;&nbsp; &nbsp;設置の Lync Server または <br>&nbsp;&nbsp; &nbsp;Skype ビジネスの展開 <br/> <input type="checkbox">サード ・ パーティ製のオーディオ会議 <br>&nbsp;&nbsp; &nbsp;(詳細については、[コメント] 列に注意してください) <br/> <input type="checkbox">エンタープライズ VoIP を使用してオンプレミス PSTN <br>&nbsp;&nbsp; &nbsp;の接続 <br/> <input type="checkbox">通話プラン (以前の PSTN の呼び出し) を使用して <br>&nbsp;&nbsp; &nbsp;オンライン ビジネスの Skype でのハイブリッド | |
> | 展開済みの Edge Server のバージョンはいくつですか? | <input type="checkbox">Office Communications Server 2007「R1」 <br/> <input type="checkbox">Office 通信 Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">ビジネス サーバー 2015 の Skype <br/> <input type="checkbox">Skype ビジネス サーバー 2019 | |
> | 持っている Lync または Skype ビジネス エッジの展開の <br>1 つ以上のデータ センターですか。 <br/>[はい]、[コメント] 列に詳細に注意してください。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | 今日、エッジの役割を提供するサービスを選択します。 | <input type="checkbox">外部ユーザー アクセス (企業ユーザー) <br/> <input type="checkbox">(匿名の外部のリモート ユーザー アクセス <br>&nbsp;&nbsp; &nbsp;ミーティングの参加者) <br/> <input type="checkbox">フェデレーション <br/> <input type="checkbox">メディア リレー | |
> | 次の音声機能を呼び出すことの <br>現在依存関係があるでしょうか。 <br/>コメントの追加の依存関係に注意してください。 <br>列。 | <input type="checkbox">使用中のオプション <br/> <input type="checkbox">パーク <br/> <input type="checkbox">ピックアップまたはグループのコール ピックアップ <br/> <input type="checkbox">共通領域電話、または「ホットデスク」 <br/> <input type="checkbox">応答グループまたはハント グループ <br/> <input type="checkbox">共有行の外観 <br/> <input type="checkbox">専用回線 <br/> <input type="checkbox">ボイスメール <br/> <input type="checkbox">作業を使用して通話. <br/> <input type="checkbox">緊急時または情報の番号 <br>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox">拡張ダイヤル <br/> <input type="checkbox">自動応答 <br/> <input type="checkbox">サブスクライバー アクセス <br/> <input type="checkbox">アナログ デバイス <br/> <input type="checkbox">Fax <br/> <input type="checkbox">呼び出し元 ID のマスキングまたは変更します。 <br/> <input type="checkbox">場所ベースのルーティング <br/> <input type="checkbox">最低コスト ルーティング <br/> <input type="checkbox">エレベーターの電話 | |

## <a name="networking-and-access-to-office-365-services"></a>ネットワークと Office 365 サービスへのアクセス

次の表を使用して、組織のネットワークの詳細情報と、ユーザーをキャプチャする (または、) Office 365 サービスに接続します。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | 方法はなど、どのような移行のためのスコープ内のユーザー <br>オフィスにいるときにチームにアクセスしますか。 <br/>該当するものすべてを選択します。 | <input type="checkbox">NAT のルーティングされた接続 <br/> <input type="checkbox">プロキシ サーバー <br/> <input type="checkbox">パブリック Wi-fi <br/> <input type="checkbox">(パブリック) の Wi-fi を管理 <br/> <input type="checkbox">(マイクロソフトのピアリング) ExpressRoute ||
> | Office 365 へのアクセスがプロキシ サーバー経由の場合があります。 <br>プロキシをバイパスする方法ですか。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | ExpressRoute は現在使用されていますか? | <input type="checkbox">うん <br/> <input type="checkbox">違います <br/> <input type="checkbox">残念ですが、それを計画していますが、 | |
> | ネットワーク対応の評価を実施したことでしょうか。 <br/>詳細については、[ネットワーク対応の評価](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)を参照してください。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | 接続時に VPN を使用するために必要なユーザーは、します。 <br>社内リソース リモートですか。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | 場合は、VPN を使用すると、チームのトラフィックから除外すること <br>Office 365 サービスに直接アクセスする VPN ですか。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | お使いのネットワークは QoS をサポートしていますか? | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | チームのオーディオおよびビデオのトラフィックを優先することができます。 <br>高品質のドライブを次のように発生しますか。 | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | 領域内のすべての場所でインターネットの出口があります。 <br>または地域全体のインターネットの出口が集中しますか。 | <input type="checkbox">インターネットへのアクセスを地域 <br/> <input type="checkbox">インターネットへのアクセスを集中管理 | |

> [!TIP]
> 帯域幅と、クラウドの声の場合は、他のネットワーク要件の量を計算するために配置、組織の詳細と推定の使用状況によっては[MyAdvisor](https://myadvisor.fasttrack.microsoft.com/)では、[ネットワークの計画](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)を参照してください。

## <a name="endpoints"></a>エンドポイント

クライアントと使用中のエンドポイントの詳細を取得するのにには、次の表を使用します。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | ユーザーが使用しているデスクトップ OS は何ですか? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac ([コメント] 列でバージョンを指定します。) <br/> <input type="checkbox">他の (詳細については、[コメント] 列に注意してください)。 | |
> | Microsoft Office のバージョンを展開します。 <br>これらのデバイスですか。 | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office for Mac 2011 <br/> <input type="checkbox">2016年 Office for Mac <br/> <input type="checkbox">他の (詳細については、[コメント] 列に注意してください)。 | |
> | Office の展開テクノロジは使用されています。 <br>組織でしょうか。 | <input type="checkbox">MSI <br/> <input type="checkbox">クイック実行 | |
> | どのような許可は、モバイル サポート <br>使用中のプラットフォームですか。 <br/>該当するものすべてを選択します。 | <input type="checkbox">Windows <br/> <input type="checkbox"> 携帯電話 <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">他の (詳細については、[コメント] 列に注意してください)。 | |
> | モバイル デバイスはどのように提供されますか? <br/>該当するものすべてを選択します。 | <input type="checkbox">企業のデバイス <br/> <input type="checkbox">独自のデバイスを表示します。 | |
> | どのようなデバイスはユーザーが現在のアクセスに使用 <br>音声会議サービス <br>(ハンドセット、ヘッドセット、電話、ビデオ) でしょうか。 | | |

## <a name="operations"></a>運用

環境の運用上の側面の詳細を取得するのにには、次の表を使用します。

> | 質問 | 回答 | コメント |
> |---|---|---|
> | Lync サーバーの運用モデルとは <br>Skype ビジネス サーバー、または Office 365 の展開 <br>本日は。 | | |
> | 現在のサポート契約をアウトラインすることができます。 <br>Lync Server では、ビジネス サーバー、または Office 365 の Skype ですか。 | | |
> | 複数の国や地域に導入する場合 <br>それぞれの国や地域が独自の IT とテレフォニー <br>スタッフを扱う、またはこれを管理する集中的にでしょうか。 | <input type="checkbox">地域の運用とサポート <br/> <input type="checkbox">一元的なオペレーションおよびサポート | |
> | [品質方法論の呼び出し](quality-of-experience-review-guide.md)の後ですか? | <input type="checkbox">うん <br/> <input type="checkbox">違います | |
> | 割り当てられている個人やチームに、 <br>コラボレーション プラットフォームの品質チャンピオンの役割 <br>使用中ですか。 | <input type="checkbox">うん <br/> <input type="checkbox">違います ||
> | Skype、Lync Server を監視します。 <br>ビジネス サーバー、または Office 365 の展開ですか。 | | |
> | 通話品質の問題を経験しましたか? | <input type="checkbox">うん<br/> <input type="checkbox">違います | |
> | 時期と方法を提供してトレーニングを <br>新しいサービスや機能のヘルプ デスクですか。 | | |

## <a name="adoption-and-readiness"></a>導入と準備

次の表を使用して、自分の組織での現在の導入と準備状況を記録してください。

>
> | 質問 | 回答 | コメント |
> |---|---|---|
> | 現在のアクティブな使用状況とは <br>ビジネスの Skype ですか。 | **_ _** % アクティブなユーザーの総数と有効なユーザー | |
> | 組織はどのように使用します。 <br>ビジネスの Skype ですか。 | 1 対 1 の会話 <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> IM <br>&nbsp;&nbsp; &nbsp; <input type="checkbox">を呼び出す <br>&nbsp;&nbsp; &nbsp; <input type="checkbox">の共有<br> 会議 <br>&nbsp;&nbsp; &nbsp; <input type="checkbox">会議<br>&nbsp;&nbsp; &nbsp; <input type="checkbox">の共有<br>&nbsp;&nbsp; &nbsp; <input type="checkbox">を呼び出す | |
> | 組織がユーザーの導入 <br>変更管理チームが必要ですか。 | <input type="checkbox">うん<br/> <input type="checkbox">違います | |
> | どのようにして現在の技術の評価 <br>ビジネス用の Skype と同じように展開しますか。 | | |
> | ユーザー ベースの割合をお答えには <br>ビジネス用の Skype を採用しますか。 | | |
> | Skype for Business についてのユーザーの感想を教えてください。 | <input type="checkbox">よし <br/> <input type="checkbox">ニュートラル <br/> <input type="checkbox">不良 | |
> | ロールアウトを表しているは次の <br>ビジネスのため、Skype の使用方法 <br>展開でしょうか。 | <input type="checkbox">幅広い: を使用してキャンペーンの電子メールを送信 <br>&nbsp;&nbsp; &nbsp;トレーニングへのリンク <br/> <input type="checkbox">幅広いと様々 なを展開します。 <br>&nbsp;&nbsp; &nbsp;の意識向上キャンペーン (ポスター、 <br>&nbsp;&nbsp; &nbsp;イベント、チャンピオン) とトレーニング <br>&nbsp;&nbsp; &nbsp;(ビデオ、ユーザー ガイド、ユーザーに) <br/> <input type="checkbox">合わせて調整します。 展開すると対象に <br>&nbsp;&nbsp; &nbsp;メッセージングおよびペルソナによるトレーニング <br/> <input type="checkbox">その他の <br>&nbsp;&nbsp; &nbsp;(詳細については、[コメント] 列に注意してください)。 | |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>判断ポイント</td><td><ul><li>環境の評価を完了するため管理するはだれですか。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>次のステップ</td><td><ul><li>環境アセスメントの結果を文書化します。</li></ul></td></tr>
</table>

お客様の環境を評価した後は、次の手順に進みます:[ネットワークを準備](upgrade-prepare-environment-prepare-network.md)します。