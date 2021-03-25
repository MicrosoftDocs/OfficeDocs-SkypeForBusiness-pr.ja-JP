---
title: 会議の設定を管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 組織のユーザーがスケジュールする Teams 会議の設定を管理する方法を説明します。
ms.openlocfilehash: a8fe3f0c2375e7322397fabfeb1d3f5456d7c55b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117895"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Microsoft Teams で会議の設定を管理する

管理者は Teams 会議の設定を使用することにより、Teams 会議への匿名ユーザーの参加可否、会議への招待状のカスタマイズ、およびサービスの品質 (QoS) をオンにするかどうかの制御を行え、リアルタイム トラフィックのポート範囲を設定することができます。 これらの設定は、組織のユーザーがスケジュールするすべての Teams 会議に適用されます。 これらの設定は、Microsoft Teams 管理センターの [**会議**] > [**会議設定**] から管理します。

## <a name="allow-anonymous-users-to-join-meetings"></a>匿名ユーザーによる会議への参加を許可する

匿名参加を許可した場合、会議への招待状に含まれるリンクをクリックすると、誰でも匿名ユーザーとして会議に参加することができます。 詳細については、「[Teams のアカウントなしに会議に参加する](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)」を参照してください。

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

これらの変更を行うには、Teams サービス管理者であることが必要です。 「[Teams 管理者ロールを使用してチームを管理する](./using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。

1. 管理センターにアクセスします。

2. 左側のナビゲーションで、[**会議**] > [**会議設定**] に移動します。

3. [**参加者**] の下で、[**匿名ユーザーが会議に参加できます**] をオンにします。

    ![管理センターでの会議の参加者設定のスクリーンショット](media/meeting-settings-participants.png "Microsoft Teams 管理センターでの Teams 会議の参加者設定のスクリーンショット")

> [!CAUTION]
> 組織のユーザーがスケジュールを行った会議に匿名ユーザーを参加させないようにするには、この設定をオフにします。

## <a name="allow-anonymous-users-to-interact-with-apps-in-meetings"></a>匿名ユーザーが会議でアプリを操作できるようにする

匿名ユーザーは、ユーザー レベルのグローバル既定アクセス許可ポリシーを継承するようになりました。 このコントロールにより、ユーザー レベルのアクセス許可ポリシーでアプリが有効になっている限り、匿名ユーザーが Teams 会議でアプリを操作できるようになります。 匿名ユーザーは、会議ですでに利用可能なアプリのみを操作でき、これらのアプリを取得または管理できないことに注意してください。 

> [!IMPORTANT]
> 既定では、匿名ユーザーが会議でアプリを操作できるようにする設定が有効になっています。

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

この設定にアクセスするには、Teams サービス管理者であることが必要です。 「[Teams 管理者ロールを使用してチームを管理する](./using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。

1. 管理センターにアクセスします。

2. 左側のナビゲーションで、[**会議**] > [**会議設定**] に移動します。

3. [**参加者**] の下で、[**匿名ユーザーが会議でアプリを操作できます**] の設定を変更できます。

> [!CAUTION]
> 組織のユーザーがスケジュールを行った会議で匿名ユーザーがアプリを操作しないようにするには、この設定をオフにします。

## <a name="customize-meeting-invitations"></a>会議への招待状をカスタマイズする

組織のニーズに合わせて Teams 会議への招待状をカスタマイズできます。 組織のロゴを加えたり、役立つ情報 (組織のサポート Web サイトへのリンク、法的免責事項、テキストのみのフッターなど) を含めたりすることができます。

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>会議の招待状用ロゴの作成ヒント  

1. 幅 188 ピクセル、高さ 30 ピクセル以内の、ごく小さな画像を作成します。
2. 画像を JPG または PNG 形式で保存します。
3. パブリック Web サイトなど、招待状を受け取るすべてのユーザーがアクセス可能な場所に画像を保存します。

    会議出席依頼に追加できるようになります。 方法については、次の手順を参照してください。

### <a name="customize-your-meeting-invitations"></a>会議の招待状をカスタマイズする

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 管理センターにアクセスします。
2. 左側のナビゲーションで、[**会議**] > [**会議設定**] に移動します。
3. [**招待メール**] で、次の操作を行います。

    ![カスタマイズ可能な会議の招待状設定のスクリーンショット](media/meeting-settings-invitation.png "Teams 会議用のカスタマイズ可能な会議の招待状設定のスクリーンショット")

    - [**ロゴ URL**] ロゴの保存場所の URL を入力します。
    - [**法的事項の URL**] 法的な質問があるユーザーを誘導することができる、法的事項が記載されている Web サイトが組織にある場合は、こちらに URL を入力します。
    - [**ヘルプの URL**] ユーザーに問題が発生した場合にユーザーを誘導することができる、サポート Web サイトが組織にある場合は、こちらに URL を入力します。
    - [**フッター**] フッターとして含めるテキストを入力します。
4. **[Preview invite]**(出席依頼のプレビュー) をクリックして、会議出席依頼のプレビューを表示します。
5. 作業を終えたら、**[保存]** をクリックします。
6. 変更が反映されるまで、約 1 時間待ちます。 その後、Team 会議をスケジュールし、会議の招待状の表示のされ方を確認します。  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Teams 会議でのリアルタイム メディア トラフィックの処理方法を設定する

<a name="bknetwork"> </a>

ネットワーク トラフィックの優先順位を付けるためにサービスの品質 (QoS) を使用している場合は、QoS マーカーを有効にしたり、メディア トラフィックの種類ごとにポート範囲を設定したりできます。 トラフィックの種類ごとのポート範囲の設定は、リアルタイム メディアの処理に関する手順のうちの 1 つに過ぎません。詳細については、「[Teams でのサービスの品質 (QoS)](qos-in-teams.md)」を参照してください。

> [!IMPORTANT]
> QoS を有効にするか Microsoft Teams サービスに関する設定を Microsoft Teams 管理センターで変更するには、[すべてのユーザー デバイスおよびすべての内部ネットワーク デバイスに対して対応する設定を適用](QoS-in-Teams-clients.md)して、Teams で QoS への変更を完全に実装する必要があります。

 ![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**
1. 管理センターにアクセスします。
2. 左側のナビゲーションで、[**会議**] > [**会議設定**] に移動します。
3. [**ネットワーク**] で、以下の手順を実行します。

    ![管理センターでの会議のネットワーク設定のスクリーンショット](media/meeting-settings-network.png "Microsoft Teams 管理センターでの Teams 会議のネットワーク設定のスクリーンショット")

    - DSCP マーキングを QoS で使用できるようにするには、[**リアルタイム メディア トラフィックのサービスの品質 (QoS) マーカーを挿入する**] をオンにします。 選択できるのは、マーカーを使用するか使用しないかのどちらかです。トラフィックの種類ごとにカスタム マーカーを設定することはできません。 DSCP マーカーの詳細については、「[QoS の実装方法を選択する](QoS-in-Teams.md#select-a-qos-implementation-method)」を参照してください。
        > [!NOTE]
        > 通常、DSCP タグはソースポート経由で実行されます。 UDP トラフィックは、既定では 3478 の送信先ポートを使用してトランスポート リレーにルーティングされます。 会社が送信先ポートでのタグ付けを必要とする場合は、サポートに連絡して、UDP ポート 3479 (Audio)、3480 (ビデオ)、3481 (共有) を使用したトランスポート リレーへの通信を有効にしてください。
    - ポート範囲を指定するには、[**リアルタイム メディア トラフィックの種類ごとのポート範囲を選択する**] の横にある [**ポート範囲を指定**] を選択し、オーディオ、ビデオ、画面共有用の開始および終了ポートを入力します。 QoS を実装するには、このオプションを選択する必要があります。 
        > [!Note]
        > **リアルタイムのメディア トラフィックのサービス品質 (QoS) マーカー** がオンになっている場合は、ポート設定を管理する必要があります。 これらは、自動的に管理されません。
        
        > [!IMPORTANT]
        > [**任意の利用可能なポートを自動的に使用する**] を選択すると、1024 と 65535 の間の利用可能なポートが使用されます。 このオプションは、QoS を実装しない場合にのみ使用します。
        >
        > 範囲が狭すぎるポート範囲を選択すると、通話の中断や通話の品質低下が発生します。 以下の推奨事項は、最低限のものです。

お客様の環境で使用すべきポート範囲がわからない場合は、以下の設定から始めることをお勧めします。 詳細については、「[Microsoft Teams でサービスの品質 (QoS) を実装する](QoS-in-Teams.md)」を参照してください。 必要な DSCP マーキングと、Teams と ExpressRoute の両方で使用される、対応する推奨メディア ポートの範囲を以下に示します。

### <a name="port-ranges-and-dscp-markings"></a>ポート範囲と DSCP マーカー

メディア トラフィックの種類| クライアントのソース ポートの範囲\* |プロトコル|DSCP 値|DSCP クラス|
|:---             |:---                         |:---    |:---      |:---      |
|オーディオ            | 50,000–50,019               |TCP/UDP |46        |完全優先転送 (EF)|
|ビデオ            | 50,020–50,039               |TCP/UDP |34        |相対的優先転送 (AF41)|
|アプリケーション/画面共有| 50,040–50,059      |TCP/UDP |18        |相対的優先転送 (AF21)|
| | | | |

\* 割り当てたポート範囲は重なり合うことができず、相互に隣接することになります。

QoS をしばらくの期間使用すると、これらの 3 つのワークロードのそれぞれの需要に関する使用状況情報を入手できます。具体的なニーズに応じて、変更が必要な点を決められます。 この作業を行う上で、[通話品質ダッシュボード](turning-on-and-using-call-quality-dashboard.md)が役に立ちます。