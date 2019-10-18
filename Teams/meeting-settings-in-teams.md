---
title: 会議の設定を管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
description: 組織でスケジュールされているユーザーのチーム会議の設定を管理する方法について説明します。
ms.openlocfilehash: 36325fe82c8864850da8e92de385752422e02f72
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37564935"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Microsoft Teams で会議の設定を管理する

管理者として、Teams 会議の設定を使用して、匿名ユーザーが Teams 会議に参加できるかどうかを制御したり、会議出席依頼をカスタマイズしたり、サービスの品質 (QoS) を有効にしたりする場合は、リアルタイムトラフィック用のポート範囲を設定する必要があります。 これらの設定は、ユーザーが組織でスケジュールしたすべてのチーム会議に適用されます。 これらの設定は、Microsoft Teams 管理センターの**会議** > の**設定**から管理します。

## <a name="allow-anonymous-users-to-join-meetings"></a>匿名ユーザーによる会議への参加を許可する

匿名の参加では、会議出席依頼のリンクをクリックすると、誰でも匿名ユーザーとして会議に参加できます。

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**会議** > の**会議の設定**] に移動します。
2. [**参加者**] の下で、[**匿名ユーザーが会議に参加できるよう**にする] をオンにします。

    ![管理センターでの会議の参加者設定のスクリーンショット](media/meeting-settings-participants.png "Microsoft Teams 管理センターでの Teams 会議の参加者設定のスクリーンショット")

組織内のユーザーによってスケジュールされている会議に匿名ユーザーが会議に参加しないようにするには、この設定をオフにします。

## <a name="customize-meeting-invitations"></a>会議出席依頼をカスタマイズする

組織のニーズに合わせて、Teams の会議出席依頼をカスタマイズすることができます。 組織のロゴを追加したり、サポート web サイトや法的免責事項へのリンクやテキストのみのフッターなど、有用な情報を含めることができます。

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>会議出席依頼のロゴを作成するためのヒント  

1. 高さが188ピクセル未満で、幅が30ピクセル以下の画像を作成します (非常に小さい)。
2. 画像を JPG または PNG 形式で保存します。
3. ネットワーク共有など、組織内のすべてのユーザーがアクセスできる一元的な場所に画像を保存します。

    会議出席依頼に追加できるようになります。 次の手順を参照してください。

### <a name="customize-your-meeting-invitations"></a>会議出席依頼をカスタマイズする

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**会議** > の**会議の設定**] に移動します。
2. [**電子メールの招待状**] で、次の操作を行います。

    ![カスタマイズできる会議出席依頼の設定のスクリーンショット](media/meeting-settings-invitation.png "チーム会議用にカスタマイズできる会議出席依頼の設定のスクリーンショット")

    - **ロゴ URL**ロゴが保存されている URL を入力します。
    - **法的**情報の URL法的な懸念事項についてユーザーに連絡する法的 web サイトが組織にある場合は、URL をここに入力します。
    - **ヘルプ URL**問題が発生した場合にユーザーが移動できるサポート web サイトが組織にある場合は、URL をここに入力します。
    - **フッター**フッターとして追加するテキストを入力します。
3. 変更を反映させるには1時間ほど待ちます。 次に、Teams 会議をスケジュールして、会議の出席依頼がどのように表示されるかを確認します。  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Teams 会議でのリアルタイムのメディアトラフィックの処理方法を設定する

<a name="bknetwork"> </a>

Qos (Quality of Service [)](qos-in-teams.md)を使ってネットワークトラフィックの優先順位を設定している場合は、qos マーカーを有効にして、メディアトラフィックごとにポート範囲を設定することができます。 トラフィックの種類ごとにポート範囲を設定することは、リアルタイムメディアを処理する手順の1つにすぎません。詳細については、「 [Teams のサービスの品質 (QoS)](qos-in-teams.md) 」を参照してください。

> [!IMPORTANT]
> Microsoft Teams サービスの Microsoft Teams 管理センターで QoS を有効にしたり設定を変更したりする場合は、[すべてのユーザーデバイス](QoS-in-Teams-clients.md)とすべての内部ネットワークデバイスに一致する設定を適用して、Teams の QoS への変更を完全に実装する必要もあります。

 ![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**会議** > の**会議の設定**] に移動します。
2. [**ネットワーク**] で、次の操作を行います。

    ![管理センターでの会議のネットワーク設定のスクリーンショット](media/meeting-settings-network.png "Microsoft Teams 管理センターの Teams 会議のネットワーク設定のスクリーンショット")

    - QoS に DSCP マーキングを使用できるようにするには、**リアルタイムメディアトラフィックの [サービス品質 (QoS) マーカーの挿入**] を有効にします。 マーカーを使用するかどうかは選択できません。トラフィックの種類ごとにカスタムマーカーを設定することはできません。 詳細については[、「QoS の実装方法を選択する](QoS-in-Teams.md#select-a-qos-implementation-method)」を参照してください。
    > [!NOTE] 
    > **リアルタイムメディアトラフィックの [サービス品質の挿入 (QoS)] マーカー**を有効にすると、UDP ポート 3479 (オーディオ)、3480 (ビデオ)、3481 (共有) を使用したトランスポートリレーとの通信が可能になります。
    - ポート範囲を指定するには、[ポート範囲の指定] の横にある [ポート範囲の**指定** **] を選択**し、オーディオ、ビデオ、画面共有の開始ポートと終了ポートを入力します。 QoS を実装するには、このオプションを選択する必要があります。
    > [!IMPORTANT]
    > [**利用可能なポートを自動的に使用**する] を選択すると、1024と65535の間で利用可能なポートが使用されます。 このオプションは、QoS を実装していない場合にのみ使用します。
    >
    > 狭い範囲のポート範囲を選択すると、通話の中断や音質の低下が発生する可能性があります。 以下の推奨事項は最小限にする必要があります。

環境で使用するポートの範囲がわからない場合は、次の設定を開始することをお勧めします。 詳細については、「 [Microsoft Teams でサービスの品質 (QoS) を実装する」](QoS-in-Teams.md)を参照してください。 必要な DSCP マーキングと、両方の Teams と ExpressRoute で使用される、対応するメディアポート範囲を示します。

_ポート範囲と DSCP マーキング_

メディアトラフィックの種類| クライアントのソースポートの範囲\* |プロトコル|DSCP 値|DSCP クラス|
|:---             |:---                         |:---    |:---      |:---      |
|オーディオ            | 50000–50019               |TCP/UDP |46        |完全優先転送 (EF)|
|ビデオ            | 50020–50039               |TCP/UDP |34        |相対的優先転送 (AF41)|
|アプリケーション/画面共有| 50040–50059      |TCP/UDP |才        |確実に転送 (AF21)|
| | | | |

\*割り当てるポートの範囲は重なり合って、互いに隣り合っている必要があります。

しばらくの間 QoS が使用された後は、これら3つのワークロードのそれぞれについて、必要に応じて使用に関する情報を入手できます。また、特定のニーズに応じてどのような変更を行うかを選ぶこともできます。 [通話品質ダッシュボード](turning-on-and-using-call-quality-dashboard.md)は、そのために役立ちます。
