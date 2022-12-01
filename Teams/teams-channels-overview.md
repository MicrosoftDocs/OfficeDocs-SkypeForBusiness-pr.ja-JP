---
title: Microsoft Teams でのチームとチャネルの概要
author: MikePlumleyMSFT
ms.author: mikeplum
ms.reviewer: ''
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-chat
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
- intro-overview
- chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1cfbda5204e9294dd202440bbcd53b343cafe96f
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198709"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Microsoft Teams でのチームとチャネルの概要

はじめに、Microsoft Teams が各チームの自己組織化と、複数のビジネス シナリオにわたる共同作業をどのように実現しているかについて考えましょう。

- **Teams** は、組織内のさまざまなプロジェクトや成果を取り巻く人、コンテンツ、およびツールの集合です。

    - 招待されたユーザーだけが対象の非公開チームを作成することもできます。
    - チームは公開の形で作成することもでき、組織内の誰でも参加できます（最大 10,000 人のメンバー）。
    
    チームは、何かの仕事を完成させるために緊密に作業している人たちを 1 つにまとめるために設計されています。 Teams はプロジェクト単位の作業 (製品の立ち上げや、デジタル作戦指令室を作るなど) において、現在進行中の作業も含めて、組織の内部構造 (たとえば、部署やオフィスの場所など) を反映して、動的に機能します。 複数のチーム チャネルにわたる会話、ファイル、ノートはチームのメンバーだけが見ることができます。

- **チャネル** は、チーム内の専用セクションで、チームで機能しているすべてのことについて、たとえば特定のトピック、プロジェクト、分野などの別に会話をまとめ、保存します。 ([ファイル] タブで) チャネルで共有するファイルは、SharePoint に保存されます。 詳細については、「[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](SharePoint-OneDrive-interact.md)」をご覧ください。

    - チャネルは、会話がなされ、実際に作業が行われる場所です。 チャネルは、すべてのチーム メンバー (標準チャネル)、選択したチーム メンバー ([プライベート チャネル](private-channels.md))、またはチームの内部と外部の両方の選択されたユーザー ([共有チャネル](shared-channels.md)) に公開することができます。
    - チャネルは、タブ、コネクタ、およびボットを含んでいるアプリで拡張することで最大の価値を発揮するようになり、チームのメンバーにとってのチャネルの価値が高まります。 詳細については、「 [Teams アプリの概要](deploy-apps-microsoft-teams-landing-page.md)」を参照してください。
    
チームとチャネルの使用に関するヘルプについては、「[チームとチャネル](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499)」をご覧ください。

Teams の使用に関する制限については、「[Microsoft Teams の制限事項と仕様](/microsoftteams/limits-specifications-teams)」を参照してください。

## <a name="membership-roles-and-settings"></a>メンバーシップ、ロール、および設定

**チーム メンバーシップ**

Teams が組織全体に対してアクティブ化されると、チーム所有者は、組織内の誰でもチームに参加するように招待できます。 Teams では、チーム所有者が組織内のユーザーを名前に基づいて追加することが簡単に行えます。 組織の設定に応じて、組織外のユーザーをゲストとして、または共有チャネルの外部参加者としてチームに追加できます。 詳細については、「[Microsoft Teams でのゲスト アクセス](guest-access.md)」をご覧ください。 

チーム所有者は、既存の Microsoft 365 グループに基づいてチームを作成することもできます。 グループ メンバーシップに対するいかなる変更も、Teams に自動的に同期されます。

**チームの役割**

Teams には、次の 2 つの主な役割があります。 

- **チーム所有者** - チームを作成するユーザーです。 チーム所有者は、チームのメンバーをチームに招待した時点またはチームに参加した後に、共同所有者にすることができます。 複数のチーム所有者がいると、招待などの設定やメンバーシップの管理の負担を分散できるようになります。
- **チーム メンバー** - 所有者が自分のチームに招待したユーザーです。

また、モデレートが設定されている場合、チームの所有者とメンバーには、チャネルに対するモデレーターの機能を割り当てることができます。 モデレーターは、チャネルで新しい投稿を開始することと、チームのメンバーが既存のチャネル メッセージに返信できるようするかどうかを制御することができます。 チーム所有者は、チャネル内にモデレーターを割り当てることができます。 (既定では、チーム所有者はモデレーター機能を所有しています。) チャネル内のモデレーターは、チャネル内の他のモデレーターを追加または削除できます。 詳細については、「[Microsoft Teams でチャネル モデレーションをセットアップして管理する](manage-channel-moderation-in-teams.md)」をご覧ください。

> [!NOTE]
> チーム所有者を追加すると、Teams 管理センターでチームが作成された場合、またはチームが新規または既存の Microsoft 365 グループに追加された場合を除いて、メンバーとしても追加されます。

**チームの設定** 

Team owners can manage team-wide settings directly in Teams. Settings include the ability to add a team picture, set permissions across team members for creating standard, private, and shared channels, adding tabs and connectors, @mentioning the entire team or channel, and the usage of GIFs, stickers, and memes.

Microsoft 365 での Teams 管理者である場合は、Teams 管理センターのシステム全体の設定にアクセスすることができます。 これらの設定は、チーム設定でチーム所有者に表示されるオプションと既定値に影響します。 たとえば、チーム全体の通知、ディスカッション、リソースのために、既定のチャネル「一般」を有効にして、それらがすべてのチームにわたって表示されるようにすることができます。

既定では、すべてのユーザーにチームを作成するアクセス許可があります。 これを変更するには、「[Teams での役割とアクセス許可の割り当て](assign-roles-permissions.md)」を参照してください。

ユーザーを Teams に関与させるために鍵となる初期段階の計画アクティビティは、日々の生活で Teams がどのようにコラボレーションを深めているのかについて、洞察と理解を促進することです。 ユーザーと話し合い、断片的な方法で現在共同作業を行っている状況でビジネス シナリオを選択できるように支援します。 ユーザーたちが作業を完了するために役に立つ関連するタブとともに、それらのユーザーをチャネルに取り込みます。 Teams の最も強力なユース ケースの 1 つは、あらゆる組織横断型のプロセスです。

> [!NOTE]
> Teams で新しいチームやプライベート チャネル、または共有チャネルを作成すると、SharePoint のチーム サイトが自動的に作成されます。 このチーム サイトのサイトの説明または分類を編集するには、対応するチャネルの [Microsoft Teams の設定](https://support.microsoft.com/office/bf39798f-90d2-44fb-a750-55fa05a56f1d)に移動します。
>
> [Microsoft Teams に接続されたチーム サイト](/SharePoint/teams-connected-sites)の管理についての詳細情報をご覧ください。

このビデオでは、ユーザーのチーム メンバーシップを表示および管理する手順を示します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE53x1L?autoplay=false]

## <a name="channel-feature-comparison"></a>チャネル機能の比較

次の表は、チャネルの種類ごとの Teams 機能の比較を示しています。

|機能|標準チャネル|プライベート チャネル|共有チャネル|
|:-------|:---------------|:--------------|:-------------|
|チームに追加しなくても、ユーザーをチャネルに追加することができます。|いいえ|いいえ|はい|
|チャネル メンバーシップは、チームのサブセットに制限できます。|いいえ|Yes|はい|
|チャネルは、他のチームと直接共有できます。|いいえ|いいえ|はい|
|チャネルは、その親チームと直接共有できます。|該当なし|いいえ|はい|
|ゲストはチャネルに参加できます。|はい|Yes|いいえ|
|外部参加者 (B2B Direct Connect) は、チャネルに参加できます。|いいえ|いいえ|Yes|
|モデレート|はい|いいえ|いいえ|
|ブレークアウト ルーム|Yes|いいえ|いいえ|
|チャネルへのリンクをコピー|はい|いいえ|いいえ|
|各チャネルには専用の SharePoint サイトがあります。|いいえ|Yes|はい|
|予約された会議|はい|いいえ|はい|
|プランナー|はい|いいえ|いいえ|
|ボット、コネクタ、およびメッセージングの拡張機能|はい|いいえ|いいえ|
|クラス チームでサポートされています|はい|Yes|いいえ|
|タグ|はい|いいえ|いいえ|
|分析|はい|Yes|いいえ|

## <a name="org-wide-teams"></a>組織全体のチーム

組織のユーザー数が 10,000 以下の場合は、組織全体でチームを作成できます。 組織全体のチームは、組織内の全員がコラボレーションのための単一チームの一部に自動的なれる方法を提供します。 組織全体のチームを作成および管理するための、ベストプラクティスを含む詳細については、[Microsoft Teams で組織全体のチームを作成する](create-an-org-wide-team.md)を参照してください。

## <a name="next-steps"></a>次の手順

[Microsoft Teams のチャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)に進み、Teams の立ち上げに重要な決定事項のリストを確認します。
