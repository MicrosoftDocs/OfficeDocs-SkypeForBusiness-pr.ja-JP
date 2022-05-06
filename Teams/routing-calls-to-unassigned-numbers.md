---
title: 割り当てられていない番号への呼び出しのルーティング
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 組織内の割り当てられていない番号に通話をルーティングする方法について説明します。
ms.openlocfilehash: f53e83b3d4f26123feed70bdecad32cb45bc5588
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442795"
---
# <a name="routing-calls-to-unassigned-numbers"></a>割り当てられていない番号への呼び出しのルーティング

管理者は、組織内の割り当てられていない番号に通話をルーティングできます。 たとえば、次のように、割り当てられていない番号に呼び出しをルーティングできます。 

- 割り当てられていない特定の番号にすべての呼び出しをカスタムのお知らせにルーティングします。

- 割り当てられていない特定の番号にすべての呼び出しをメインスイッチボードにルーティングします。

割り当てられていない番号への呼び出しは、ユーザー、自動応答または通話キューに関連付けられているリソース アカウント、またはカスタム オーディオ ファイルを呼び出し元に再生するアナウンス サービスにルーティングできます。

## <a name="configuration"></a>構成

割り当てられていない番号に呼び出しをルーティングするには、PowerShell モジュール 2.5.1 以降で使用できる New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment コマンドレットTeams使用します。

これらの番号の呼び出しに対して、呼び出された番号または番号の範囲と、関連するルーティングを指定する必要があります。 たとえば、次のコマンドは、番号 +1 (555) 222-3333 へのすべての呼び出しがリソース アカウント aa@contoso.com にルーティングされるように指定します。

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

次の例では、番号範囲 +1 (555) 333-0000 から +1 (555) 333-9999 へのすべての呼び出しがアナウンス サービスにルーティングされるように指定します。これにより、オーディオ ファイル MainAnnouncement.wav が呼び出し元に再生されます。

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>メモ

- アナウンスにルーティングする場合、オーディオ ファイルは呼び出し元に 1 回再生されます。

- 割り当てられていない Microsoft 通話プランサブスクライバー番号に通話をルーティングするには、テナントで使用可能な [通信クレジット](what-are-communications-credits.md)が必要です。

- 割り当てられていない Microsoft Calling Plan サービス番号に呼び出しをルーティングするには、テナントに少なくとも 1 つの電話システム仮想ユーザー ライセンスが必要です。

- サポートされるカスタム オーディオ ファイル形式は、WAV (モノラルまたはステレオで 8/16/32 ビット深度の非圧縮の線形 PCM)、WMA (モノラルのみ)、MP3 です。 オーディオ ファイルのコンテンツは 5 MB を超えることはできません。

## <a name="related-topics"></a>関連項目

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
