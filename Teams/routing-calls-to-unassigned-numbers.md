---
title: 割り当てられていない番号への通話のルーティング
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
description: 組織内の割り当てられていない番号に通話をルーティングする方法について学習します。
ms.openlocfilehash: 2574a0ac734ed6caee1eadf5a5ee006111713055
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536998"
---
# <a name="routing-calls-to-unassigned-numbers"></a>割り当てられていない番号への通話のルーティング

> [!NOTE]
> この機能は、パブリック プレビュー リリースとして利用できます。

管理者は、組織内の割り当てられていない番号に通話をルーティングできます。 たとえば、次のように、割り当てられていない番号に呼び出しをルーティングできます。 

- すべての呼び出しを、割り当てられていない特定の番号にカスタムアナウンスにルーティングします。

- すべての呼び出しを、割り当てられていない特定の番号にメイン のスイッチボードにルーティングします。

ユーザー、自動応答 または通話キューに関連付けられているリソース アカウント、またはカスタム オーディオ ファイルを呼び出し元に再生するアナウンス サービスに、割り当てられていない番号への呼び出しをルーティングできます。

## <a name="configuration"></a>構成

割り当てられていない番号に呼び出しをルーティングするには、Teams PowerShell モジュール 2.5.1 以降で使用できる New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment コマンドレットを使用します。

番号の呼び出し番号または範囲、およびこれらの番号の呼び出しに関連するルーティングを指定する必要があります。 たとえば、次のコマンドでは、+1 (555) 222-3333 の番号に対する呼び出しはすべてリソース アカウントにルーティング aa@contoso.com。

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

次の例では、+1 (555) 333-0000 から +1 (555) 333-9999 までのすべての呼び出しがアナウンス サービスにルーティングされ、音声ファイル MainAnnouncement.wav が呼び出し元に再生されます。

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>メモ

- アナウンスにルーティングする場合、音声ファイルは呼び出し元に対して 1 回再生されます。

- 割り当てられていない Microsoft 通話プランのサブスクライバー番号に呼び出しをルーティングするには、テナントに使用可能な通信クレジット が [必要です](what-are-communications-credits.md)。

- 割り当てられていない Microsoft 通話プランのサービス番号に呼び出しをルーティングするには、テナントに少なくとも 1 つの仮想電話システム – 仮想ユーザー ライセンスが必要です。

## <a name="related-topics"></a>関連項目

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)