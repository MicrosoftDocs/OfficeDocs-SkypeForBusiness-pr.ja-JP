---
title: コンテンツ共有の会議ポリシーを管理する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: コンテンツ共有用の会議ポリシー設定をTeamsする方法について学習します。
ms.openlocfilehash: 7b318ad0025d6c68b041c65d8fbb78cbfbc87723
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598774"
---
# <a name="meeting-policy-settings---content-sharing"></a>会議ポリシーの設定 - コンテンツの共有

<a name="bkcontentsharing"> </a>

この記事では、コンテンツ共有に関連する次の会議ポリシー設定について説明します。

- [画面共有モード](#screen-sharing-mode)
- [参加者に制御を渡す、または制御を要求する](#allow-a-participant-to-give-or-request-control)
- [外部の参加者に制御を渡す、または制御を要求する](#allow-an-external-participant-to-give-or-request-control)
- [PowerPoint の共有を許可する](#allow-powerpoint-sharing)
- [ホワイトボードを許可する](#allow-whiteboard)
- [メモの共有を許可する](#allow-shared-notes)

## <a name="screen-sharing-mode"></a>画面共有モード

この設定は、開催者ごとのポリシーとユーザーごとのポリシーの組み合わせです。 この設定は、ユーザーの会議でデスクトップとウィンドウの共有を許可するかどうかを制御します。 ポリシーが割り当てられていない会議参加者 (匿名参加者、ゲスト参加者、B2B 参加者、フェデレーション参加者など) は、会議開催者のポリシーを継承します。

|値を設定する |動作  |
|---------|---------|
|**画面全体**    | 会議では完全なデスクトップ共有とアプリケーション共有が許可されます |
|**単一アプリケーション**   | 会議ではアプリケーションの共有が許可されます        |
|**無効**     |会議では画面共有とアプリケーション共有が無効になります。       |

次の例を見てみましょう。

|ユーザー |会議ポリシー |画面共有モード |
|---------|---------|---------|
|Daniela  | グローバル   | 画面全体 |
|Amanda   | Location1MeetingPolicy  | 無効 |

Daniela が開催する会議では、会議の参加者が画面全体または特定のアプリケーションを共有できます。 Amanda が Daniela の会議に参加すると、ポリシー設定が無効になっているため、Amanda は自分の画面または特定のアプリケーションを共有できません。 Amanda がホストする会議では、割り当てられた画面共有モード ポリシーに関係なく、誰も画面または単一のアプリケーションを共有できません。  その結果、Daniela は Amanda の会議で画面または 1 つのアプリケーションを共有できない。  

現在、ユーザーは Google Chrome を使用している場合、Teams 会議でビデオを再生したり画面を共有したりすることはできません。

## <a name="allow-a-participant-to-give-or-request-control"></a>参加者に制御を渡す、または制御を要求する

この設定は、ユーザーごとのポリシーです。 この設定は、ユーザーが他の会議参加者に共有デスクトップまたはウィンドウの制御を渡すことができるかどうかを制御します。 制御を渡すには、画面の上部にカーソルを合わせます。

ユーザーに対してこの設定が有効になっている場合、共有セッションの上部のバーに [**制御を渡す**] オプションが表示されます。

![[制御を渡す] オプションが表示されたスクリーンショット](media/meeting-policies-give-control.png)

設定がユーザーに対して無効になっている場合、[**制御を渡す**] オプションは使用できません。

![[制御を渡す] オプションが利用できないことを示すスクリーンショット](media/meeting-policies-give-control-not-available.png)

次の例を見てみましょう。

|ユーザー |会議ポリシー  |参加者に制御を渡す、または制御を要求する |
|---------|---------|---------|
|Daniela   | グローバル   | オン       |
|Babek    | Location1MeetingPolicy        | オフ   |

Daniela は、共有デスクトップまたはウィンドウを、赤んじりで開催された会議の他の参加者に制御できます。 ただし、他の参加者に対して制御を与え得ない。

制御を渡したり、制御要求を受け入れたりすることができるユーザーを PowerShell を使用して制御するには、AllowParticipantGiveRequestControl コマンドレットを使用します。

> [!NOTE]
> 共有中に共有コンテンツの制御を渡したり受け取ったりするには、両者が Teams デスクトップ クライアントを使用している必要があります。 いずれかの当事者がブラウザーで Teams を実行している場合、制御はサポートされません。 これは、修正する予定の技術的制限によるものです。

## <a name="allow-an-external-participant-to-give-or-request-control"></a>外部の参加者に制御を渡す、または制御を要求する

この設定は、ユーザーごとのポリシーです。 組織がユーザーに対してこのポリシーを設定したかどうかは、会議開催者が設定した設定に関係なく、外部参加者が実行できる操作を制御しない。 このパラメーターは、組織の会議ポリシー内において、共有先が設定した内容に応じて、外部の参加者に共有スクリーンの制御または制御の依頼を許可するかどうかを制御します。 Teams 会議の外部参加者は、次のように分類できます。  

- 匿名ユーザー
- ゲスト ユーザー  
- B2B ユーザー
- フェデレーション ユーザー  

フェデレーション ユーザーが共有中に外部ユーザーに制御を渡すことができるかどうかは、組織の「**外部の参加者に制御を渡す、または制御を要求する**」設定によって制御されます。

PowerShell を使用して、外部の参加者が制御を渡すことができるか、または制御要求を受け入れることができるかを制御するには、AllowExternalParticipantGiveRequestControl コマンドレットを使用します。

### <a name="allow-powerpoint-sharing"></a>PowerPoint の共有を許可する

これは、ユーザーごとのポリシーです。 この設定は、ユーザーが会議で PowerPoint スライド セットを共有できるかどうかを制御します。 匿名ユーザー、ゲスト ユーザー、フェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。

次の例を見てみましょう。

|ユーザー |会議ポリシー  |PowerPoint の共有を許可する |
|---------|---------|---------|
|Daniela   | グローバル   | オン       |
|Amanda   | Location1MeetingPolicy        | オフ   |

Amanda は、会議の開催者であっても、PowerPoint スライド セットを会議で共有することはできません。 Daniela は、会議が Amanda によって開催されている場合でも、PowerPoint スライド セットを共有することができます。 Amanda は、PowerPoint スライド セットを共有できない場合でも、会議の他のユーザーによって共有されている PowerPoint スライド セットを表示することができます。

## <a name="allow-whiteboard"></a>ホワイトボードを許可する

この設定は、ユーザーごとのポリシーです。 この設定は、ユーザーが会議でホワイトボードを共有できるかどうかを制御します。 匿名ユーザー、B2B ユーザー、およびフェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。

次の例を見てみましょう。

|ユーザー |会議ポリシー  |ホワイトボードを許可する|
|---------|---------|---------|
|Daniela   | グローバル   | オン       |
|Amanda   | Location1MeetingPolicy        | オフ   |

Amanda は、会議の開催者であっても、会議でホワイトボードを共有することはできません。 Daniela は、Amanda が会議を開催する場合でも、ホワイトボードを共有することができます。  

## <a name="allow-shared-notes"></a>メモの共有を許可する

この設定は、ユーザーごとのポリシーです。 この設定は、ユーザーが会議でメモを作成および共有できるかどうかを制御します。 匿名ユーザー、B2B ユーザー、およびフェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。 現在、[**会議メモ**] タブは、参加者が 20 人未満の会議でのみサポートされています。

次の例を見てみましょう。

|ユーザー |会議ポリシー  |メモの共有を許可する |
|---------|---------|---------|
|Daniela   | グローバル   | オン       |
|Amanda   | Location1MeetingPolicy | オフ |

Daniela は Amanda の会議でメモを取ることができ、Amanda はすべての会議でメモを取ることができません。




## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)
- [ Teams でユーザーにポリシーを割り当てる](assign-policies.md)
- [ユーザーから RestrictedAnonymousAccess Teams 会議ポリシーを削除する](meeting-policies-restricted-anonymous-access.md)
