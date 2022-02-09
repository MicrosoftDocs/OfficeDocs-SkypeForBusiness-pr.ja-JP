---
title: 表示限定の会議エクスペリエンス
author: SerdarSoysal
ms.author: serdars
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 管理者、発表者、出席者の Teams 表示限定の会議エクスペリエンスについて説明します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 104540c047f499f8b82139e0c76c93e4b4625f62
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401141"
---
# <a name="teams-view-only-meeting-experience"></a>Teams の表示限定の会議エクスペリエンス

> [!Note]
> 表示限定のブロードキャストは、Microsoft 365 E3/E5 および Microsoft 365 A3/A5 で利用できます。 この機能は2021 年 3 月 1 日に有効になりますが、既定でオフになっています。 Microsoft 365 Government Community Cloud (GCC) の機能は、2021 年 3 月末にロールアウトが開始される予定です。 Government Community Cloud High (GCCH) と Department of Defense (DoD) は後日ロールアウトされる予定です。 この機能を既定でオンにしたい場合は、その日付以降に既定のポリシーを変更する必要があります。 PowerShell を使用して、ポリシー`Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`を有効にする。

> [!Note]
> 会議が容量を超えた場合、Teams は 10,000 人に対応できる閲覧限定のブロードキャスト エクスペリエンスにシームレスに拡大縮小されます。 さらに、リモート 作業が増加したこの期間中は、今年の終わりまでさらに大規模な 20,000 人のブロードキャストを利用することができます。 ウェビナーは現在、閲覧限定のブロードキャスト エクスペリエンスをサポートしていません。

Microsoft Teams では、最大 10,000 人の参加者がTeams 会議に参加できます。 メイン会議の容量に達する (1,000 人のユーザーが会議に参加した場合) と、その他の出席者は表示限定のエクスペリエンスで参加します。

会議に最初に参加する出席者 (メイン会議の容量制限まで) は、Teams の会議エクスペリエンスをフルに活用できます。 音声とビデオの共有、共有ビデオの表示、会議チャットへの参加ができます。

主要な会議の容量に達した後に参加する出席者には、表示限定のエクスペリエンスを利用できます。

出席者は、デスクトップ、Web、Teams モバイル (Android および iOS) を通じて表示限定のエクスペリエンスに参加できます。

> [!Note]
> "メイン会議" の現在の制限容量、つまり、完全に対話ができるユーザーの数は 1000 であり、GCC とウェビナーが含まれています。

## <a name="teams-view-only-experience-controls"></a>Teams の表示限定のエクスペリエンス コントロール

[SkypeForBusiness PowerShell モジュール](/powershell/module/skype/?view=skype-ps)、または [MicrosoftTeams モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)のバージョン 2.0.0 以降の [`Set-CsTeamsMeetingPolicy`](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) コマンドレットを使用して、表示限定のエクスペリエンスを有効にします。

推奨される `MicrosoftTeams` モジュールを使用するには

```PowerShell
Install-Module -Name "MicrosoftTeams" -MinimumVersion 2.0.0
Connect-MicrosoftTeams
```

表示限定のエクスペリエンスを有効にするには、次の PowerShell スニペットを使用できます。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

表示限定のエクスペリエンスを無効にするには、PowerShell を使用することもできます。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

今後は Teams 管理センターで表示限定のエクスペリエンスを有効にしたり、無効にしたりすることができます。

## <a name="impact-to-users"></a>ユーザーへの影響

ユーザーのエクスペリエンスは、いくつかの要因によって異なります。

メイン会議の容量に達すると、次の場合、出席者は会議に参加できません。

- 管理者が、Teams で開催者またはテナント全体に対して表示限定のエクスペリエンスを無効にしています。
- 表示限定の出席者はロビーをバイパスできません。 たとえば、会議の開催者が **組織内のユーザー** だけをロビーにバイパスさせようとすると、組織外の出席者が表示限定のみの出席者として参加しようとしても参加できなくなります。

メイン会議の容量に達すると、会議の開催者と発表者には、新しい出席者が表示限定の出席者として参加する、という通知のバナーが表示されます。

  ![主催者と発表者用の Teams クライアントとバナー メッセージ](media/chat-and-banner-message.png)

メイン会議の容量に達すると、会議の出席者は参加前の画面で、表示限定モードで参加しているという通知が表示されます。

  ![Teams の参加前の画面と参加者に表示限定モードで参加することを伝えるメッセージ](media/view-only-pre-join-screen.png)

スペースがある場合は、ユーザーは常にメイン会議に参加します。 メイン会議が容量に達してから、1 人または複数の出席者がメイン会議を離れると、メイン会議には利用可能な容量ができます。 会議に参加 (または再参加) した出席者は、再び容量に達するまでメイン会議に参加します。 表示限定のエクスペリエンスで参加している出席者は、自動的にメイン会議に昇格されることはありません。メイン会議に手動で昇格することはできません。

発表者と出席者の役割が設定されていて、発表者がメイン会議の容量に達した後に会議に参加しようとすると、出席者は表示限定の出席者として参加することになり、他の表示限定の出席者と同じ制限になります。 すべての発表者がメイン会議に参加できるようにするサポートは、後日ロールアウトされます。 開催者にはメイン会議のスペースが常に保証されます。

## <a name="impact-to-meeting-presenters-and-organizers"></a>会議の発表者と開催者に与える影響

会議の発表者と開催者の制限事項は次のとおりです。

- 表示限定の出席者に関する情報はありません。 E-Discovery は、表示限定の出席者に対してサポートしません。
- メイン会議のユーザーは、表示限定の出席者を表示できません。
- 会議から表示限定の出席者を削除できません。

> [!Note]
> 出席者数にはメイン会議のユーザー数だけが反映され、表示限定会議室のユーザー数は反映されません。 そのため、発表者は、表示限定エクスペリエンスのユーザー数を正確にカウントすることができません。

## <a name="experience-for-view-only-attendees"></a>表示限定出席者のエクスペリエンス

Teams の表示限定エクスペリエンスでは、参加者は次の機能を利用できます。

- Teams のメイン会議の参加者の話を聞きます。
- アクティブなスピーカーのビデオ フィードを見ます (アクティブなスピーカーがビデオを共有している場合)。
- デスクトップ共有機能または画面機能を使用して共有されているコンテンツを閲覧します。

表示限定出席者は、会議で次のオプションを利用できません。

- 設定したロビー ポリシーまたはオプションに基づく、ロビーをバイパスするアクセス許可を持っていてない場合は、会議に参加すること。
- オーディオ会議を使用して、表示限定の部屋に参加すること。
- Microsoft Teams Room System を使用するか、クラウド ビデオ相互運用機能 (CVI) サービスを使用して、表示限定の部屋に参加すること。
- オーディオまたはビデオを共有すること。
- 会議チャットを参照または参加すること。
- 参加者がアクティブな発表者でない場合は、会議参加者のビデオ フィードを参照すること。
- (デスクトップ共有または画面共有以外の) PowerPoint Live 機能または個々のアプリケーション共有を使用して共有されている PowerPoint ファイルを参照すること。
- 会議で手を挙げます。
- リアクションを送信または表示します。
- 投票など、Teams 会議に統合されている任意の 3P アプリと対話します。

## <a name="view-only-feature-limitations"></a>表示限定機能の制限

- 表示限定の出席者は、デスクトップと Web でライブ キャプションを表示することだけできます。 現時点でサポートされているのは英語のキャプションのみです。
- 表示限定の出席者はウェビナーに登録できません。
- 表示限定の出席者はストリーミング テクノロジでサポートされます。
- 参加レポートには、表示限定の出席者は含まれません。
- 表示限定の出席者は、1 つのビデオ機能を利用できます。 アクティブな発表者を見ること、または共有されているコンテンツの閲覧はできますが、両方はできません。
- 現在、**ギャラリー**、 **大きなギャラリー**、または表示限定の出席者用の **Together モード** レイアウトはサポートされていません。
- 表示専用の出席者は、"組織内のユーザー"、"組織内のユーザーとゲスト"、"組織内のユーザー、信頼できる組織、ゲスト"、"すべてのユーザー" というロビー ポリシーでのみサポートされます。 表示限定の出席者をサポートしていないロビー ポリシーを使用している場合、表示限定の出席者は会議で拒否されます。 
- 表示限定の出席者は、通常の出席者と同じ待機時間ではありません。<sup>1</sup>

  <sup>1</sup> 表示限定の出席者は、会議で 30 秒のビデオと音声の遅延が発生します。  
