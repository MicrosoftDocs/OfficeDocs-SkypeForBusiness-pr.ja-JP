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
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: ユーザーは、他のユーザーの状態メッセージの代理人として明示的に設定することができます。
ms.openlocfilehash: be7092d2a68010d00a2d214f12bfe9011d44bbc5
ms.sourcegitcommit: 1786d4beccc8749e20709d2360d90e2bf7634925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2019
ms.locfileid: "35119485"
---
# <a name="set-a-delegate-in-a-status-message"></a>状態メッセージで代理人を設定する

ユーザーは、状態を既に [退席中] または [応答不可] に設定して、カスタムテキストを指定できます。 委任機能を使用すると、別のユーザーにテキスト状態メッセージの一部としてメンションを @username ことができます。また、それらのユーザーが連絡できるようにする場合は、代わりに、@username メンションされたユーザーに連絡することをお勧めします。 他のユーザーに連絡してもらい、指定された代理人の上にカーソルを置いて、代わりに簡単にメッセージを送信できます。  代理人として割り当てられたユーザーには、代理人として任命されたことが通知されます。

これは、クライアントでのユーザーによって開始されるプロセスであり、管理者の関与は必要ありません。

## <a name="delegation-use-scenario-in-healthcare"></a>医療機関の委任使用シナリオ

*代理人を設定しない場合の使用例:* Franco のお店では、radiology 部門で通話を発信できます。 緊急の個人的な通話を受信していて、次の数時間の間に一歩離してください。 彼は、radiology department、Lena Ehrle の相手のうちの1人に、彼が休暇中に自分のことを説明するように求めています。 彼は、ポケットベルを使って、緊急のメッセージやポケットベルをリッスンしていて、現在の責任に加えて、ワトソン博士の代理として応答します。 チームの他のユーザーは、非公式の委任が行われていない可能性があり、患者の ensues に混乱を招く可能性があります。

*代理人を設定する使用例:* Franco のお店では、radiology 部門で通話を発信できます。 緊急の個人的な通話を受信していて、次の数時間の間に一歩離してください。 彼は、radiology department、Lena Ehrle のいずれかのピアに連絡して、彼が休暇中の相手に向けて説明します。 自分のユーザー設定の状態メッセージを変更して、"今後数時間は利用できません" というメッセージが表示されるようにしました。 緊急対応の @DrEhrle に連絡してください。」  チームの他のユーザーは、あなたが Dr. it Cio に連絡しようとしているため、この委任が行われていることを認識しているため、現在はワトソン博士に連絡してください。 患者の注意を ensues ことができます。

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Teams クライアントでのユーザーの状態への共存モードの影響

管理者は、状態メモと委任メンションが一部のユーザーの共同のモードに依存することに注意する必要があります。 このマトリックスは、次の可能性を示します。

|共存モード | 予期される動作|
|---|---|
|TeamsOnly |ユーザーは、Teams からのみメモを設定することができます。 <br> ユーザーの Teams のメモは Teams & SfB に表示されます。 |
|アイランド | Teams でのユーザーのメモセットは、Teams でのみ表示されます。 <br> Sfb でのみ表示される sfb でのユーザのメモセット |
|SfB * モード | ユーザーは、SfB からのみメモを設定することができます。 <br> ユーザーの SfB メモは、SfB & Teams で表示されます。  |
|||

ユーザーは、チーム内のメモを設定できるのは、チームのモードが Teams s のみか、または諸島の場合のみです。  

### <a name="displaying-notes-set-in-skype-for-business"></a>Skype for Business でのノートセットの表示
  
ノートが Skype for Business から設定されたことを示す視覚的な通知はありません。

Skype for Business では、状態メモに文字数の制限は適用されません。 Microsoft Teams では、Skype for Business からのメモセットの最初の280文字のみが表示されます。 終端の省略記号 (...) は、切り捨てを示します。
  
Skype for Business では、ノートの有効期間をサポートしていません。

ユーザーが TeamsOnly モードにアップグレードされている場合、Skype for Business から Teams へのメモの移行はサポートされません。

## <a name="configure-allowing-clients-to-use-delegates"></a>クライアントに代理人の使用を許可するように構成する

この機能には、Microsoft Teams 管理センターでの構成または PowerShell の使用は必要ありません。 サポートされているテナントでは、チームクライアントで既定で利用できます。

## <a name="related-topics"></a>関連項目

[Skype for Business と共存する](../../coexistence-chat-calls-presence.md)
