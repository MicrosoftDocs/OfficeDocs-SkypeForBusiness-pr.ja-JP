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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 組織内の未割り当て番号に通話をルーティングする方法について説明します。
ms.openlocfilehash: 810c6b1547586d5494dbba3d0ddbdfc8d5d3c5e1
ms.sourcegitcommit: ffcc4c7d5688fee28f5fdc8bb8e6b78afb1ee626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2022
ms.locfileid: "68795519"
---
# <a name="routing-calls-to-unassigned-numbers"></a>割り当てられていない番号への呼び出しのルーティング

管理者は、組織内の未割り当て番号に通話をルーティングできます。 たとえば、次のように、割り当てられていない番号に呼び出しをルーティングできます。 

- 特定の割り当てられていない番号へのすべての呼び出しをカスタムのお知らせにルーティングします。

- 特定の割り当てられていない番号へのすべての呼び出しをメイン スイッチボードにルーティングします。

割り当てられていない番号への呼び出しは、ユーザー、自動応答または通話キューに関連付けられているリソース アカウント、または呼び出し元にカスタム オーディオ ファイルを再生するアナウンス サービスにルーティングできます。

Teams 管理センターまたは PowerShell を使用して、割り当てられていない番号のルーティングを構成できます。

## <a name="use-teams-admin-center"></a>Teams 管理センターを使用する

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**音声** > 電話番号] に移動 **します**。

2. [ **ルーティング規則** ] タブで、[ **追加**] をクリックします。

3. ルールに名前、説明を付け、ルールの評価順序を指定します。

4. 追加するルールの種類を決定します。 電話番号パターンの種類を事前に構成し、パターンとルーティング オプションを完了するルールを選択できます。 また、電話番号パターンとルーティング オプションの正規表現を直接入力する高度な設定を選択することもできます。

5. **[保存]** を選択します。

割り当てられていない電話番号のルーティング規則を直接作成することもできます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**音声** > 電話番号] に移動 **します**。

2. [ **番号** ] タブで、割り当てられていない電話番号を選択し、ビューの上部にある [ **ルート** ] をクリックします。

4. ルールに名前、説明を付け、ルールの評価順序を指定します。

4. ルーティング オプションを選択します。

5. **[保存]** を選択します。

テスト番号機能を使用して、ルーティング ルールをテストできます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**音声** > 電話番号] に移動 **します**。

2. [ **ルーティング規則** ] タブで、[ **テスト番号**] をクリックします。

3. 電話番号を直接入力するか、[ **番号の選択** ] をクリックし、ドロップダウンから割り当てられていない電話番号のいずれかを選択します。

4. [ **テスト**] を選択します。


## <a name="use-powershell"></a>PowerShell を使用する

割り当てられていない番号に呼び出しをルーティングするには、Teams PowerShell モジュール 2.5.1 以降で使用できる New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment コマンドレットを使用します。

番号の呼び出し番号または範囲と、これらの番号の呼び出しに関連するルーティングを指定する必要があります。 たとえば、次のコマンドは、番号 +1 (555) 222-3333 のすべての呼び出しをリソース アカウント aa@contoso.com にルーティングすることを指定します。

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId

New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

次の例では、番号範囲 +1 (555) 333-0000 から +1 (555) 333-9999 へのすべての呼び出しがアナウンス サービスにルーティングされるように指定します。これにより、オーディオ ファイル MainAnnouncement.wav が呼び出し元に再生されます。

```PowerShell
$Content = [System.IO.File]::ReadAllBytes('C:\Media\MainAnnouncement.wav')

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>メモ

- アナウンスへのルーティングの場合、オーディオ ファイルは呼び出し元に 1 回再生されます。

- 割り当てられていない Microsoft Calling Plan サブスクライバー番号に通話をルーティングするには、テナントで使用可能な [コミュニケーション クレジット](what-are-communications-credits.md)が必要です。

- 割り当てられていない Microsoft Calling Plan サービス番号に通話をルーティングするには、テナントに少なくとも 1 つの **Microsoft Teams 電話 リソース アカウント** ライセンスが必要です。

- サポートされているカスタム オーディオ ファイル形式は、WAV (非圧縮、モノラルまたはステレオの 8/16/32 ビット深度の線形 PCM)、WMA (モノラルのみ)、MP3 です。 オーディオ ファイルの内容は 5 MB を超えることはできません。

> [!NOTE]
> お客様は、Microsoft Teams サービスで音楽またはオーディオ ファイルを使用するために必要なすべての権利とアクセス許可を個別にクリアして保護する責任を負います。 これには、関連するすべての権利者からのオーディオファイル内の音楽、サウンドエフェクト、オーディオ、ブランド、名前、その他のコンテンツに関する知的財産権およびその他の権利が含まれる場合があります。 所有者は、アーティスト、俳優、パフォーマー、ミュージシャン、ソングライター、作曲家、レコードラベル、音楽出版社、組合、ギルド、権利協会、集合管理組織、および音楽著作権、音響効果、オーディオおよびその他の知的財産権を所有、制御またはライセンスする他の当事者を含めることができます。

- Microsoft Teams への受信呼び出しと Microsoft Teams からの発信呼び出しの両方で、割り当てられていない番号範囲に対して通話番号がチェックされます。

- 指定したパターン/範囲にテナント内のユーザーまたはリソース アカウントに割り当てられている電話番号が含まれている場合、これらの電話番号への呼び出しは適切なターゲットにルーティングされ、指定された割り当てられていない番号処理にはルーティングされません。 範囲内の数値の他のチェックはありません。 範囲に有効な外部電話番号が含まれている場合、Microsoft Teams からその電話番号への発信通話は、処理に従ってルーティングされます。


## <a name="related-topics"></a>関連項目

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
