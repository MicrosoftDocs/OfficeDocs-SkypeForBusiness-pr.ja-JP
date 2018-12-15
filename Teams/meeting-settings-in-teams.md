---
title: Microsoft Teams で会議の設定を管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.overview
MS.collection: Teams_ITAdmin_Help
description: 組織内のユーザーのスケジュールを設定するチームの会議の設定を管理する方法について説明します。
ms.openlocfilehash: 1e3415b1fd17a863e14a79fcc66b32e6749b39e7
ms.sourcegitcommit: a51d357069765b7d0956880da2ffd041533cfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2018
ms.locfileid: "27283550"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Microsoft Teams で会議の設定を管理する

管理者と匿名ユーザーは、チームのミーティングに参加、ミーティングの招待状をカスタマイズ、およびサービスの品質 (QoS) を有効にする場合は、リアルタイムのトラフィック用のポートを設定するかどうかのチーム ミーティングを制御する設定を使用します。 これらの設定は、組織内でそのユーザーのスケジュールをチームのすべての会議に適用されます。 **会議**からこれらの設定を管理する > 、マイクロソフトのチームとビジネス管理センターの Skype で**会議を設定**します。 

## <a name="allow-anonymous-users-to-join-meetings"></a>匿名ユーザーが会議に参加できるように

匿名結合は、ミーティング招待状のリンクをクリックすると、匿名ユーザーとして会議に参加誰でもできます。 

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) ビジネス管理センターの Microsoft のチームと Skype を使用します。
1. 左側のナビゲーションでは、**会議**に移動 > **会議を設定**します。 
2. **参加者**の下でオンに**匿名ユーザーが会議に参加できます**。 

    ![会議の設定-participants.png](media/meeting-settings-participants.png "マイクロソフトのチームとビジネス管理センターの Skype でのチーム会議の参加者の設定のスクリーン ショット")

匿名ユーザーは、組織内のユーザーがスケジュールしたミーティングに参加しない場合は、この設定をオフにします。 
## <a name="customize-meeting-invitations"></a>会議出席依頼をカスタマイズする

組織のニーズを満たすためにチームのミーティングの招待状をカスタマイズできます。 組織のロゴを追加したり、サポート用 web サイトと免責事項、およびテキストのみのフッターへのリンクなど、役に立つ情報が含まれます。 

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>会議出席依頼のロゴを作成するためのヒント  

1. 188 ピクセル 30 ピクセルの高さ (非常に小さいです) では、イメージを作成します。 
2. イメージを JPG 形式で保存します。 
3. ネットワーク共有など、組織内のすべてのユーザーがアクセスできる中央の場所にイメージを格納します。 

### <a name="customize-your-meeting-invitations"></a>会議出席依頼をカスタマイズします。

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) ビジネス管理センターの Microsoft のチームと Skype を使用します。

1. 左側のナビゲーションでは、**会議**に移動 > **会議を設定**します。
2. [**電子メール招待状**の場合は、次の操作を行います。 

    ![会議の設定-invitation.png](media/meeting-settings-invitation.png "のスクリーン ショットは、会議のチーム会議用にカスタマイズできる招待状の設定") 

    - **ロゴの URL**ロゴを保存する場所の URL を入力します。 
    - **有効な URL**組織の法的な懸念事項を参照する有効な web サイトの場合は、ここに URL を入力します。 
    - **URL のヘルプ**組織がサポートする web サイトに問題が発生する場合に移動するようにする場合は、ここに URL を入力します。
    - **フッター**フッターとして使用するテキストを入力します。 
3. 1 時間など、変更を伝達するを待ちます。 会議のチームに会議出席依頼は次のように参照してください。  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>チームの会議のためのリアルタイムのメディア トラフィックを処理する方法を設定します。
サービスの品質 (QoS) を使用してネットワーク トラフィックの優先順位を設定する場合、QoS のマーカーを有効にすることができ、メディア トラフィックの種類ごとにポートの範囲を設定することができます。 

 ![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) ビジネス管理センターの Microsoft のチームと Skype を使用します。

1. 左側のナビゲーションでは、**会議**に移動 > **会議を設定**します。 
2. [**ネットワーク**では、次の操作を行います。

    ![会議の設定-network.png](media/meeting-settings-network.png "チーム会議は、マイクロソフトのチームとビジネス管理センターの Skype でのネットワーク設定のスクリーン ショット")

    - QoS のマーカーを有効にするには、**トラフィックのリアルタイム メディアの挿入のサービスの品質 (QoS) のマーカー**を入れます。
    - **リアルタイム メディア トラフィックの種類ごとにポートの範囲を選択**すると、横には、ポート範囲を指定するのには**を指定するポートの範囲**を選択し、オーディオ、ビデオ、および画面共有の開始と終了のポートを入力します。 
    
        **自動的にすべての利用可能なポートを使用して**1024 の間で利用可能なポートを選択すると、65535 が使用されます。 

 ### <a name="related-topics"></a>関連トピック
- [サービスの品質 (QoS のチームで)](qos-in-teams.md)

