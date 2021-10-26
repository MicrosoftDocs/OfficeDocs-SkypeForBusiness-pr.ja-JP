---
title: Microsoft Teams でのチームとチャネルの概要
author: MikePlumleyMSFT
ms.author: mikeplum
ms.reviewer: ''
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 財務、イベント計画、販売など、多岐にわたる要件で利用できるさまざまなチーム、チャネル、アプリについて紹介します。
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.msteamsfiles
- ms.teamsadmincenter.dashboard.helparticle.teamsandchannels
- ms.teamsadmincenter.teamschannel.overview
- ms.teamsadmincenter.teamssettings.overview
- okr_smb
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34c255dab5f2f231735abeba9a03ed091d10c205
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536568"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Microsoft Teams でのチームとチャネルの概要

はじめに、Microsoft Teams が各チームの自己組織化と、複数のビジネス シナリオにわたる共同作業をどのように実現しているかについて考えましょう。

- **Teams** は、組織内のさまざまなプロジェクトや成果を取り巻く人、コンテンツ、およびツールの集合です。

    - 招待されたユーザーだけが対象の非公開チームを作成することもできます。
    - チームは公開の形で作成することもでき、組織内の誰でも参加できます（最大 10,000 人のメンバー）。
    
    チームは、何かの仕事を完成させるために緊密に作業している人たちを 1 つにまとめるために設計されています。 Teams はプロジェクト単位の作業 (製品の立ち上げや、デジタル作戦指令室を作るなど) において、現在進行中の作業も含めて、組織の内部構造 (たとえば、部署やオフィスの場所など) を反映して、動的に機能します。 複数のチーム チャネルにわたる会話、ファイル、ノートはチームのメンバーだけが見ることができます。

- **チャネル** は、チーム内の専用セクションで、チームで機能しているすべてのことについて、たとえば特定のトピック、プロジェクト、分野などの別に会話をまとめ、保存します。 ([ファイル] タブで) チャネルで共有するファイルは、SharePoint に保存されます。 詳細については、「[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](SharePoint-OneDrive-interact.md)」をご覧ください。

    - チャネルは、会話がなされ、実際に作業が行われる場所です。 チャネルはすべてのチーム メンバーに公開することができ、対象ユーザーを限定する必要がある場合は、プライベートにすることもできます。 標準チャネルは、チーム内のすべてのユーザーが参加できる会話向けであり、[プライベート チャネル](private-channels.md)は、会話をチーム内の少人数のユーザーに限定します。
    - チャネルは、タブ、コネクタ、およびボットを含んでいるアプリで拡張することで最大の価値を発揮するようになり、チームのメンバーにとってのチャネルの価値が高まります。 詳細については、「[Microsoft Teams のアプリ、ボット、およびコネクタ](deploy-apps-microsoft-teams-landing-page.md)」をご覧ください。
    
チームとチャネルの使用に関するヘルプについては、「[チームとチャネル](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499)」をご覧ください。

チームとチャネルを作成するためのベストプラクティスの詳細について、この短いビデオをご覧ください。

- [TechTip: Microsoft Teams でプライベート チャネルを含む Teams とチャネルを作成するためのガイダンス](https://youtu.be/WkAVgNKn0hs) (21:08分)

## <a name="membership-roles-and-settings"></a>メンバーシップ、ロール、および設定

**チーム メンバーシップ**

Teams が組織全体に対してアクティブ化されると、チーム所有者は、組織内の誰でもチームに参加するように招待できます。 Teams では、チーム所有者が組織内のユーザーを名前に基づいて追加することが簡単に行えます。 組織の設定に応じて、組織外のユーザーをゲストとしてチームに追加できます。 詳細については、「[Microsoft Teams でのゲスト アクセス](guest-access.md)」をご覧ください。 

チーム所有者は、既存の Microsoft 365 グループに基づいてチームを作成することもできます。 グループ メンバーシップに対するいかなる変更も、Teams に自動的に同期されます。

**チームの役割**

Teams には、次の 2 つの主な役割があります。 

- **チーム所有者** - チームを作成するユーザーです。 チーム所有者は、チームのメンバーをチームに招待した時点またはチームに参加した後に、共同所有者にすることができます。 複数のチーム所有者がいると、招待などの設定やメンバーシップの管理の負担を分散できるようになります。
- **チーム メンバー** - 所有者が自分のチームに招待したユーザーです。

また、モデレートが設定されている場合、チームの所有者とメンバーには、チャネルに対するモデレーターの機能を割り当てることができます。 モデレーターは、チャネルで新しい投稿を開始することと、チームのメンバーが既存のチャネル メッセージに返信できるようするかどうかを制御することができます。 チーム所有者は、チャネル内にモデレーターを割り当てることができます。 (既定では、チーム所有者はモデレーター機能を所有しています。) チャネル内のモデレーターは、チャネル内の他のモデレーターを追加または削除できます。 詳細については、「[Microsoft Teams でチャネル モデレーションをセットアップして管理する](manage-channel-moderation-in-teams.md)」をご覧ください。

> [!NOTE]
> チーム所有者を追加すると、Teams 管理センターでチームが作成された場合、またはチームが新規または既存の Microsoft 365 グループに追加された場合を除いて、メンバーとしても追加されます。

**チームの設定** 

チームの所有者は、チーム全体の設定を直接 Teams で管理できます。この設定には、チームの写真の追加や、標準および[プライベート チャネル](private-channels.md)を作成したり、タブとコネクタを追加したり、チームまたはチャネル全体を @メンションしたりするためのチーム メンバーにわたるアクセス許可の設定や、GIF、ステッカー、ミームの使用が含まれます。

Microsoft 365 での Teams 管理者である場合は、Teams 管理センターのシステム全体の設定にアクセスすることができます。 これらの設定は、チーム設定でチーム所有者に表示されるオプションと既定値に影響します。 たとえば、チーム全体の通知、ディスカッション、リソースのために、既定のチャネル「一般」を有効にして、それらがすべてのチームにわたって表示されるようにすることができます。

既定では、すべてのユーザーがチームを作成するアクセス許可を持っています。これを変更するには、「[Teams でロールとアクセス許可を割り当てる](assign-roles-permissions.md)」をご覧ください。

ユーザーを Teams に関与させるために鍵となる初期段階の計画アクティビティは、日々の生活で Teams がどのようにコラボレーションを深めているのかについて、洞察と理解を促進することです。 ユーザーと話し合い、断片的な方法で現在共同作業を行っている状況でビジネス シナリオを選択できるように支援します。 ユーザーたちが作業を完了するために役に立つ関連するタブとともに、それらのユーザーをチャネルに取り込みます。 Teams の最も強力なユース ケースの 1 つは、あらゆる組織横断型のプロセスです。

> [!NOTE]
> Microsoft Teams で新しいチームまたはプライベート チャネルを作成すると、SharePoint のチーム サイトが自動的に作成されます。 このチーム サイトのサイトの説明または分類を編集するには、対応するチャネルの [Microsoft Teams の設定](https://support.microsoft.com/office/change-a-team-s-data-security-classification-in-teams-bf39798f-90d2-44fb-a750-55fa05a56f1d)に移動します。
>
> [Microsoft Teams に接続されたチーム サイト](/SharePoint/teams-connected-sites)の管理についての詳細情報をご覧ください。

## <a name="example-teams"></a>チームの例

以下に、さまざまなタイプのユーザーが、チーム、チャネルおよびアプリ (タブ/コネクタ/ボット) のセットアップにどのような方法を取ることができるかを示します。これは、Teams に関する会話をユーザー コミュニティと開始するにあたってサポートを提供する場合に役立ちます。組織に Teams をどのように実装するかを考える場合、提供できるのはチームの構築方法に関するガイダンスであって、自己組織化の方法はユーザーが管理するものであることを念頭に入れてください。以下は、チームが実行可能な方法について考えるにあたって、そのサポートをするサンプルとなります。

Teams は、縦割り組織を解体して機能横断型チームを促進することに優れています。このため、ユーザーは組織の境界ではなく機能的なチームとして考える意識が高まります。

|チームのタイプ  |考えられるチャネル  |アプリ (タブ ![タブがあるフォルダーを表すアイコン。](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image2.png)/コネクタ ![くっついたブロックを表すアイコン](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image3.png)/ボット ![小さなロボットを表すアイコン](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image4.png))  |
|---------|---------|---------|
|売上     |年次販売会議<br></br> 四半期ビジネス レビュー<br></br> 月次売上パイプライン レビュー<br></br> 売上戦略 |Power BI<br></br>Trello<br></br>CRM<br></br>サマライズ ボット         |
|広報活動     |プレス リリース<br></br>ニュースおよび更新情報<br></br>ファクト チェック         |RSS フィード<br></br>Twitter         |
|イベント計画     |マーケティング<br></br>物流およびスケジュール<br></br>会場<br></br>予算         |Twitter<br></br>Facebook<br></br>プランナー<br></br>PDF         |
|マーケティング/市場開拓   |市場調査<br></br>メッセージ ピラー<br></br>コミュニケーション プラン<br></br>部品表のマーケティング        |YouTube<br></br>Microsoft Stream<br></br>Twitter<br></br>MailChimp         |
|技術運用    |インシデント管理<br></br>スプリント計画<br></br>作業項目<br></br>インフラストラクチャおよび運用         |チーム サービス<br></br>Jira<br></br>AzureBot         |
|製品チーム      |戦略<br></br>マーケティング<br></br>売上<br></br>操作<br></br>分析情報<br></br>サービスとサポート         |Power BI<br></br>チーム サービス         |
|Finance    |現会計年度<br></br>年度計画<br></br>予測<br></br>売掛金<br></br>買掛金         |Power BI<br></br>Google アナリティクス         |
|物流     |倉庫管理<br></br>車両整備<br></br>ドライバー勤務表         |気象サービス<br></br>トラベル/道路混乱<br></br>プランナー<br></br>UPS ボット         |
|人事     |人材管理<br></br>採用<br></br>業績レビュー計画<br></br>士気         |HR ツール<br></br>外部の求人サイト<br></br>Growbot         |
|組織横断型 <br></br>仮想チーム |戦略<br></br>人材育成<br></br>競争と研究         |Power BI<br></br>Microsoft Stream         |

組織構造に整合する Teams を作成することができます。これは、士気の向上、チーム固有のレビューの実施、従業員のオンボーディング プロセスの明確化、人員の計画についての話し合い、およびさまざまな人員にわたっての視認性の改善を行うことを考えているリーダーにとって最適です。  

![チームとチャネルが Microsoft Teams 内でどのように編成されるかを示す階層図。](media/overview-of-teams-and-channels-image1.png)

## <a name="org-wide-teams"></a>組織全体のチーム

組織のユーザー数が 10,000 以下の場合は、組織全体でチームを作成できます。 組織全体のチームは、組織内の全員がコラボレーションのための単一チームの一部に自動的なれる方法を提供します。 組織全体のチームを作成および管理するための、ベストプラクティスを含む詳細については、[Microsoft Teams で組織全体のチームを作成する](create-an-org-wide-team.md)を参照してください。

## <a name="next-steps"></a>次の手順

[Microsoft Teams のチャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)に進み、Teams の立ち上げに重要な決定事項のリストを確認します。
