---
title: Microsoft Teams でのチームとチャネルの概要
author: LolaJacobsen
ms.author: lolaj
ms.reviewer: ''
manager: serdars
ms.date: 06/20/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
description: 財務、イベント計画、販売など、多岐にわたる要件で利用できるさまざまなチーム、チャネル、アプリについて紹介します。
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.teamschannel.overview
- ms.teamsadmincenter.teamssettings.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c63dd69553d722612e8fc661671e95a6c0ee860
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221552"
---
> [!NOTE]
> 以下の情報を確認して、Teamsでのチャット、チーム、チャンネル、およびアプリを理解してください。 次に、[チャット、チーム、チャネル、チーム内のアプリの &](deploy-chat-teams-channels-microsoft-teams-landing-page.md)に移動して、チームのロールアウトにとって重要な決定事項の一覧を表示します。

<a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Microsoft Teams でのチームとチャネルの概要
=================================================

はじめに、Microsoft Teams が各チームの自己組織化と、複数のビジネス シナリオにわたる共同作業をどのように実現しているかについて考えましょう。

-   **Teams**は、組織内のさまざまなプロジェクトや成果を取り巻く人、コンテンツ、およびツールの集合です。

    -   招待されたユーザーだけが対象の非公開チームを作成することもできます。

    -   チームは公開の形で作成することもでき、そうすれば組織内の誰でも参加できます（最大5000人のメンバー）。
    
    チームは、何かの仕事を完成させるために緊密に作業している人たちを 1 つにまとめるために設計されています。 Teams はプロジェクト単位の作業 (製品の立ち上げや、デジタル作戦指令室を作るなど) において、現在進行中の作業も含めて、組織の内部構造 (たとえば、部署やオフィスの場所など) を反映して、動的に機能します。 チームチャネル間での会話、ファイル、メモは、チームのメンバーのみに表示されます。

-   **チャネル**は、チーム内の専用セクションで、チームで機能しているすべてのことについて、たとえば特定のトピック、プロジェクト、分野などの別に会話をまとめ、保存します。 チャネルで共有するファイル ([ファイル] タブ) は、SharePoint に保存されます。 詳細については、「 [SharePoint Online と OneDrive For business が Teams を操作する方法](SharePoint-OneDrive-interact.md)」を参照してください。

    -   チームチャネルは、チームの全員が会話を利用できる場所です。 プライベートチャットは、チャット内のユーザにのみ表示されます (チャットで共有するファイルは OneDrive for Business に保存されています)。

    -   チャネルは、タブ、コネクタ、およびボットを含んでいるアプリで拡張することで最大の価値を発揮するようになり、チームのメンバーにとってのチャネルの価値が高まります。 詳細については、「 [Teams のアプリ、ボット、& コネクタ](deploy-apps-microsoft-teams-landing-page.md)」を参照してください。

チームとチャネルを作成するためのベストプラクティスの詳細について、この短いビデオをご覧ください。

   > [!VIDEO https://www.youtube.com/embed/hjJWtoaRJeE]

<a name="membership-roles-and-settings"></a>メンバーシップ、ロール、および設定
------------------------------

**チームメンバーシップ**組織全体で Microsoft Teams がアクティブ化されると、指定されたチーム所有者は、チームに参加するために共同作業する従業員を招待することができます。 Microsoft Teams では、チーム所有者が組織内のユーザーを名前に基づいて追加することが簡単に行えます。 組織の設定によっては、組織外のチームメンバーであるゲストをチームに追加することもできます。 詳細については、「[Microsoft Teams でのゲスト アクセス](guest-access.md)」をご覧ください。

チーム所有者は、既存の Office 365 グループに基づいてチームを作成することもできます。 グループに加えた変更は、Microsoft Teams と自動的に同期されます。 既存の Office 365 グループに基づいてチームを作成することで、メンバーの招待や管理のプロセスが簡素化されるだけでなく、Microsoft Teams の内部のグループ ファイルの動機も行われます。

**チームの役割**Microsoft Teams には主に次の2つの役割があります。チーム所有者、チームを作成したユーザー。チームメンバー (チームに参加するよう招待したユーザー) チーム所有者は、チームのメンバーを、チームに招待した時点またはチームに参加した後に、共同所有者にすることができます。 複数のチーム所有者がいると、招待を含む、設定やメンバーシップの管理の責任を分散することができます。

**チームの設定**チーム所有者は、Microsoft Teams でチーム全体の設定を直接管理できます。 設定には、チームの画像を追加する機能、チームメンバー間でチャネルの作成、タブとコネクタの追加、チーム全体またはチャネルの @mentioning、Gif、ステッカー、ミームの使用などがあります。 

3分で、チームオーナー向け必須ガイドのビデオをチェックしましょう。 

   > [!VIDEO https://www.youtube.com/embed/7XcDSuw6NR4]

Office 365 での Microsoft Teams 管理者である場合は、Microsoft Teams 管理センターのシステム全体の設定にアクセスすることができます。 これらの設定は、チーム設定でチーム所有者に表示されるオプションと既定値に影響します。 たとえば、チーム全体のアナウンス、ディスカッション、リソースの既定のチャネル "全般" を有効にして、すべてのチームに表示されるようにすることができます。

既定では、すべてのユーザーが Microsoft Teams 内にチームを作成する権限を持っています (これを変更するには、「[Teams で役割と権限を割り当てる](assign-roles-permissions.md)」をご覧ください)。 既存の Office 365 グループのユーザーは、Teams 機能を使用してアクセス許可を強化することもできます。

ユーザーを Microsoft Teams に関与させるために鍵となる初期段階の計画アクティビティは、日々の生活で Teams がどのようにコラボレーションを深めているのかについて、洞察と理解を促進することです。 ユーザーと話し合い、断片的な方法で現在共同作業を行っている状況でビジネス シナリオを選択できるように支援します。 ユーザーたちが作業を完了するために役に立つ関連するタブとともに、それらのユーザーをチャネルに取り込みます。 Teams の最も強力なユース ケースの 1 つは、あらゆる組織横断型のプロセスです。 

<a name="example-teams"></a>チームの例
--------------

ここでは、さまざまな種類のユーザーがチーム、チャネル、およびアプリ (タブ/コネクタ/ボット) を設定する方法について、いくつかの機能の例を示します。 これは、ユーザーコミュニティで Microsoft Teams についての会話を開始するのに役立ちます。 組織に Microsoft Teams を実装する方法について考えている場合は、チームの構造についてのガイダンスを提供できることを覚えておいてください。ただし、ユーザーは自己組織化の方法を制御できます。 次に示すのは、teams でその可能性について考えるための例です。

Microsoft Teams は、縦割り組織を解体して機能横断型チームを促進することに優れています。このため、ユーザーは縦割り組織ではなく機能的なチームとして考える意識が高まります。

|チームのタイプ  |考えられるチャネル  |アプリ (タブ ![タブでフォルダーを示すアイコン](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image2.png)/コネクタ ![接続ブロックを示すアイコン](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image3.png)/ボット ![小さいロボットを示すアイコン](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image4.png))  |
|---------|---------|---------|
|売上     |年次販売会議<br></br> 四半期ビジネス レビュー<br></br> 月次売上パイプライン レビュー<br></br> 売上戦略 |Power BI<br></br>Trello<br></br>CRM<br></br>サマライズ ボット         |
|広報活動     |プレス リリース<br></br>ニュースおよび更新情報<br></br>ファクト チェック         |RSS フィード<br></br>Twitter         |
|イベント計画     |マーケティング<br></br>物流およびスケジュール<br></br>会場<br></br>予算         |ツイッター<br></br>Facebook<br></br>プランナー<br></br>PDF         |
|マーケティング/市場開拓   |市場調査<br></br>メッセージ ピラー<br></br>コミュニケーション プラン<br></br>部品表のマーケティング        |YouTube<br></br>Microsoft Stream<br></br>Twitter<br></br>MailChimp         |
|技術運用    |インシデント管理<br></br>スプリント計画<br></br>作業項目<br></br>インフラストラクチャおよび運用         |Team Services<br></br>Jira<br></br>AzureBot         |
|製品チーム      |戦略<br></br>マーケティング<br></br>売上<br></br>操作<br></br>分析情報<br></br>サービスとサポート         |Power BI<br></br>チーム サービス         |
|Finance    |現会計年度<br></br>年度計画<br></br>予測<br></br>売掛金<br></br>買掛金         |Power BI<br></br>Google アナリティクス         |
|物流     |倉庫管理<br></br>車両整備<br></br>ドライバー勤務表         |気象サービス<br></br>トラベル/道路混乱<br></br>プランナー<br></br>Tubot<br></br>UPS ボット         |
|人事     |人材管理<br></br>採用<br></br>業績レビュー計画<br></br>士気         |HR ツール<br></br>外部の求人サイト<br></br>Growbot         |
|組織横断型 <br></br>仮想チーム |戦略<br></br>人材育成<br></br>競争と研究         |Power BI<br></br>Microsoft Stream         |

組織構造に合わせてチームを作成することができます。 これは、morale を運転したり、チーム特定レビューしたり、従業員のオンボードプロセスを明確にしたり、労働力の計画について話し合い、さまざまな従業員に対する視程を高めたりするリーダーに最適です。  

![Microsoft Teams で編成されたチームとチャネルの階層図。](media/overview-of-teams-and-channels-image1.png)

## <a name="org-wide-teams"></a>組織全体のチーム

組織のユーザー数が 5,000以下の場合は、組織全体でチームを作成できます。 組織全体のチームは、組織内の全員がコラボレーションのための単一チームの一部に自動的なれる方法を提供します。 組織全体のチームを作成および管理するための、ベストプラクティスを含む詳細については、[Microsoft Teams で組織全体のチームを作成する](create-an-org-wide-team.md)を参照してください。
