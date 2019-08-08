---
title: メッセージの委任
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: ユーザーは、他のユーザーの状態メッセージの代理人として明示的に設定することができます。
ms.openlocfilehash: cc9895ec639589ec260a03b0a1828ccf2a4eb9b1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232349"
---
# <a name="message-delegation"></a>メッセージの委任

ユーザーは、状態を既に [退席中] または [応答不可] に設定して、カスタムテキストを指定できます。 メッセージの委任機能は、次のように動作します。

1. ユーザーは、別のユーザーをテキスト状態メッセージの一部としてメンションして、相手に連絡したいユーザーがいないときに、@username メンションされたユーザーに連絡することを提案 @username ます。
2. 代理人として割り当てられたユーザーには、代理人として任命されたことが通知されます。
3. 最初のユーザーに連絡しようとしているユーザーは、指定されたデリゲートの上にマウスポインターを置くと、代わりに代理人に簡単にメッセージを送信できます。  

これはクライアントでのユーザーによって開始されるプロセスであり、この機能を有効にするために管理者の関与は必要ありません。 

## <a name="delegation-use-scenario-in-healthcare"></a>医療機関の委任使用シナリオ

*代理人を設定しない場合の使用例:* Franco のお店では、radiology 部門で通話を発信できます。 緊急の個人的な通話を受信していて、次の数時間の間に一歩離してください。 彼は、radiology department、Lena Ehrle の相手のうちの1人に、彼が休暇中に自分のことを説明するように求めています。 彼は、ポケットベルを使って、緊急のメッセージやポケットベルをリッスンしていて、現在の責任に加えて、ワトソン博士の代理として応答します。 チームの他のユーザーは、非公式の委任が行われていない可能性があり、患者の ensues に混乱を招く可能性があります。

*代理人を設定する使用例:* Franco のお店では、radiology 部門で通話を発信できます。 緊急の個人的な通話を受信していて、次の数時間の間に一歩離してください。 彼は、radiology department、Lena Ehrle のいずれかのピアに連絡して、彼が休暇中の相手に向けて説明します。 自分のユーザー設定の状態メッセージを変更して、"今後数時間は利用できません" というメッセージが表示されるようにしました。 緊急対応の @DrEhrle に連絡してください。」  チームの他のユーザーは、あなたが Dr. it Cio に連絡しようとしているため、この委任が行われていることを認識しているため、現在はワトソン博士に連絡してください。 患者の注意を ensues ことができます。

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Teams クライアントでのユーザーの状態への共存モードの影響

管理者は、[状態メモ] と [委任によるメンション] の動作が、ユーザーの共存モードに依存することに注意する必要があります。 このマトリックスは、次の可能性を示します。

|共存モード | 予期される動作|
|---|---|
|TeamsOnly |ユーザーは、Teams からのみメモを設定することができます。 <br> ユーザーの Teams のメモは Teams & SfB に表示されます。 |
|アイランド | Teams でのユーザーのメモセットは、Teams でのみ表示されます。 <br> Sfb でのみ表示される sfb でのユーザのメモセット |
|SfB * モード | ユーザーは、SfB からのみメモを設定することができます。 <br> ユーザーの SfB メモは、SfB & Teams で表示されます。  |
|||

ユーザーは、チーム内のメモを設定できるのは、チームのモードが Teams s のみか、または諸島の場合のみです。  

### <a name="displaying-notes-set-in-skype-for-business"></a>Skype for Business でのノートセットの表示
  
ノートが Skype for Business から設定されたことを示す視覚的な通知はありません。

Skype for Business では、状態メモに文字数の制限は適用されません。 Microsoft Teams では、Skype for Business からのメモセットの最初の280文字のみが表示されます。 メモの末尾にある省略記号 (...) は、切り捨てを示します。
  
Skype for Business では、ノートの有効期間をサポートしていません。

ユーザーが TeamsOnly モードにアップグレードされている場合、Skype for Business から Teams へのメモの移行はサポートされません。

## <a name="related-topics"></a>関連項目

[Skype for Business と共存する](../../coexistence-chat-calls-presence.md)
