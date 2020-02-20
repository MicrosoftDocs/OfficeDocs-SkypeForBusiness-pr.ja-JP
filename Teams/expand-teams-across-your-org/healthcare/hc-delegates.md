---
title: メッセージの委任
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: ユーザーは、ステータス メッセージの代理人として別のユーザーを明示的に設定できます。
ms.openlocfilehash: e76181ff69f2d4e6ed75183bdb5fbdda695d05e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153809"
---
# <a name="message-delegation"></a>メッセージの委任

ユーザーは、明示的にステータスを [退席中] または [応答不可] に設定し、カスタム テキストを提供できます。 メッセージの委任機能は次のように動作します。

1. ユーザーは、テキストのステータス メッセージの一部で @username に別のユーザーの名前をあげます。これは、連絡できない場合は、@username に名前をあげたユーザーに連絡することを示します。
2. 代理人として指名されたユーザーには、指名されたことが通知されます。
3. 最初のユーザーに連絡しようとしている人は、指名された代理人にカーソルを合わせると、代理人に簡単にメッセージを送ることができます。  

これは、ユーザーによって開始されるクライアントのプロセスであり、この機能を有効にするために管理者に連絡する必要はありません。 

## <a name="delegation-use-scenario-in-healthcare"></a>医療機関における代理人の使用シナリオ

*代理人の設定を使用しない例:* Franco Piccio 先生は放射線科に電話をかけています。 彼は緊急の個人的な電話を受け、数時間現場から離れなければなりません。 彼は、放射線科の同僚である Lena Ehrle 先生に、自分がいない間、代わりに患者さんを診てほしいと依頼します。 彼は非公式にポケットベルを Ehrle 先生に渡します。Ehrle 先生は、自分の仕事をこなしながら、Piccio 先生の代わりにポケットベルの緊急メッセージと通知音を聞いて応答します。 チームの他のメンバーは、非公式の委任に気が付かず、患者さんの治療に混乱が生じるかもしれません。

*代理人の設定を使用する例:* Franco Piccio 先生は放射線科に電話をかけています。 彼は緊急の個人的な電話を受け、数時間現場から離れなければなりません。 彼は、放射線科の同僚である Lena Ehrle 先生に、自分がいない間、代わりに患者さんを診てほしいと依頼します。 彼は自分のカスタム ステータス メッセージを変更して、「数時間現場から離れなければなりません。 緊急の場合は @DrEhrle に連絡してください。」のような内容を残します。  チームの他のメンバーは、Piccio 先生と連絡を取ろうとしたときに、委任があったことに気づきます。そのため、Ehrle 先生と連絡を取ることができます。 患者の治療に混乱がほとんど生じません。

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Teams クライアントのユーザー ステータスに対する共存モードの影響

管理者は、ステータスのメモと委任言及の動作がユーザーの共存モードに一部依存することに注意する必要があります。 このマトリックスは可能性を示します。

|共存モード | 正常な動作|
|---|---|
|TeamsOnly |ユーザーは、Teams からのみメモを設定できます。 <br> ユーザーの Teams メモは、Teams と SfB に表示されます。 |
|アイランド | Teams で設定されたユーザーのメモは、Teams でのみ表示されます。 <br> SfB で設定されたユーザーのメモは、SfB でのみ表示されます。 |
|SfB* モード | ユーザーは、SfB からのみメモを設定できます。 <br> ユーザーの SfB メモは、SfB と Teams に表示されます。  |
|||

モードが TeamsOnly または アイランドの場合、ユーザーはメモを設定できます。  

### <a name="displaying-notes-set-in-skype-for-business"></a>メモの Skype for Business での表示
  
メモが Skype for Business から設定されていることを視覚的に示すものはありません。

Skype for Business のステータス メモに文字数の制限は適用されていません。 Microsoft Teams は、Skype for Business からのメモ セットのうち最初の 280 文字のみを表示します。 メモの最後にある省略記号 (…) は省略されたことを示します。
  
Skype for Business は、メモの有効期限をサポートしていません。

ユーザーが TeamsOnly モードにアップグレードされている場合は、Skype for Business から Teams にメモを移行することはできません。

## <a name="related-topics"></a>関連項目

[Skype for Business と共存する](../../coexistence-chat-calls-presence.md)
