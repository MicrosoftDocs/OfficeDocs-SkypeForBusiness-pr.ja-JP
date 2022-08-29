---
title: コンテンツ共有の会議ポリシーを管理する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
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
description: Teams でコンテンツ共有の会議ポリシー設定を管理する方法について説明します。
ms.openlocfilehash: c2baa0328cd1ff0271d2b1ecbf8e1fab76f24846
ms.sourcegitcommit: 0592f9d2696fe8c840a4ed3e7f99e55ca0c9c3e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2022
ms.locfileid: "67418616"
---
# <a name="meeting-policy-settings---content-sharing"></a>会議ポリシーの設定 - コンテンツの共有

<a name="bkcontentsharing"> </a>

この記事では、コンテンツ共有に関連する次の会議ポリシー設定について説明します。

- [画面共有モード](#screen-sharing-mode)
- [参加者に制御を渡す、または制御を要求する](#allow-a-participant-to-give-or-request-control)
- [外部参加者は、制御を与えたり要求したりできます](#external-participants-can-give-or-request-control)
- [PowerPoint Live](#powerpoint-live)
- [ホワイトボード](#whiteboard)
- [共有ノート](#shared-notes)

## <a name="screen-sharing-mode"></a>画面共有モード

この設定は、開催者ごとのポリシーとユーザーごとのポリシーの組み合わせです。 この設定は、ユーザーの会議でデスクトップとウィンドウの共有を許可するかどうかを制御します。 ポリシーが割り当てられていない会議参加者 (外部参加者など) は、会議の開催者のポリシーを継承します。

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

Daniela が開催する会議では、会議の参加者が画面全体または特定のアプリケーションを共有できます。 Amanda が Daniela の会議に参加すると、ポリシー設定が無効になっているため、Amanda は自分の画面または特定のアプリケーションを共有できません。 Amanda がホストする会議では、割り当てられた画面共有モード ポリシーに関係なく、誰も画面または単一のアプリケーションを共有できません。  その結果、Daniela は Amanda の会議で画面または 1 つのアプリケーションを共有できません。  

現在、ユーザーは Google Chrome を使用している場合、Teams 会議でビデオを再生したり画面を共有したりすることはできません。

## <a name="allow-a-participant-to-give-or-request-control"></a>参加者に制御を渡す、または制御を要求する

この設定はユーザーごとのポリシーです。 この設定は、ユーザーが他の会議参加者に共有デスクトップまたはウィンドウの制御を渡すことができるかどうかを制御します。 制御を渡すには、画面の上部にカーソルを合わせます。

ユーザーに対してこの設定が有効になっている場合、共有セッションの上部のバーに [**制御を渡す**] オプションが表示されます。

![[制御を渡す] オプションが表示されたスクリーンショット。](media/meeting-policies-give-control.png)

設定がユーザーに対して無効になっている場合、[**制御を渡す**] オプションは使用できません。

![[制御を渡す] オプションが利用できないことを示すスクリーンショット。](media/meeting-policies-give-control-not-available.png)

次の例を見てみましょう。

|ユーザー |会議ポリシー  |参加者に制御を渡す、または制御を要求する |
|---------|---------|---------|
|Daniela   | グローバル   | オン       |
|Babek    | Location1MeetingPolicy        | オフ   |

Daniela は、共有デスクトップまたはウィンドウの制御を、Bashk が開催した会議の他の参加者に与えることができます。 ただし、他の参加者に制御を与えることはできません。

制御を渡したり、制御要求を受け入れたりすることができるユーザーを PowerShell を使用して制御するには、AllowParticipantGiveRequestControl コマンドレットを使用します。

> [!NOTE]
> 共有中に共有コンテンツの制御を渡したり受け取ったりするには、両者が Teams デスクトップ クライアントを使用している必要があります。 いずれかの当事者がブラウザーで Teams を実行している場合、制御はサポートされません。 これは、修正する予定の技術的制限によるものです。

## <a name="external-participants-can-give-or-request-control"></a>外部参加者は、制御を与えたり要求したりできます

この設定はユーザーごとのポリシーです。 組織がユーザーに対してこのポリシーを設定したかどうかは、会議の開催者が設定した内容に関係なく、外部参加者が実行できる操作を制御しません。 このパラメーターは、組織の会議ポリシー内において、共有先が設定した内容に応じて、外部の参加者に共有スクリーンの制御または制御の依頼を許可するかどうかを制御します。 Teams 会議の外部参加者は、次のように分類できます。  

- 匿名参加者
- ゲスト
- 外部アクセス ユーザー

外部アクセス ユーザーが他の外部参加者に制御を与える一方で、共有が外部参加者によって制御されるかどうかは、組織内で制御設定を **付与または要求できます** 。

PowerShell を使用して、外部の参加者が制御を渡すことができるか、または制御要求を受け入れることができるかを制御するには、AllowExternalParticipantGiveRequestControl コマンドレットを使用します。

### <a name="powerpoint-live"></a>PowerPoint Live

これは、ユーザーごとのポリシーです。 この設定は、ユーザーが会議で PowerPoint スライド セットを共有できるかどうかを制御します。 匿名ユーザー、ゲスト ユーザー、外部アクセス ユーザーを含む外部参加者は、会議開催者のポリシーを継承します。

次の例を見てみましょう。

|ユーザー |会議ポリシー  |PowerPoint Live |
|---------|---------|---------|
|Daniela   | グローバル   | オン       |
|Amanda   | Location1MeetingPolicy        | オフ   |

Amanda は、会議の開催者であっても、PowerPoint スライド セットを会議で共有することはできません。 Daniela は、会議が Amanda によって開催されている場合でも、PowerPoint スライド セットを共有することができます。 Amanda は、PowerPoint スライド セットを共有できない場合でも、会議の他のユーザーによって共有されている PowerPoint スライド セットを表示することができます。

## <a name="whiteboard"></a>ホワイトボード

この設定はユーザーごとのポリシーです。 この設定は、ユーザーが会議でホワイトボードを共有できるかどうかを制御します。 匿名ユーザー、ゲスト ユーザー、外部アクセス ユーザーを含む外部参加者は、会議開催者のポリシーを継承します。

次の例を見てみましょう。

|ユーザー |会議ポリシー  |ホワイトボード|
|---------|---------|---------|
|Daniela   | グローバル   | オン       |
|Amanda   | Location1MeetingPolicy        | オフ   |

Amanda は、会議の開催者であっても、会議でホワイトボードを共有することはできません。 Daniela は、Amanda が会議を開催する場合でも、ホワイトボードを共有することができます。

PowerShell を使用して Whiteboard を有効にするには、IsWBFluidEnabled コマンドレットを [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) から$trueに設定します。

### <a name="annotation"></a>アノテーション

ホワイトボードが有効になっている場合、ユーザーは [注釈](/office/use-annotation-while-sharing-your-screen-in-teams)を使用するオプションを使用できます。この機能を使用すると、参加者は Teams 会議で画面を共有しながら共同作業できます。 ホワイトボードが無効になっている場合、ユーザーは注釈にアクセスできません。

## <a name="shared-notes"></a>共有ノート

この設定はユーザーごとのポリシーです。 この設定は、ユーザーが会議でメモを作成および共有できるかどうかを制御します。 匿名、ゲスト、外部アクセスを含む外部参加者は、会議開催者のポリシーを継承します。 現在、[**会議メモ**] タブは、参加者が 20 人未満の会議でのみサポートされています。

次の例を見てみましょう。

|ユーザー |会議ポリシー  |共有ノート |
|---------|---------|---------|
|Daniela   | グローバル   | オン       |
|Amanda   | Location1MeetingPolicy | オフ |

Daniela は Amanda の会議でメモを取ることができ、Amanda はすべての会議でメモを取ることができません。




## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)
- [ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)
- [ユーザーから RestrictedAnonymousAccess Teams 会議ポリシーを削除する](meeting-policies-restricted-anonymous-access.md)
