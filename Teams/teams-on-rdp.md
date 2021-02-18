---
title: リモート デスクトップ サービスで Teams を使用する
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: リモート デスクトップ サービスで Microsoft Teams を使用する方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ac88778fca7034446d0ec42a0a4a65d7c76f979
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278899"
---
# <a name="teams-in-remote-desktop-services"></a>リモート デスクトップ サービスの Teams

この記事では、リモート デスクトップ サービス (RDS) 環境で Microsoft Teams を使用する場合の要件と制限事項について説明します。

## <a name="what-is-rds"></a>RDS とは

リモート デスクトップ サービス (RDS) は、エンド ユーザーのニーズに合った仮想化ソリューションを構築するための選択のプラットフォームです。 RDS を使用すると、仮想化された個々のアプリケーションを提供し、セキュリティで保護されたモバイルおよびリモート デスクトップ アクセスを提供し、エンド ユーザーにクラウドからアプリケーションとデスクトップを実行する機能を提供できます。

RDS は、展開の柔軟性、コスト効率、拡張性を提供します。 RDS は、オンプレミス展開用の Windows Server 2016、クラウド展開用の Microsoft Azure、強力なパートナー ソリューションなど、さまざまな展開オプションによって提供されます。
環境と環境設定に応じて、仮想デスクトップ インフラストラクチャ (VDI) としてセッション ベースの仮想化用に RDS ソリューションを設定できます。

現在、リモート デスクトップ サービス環境の Teams は、共同作業とチャット機能をサポートして利用できます。 最適なユーザー エクスペリエンスを確保するには、この記事のガイダンスに従ってください。

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>チャットと共同作業を備えた VDI 上の Teams

組織で Teams のチャットおよび共同作業機能のみを使用する場合は、ユーザーレベル ポリシーを設定して、Teams の通話および会議機能を無効にすることができます。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>通話および会議機能を無効にするポリシーを設定する

Microsoft Teams 管理センターまたは PowerShell を使用してポリシーを設定できます。 ポリシーの変更が反映されるには、時間 (数時間) かかる場合があります。 指定したアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。

[**通話ポリシー**](teams-calling-policy.md): Teams には、すべての通話機能が無効になっている組み込みの DisallowCalling 通話ポリシーが含まれています。 DisallowCalling ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。

[**会議ポリシー**](meeting-policies-in-teams.md): Teams には、すべての会議機能が無効になっている組み込みの AllOff 会議ポリシーが含まれています。 AllOff ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターを使用してポリシーを割り当てる

ユーザーに DisallowCalling 呼び出しポリシーと AllOff 会議ポリシーを割り当てるには、

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。
2. ユーザー名の左側を選択してユーザーを選択し、[設定の編集] **を選択します**。
3. 次の手順を実行します。

    a.  [通話 **ポリシー] の**[ **通話禁止] を選択します**。

    b.  [会議 **ポリシー] で**[ **すべてオフ] を選択します**。

4. **[適用]** を選択します。

複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。
2. [**&#x2713;** (チェックマーク)] の列からユーザーを選択します。 すべてのユーザーを選択するには、表&#x2713;にあるチェック マーク (チェック マーク) を選択します。
3. [ **設定の編集]** を選択し、必要な変更を行い、[適用] を **選択します**。

または、次の手順を実行できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。 次に例を示します。

    - 音声通話 **ポリシー**  >  **に移動し、[****通話の禁止] を選択します**。
    - 会議会議 **ポリシー**  >  **に移動し、[** すべてオフ]**を選択します**。

2. **[ユーザーを管理する]** を選択します。
3. [**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。 追加するユーザーごとに、この手順を繰り返します。
4. ユーザーの追加が完了したら、**[保存]** を選択します。

#### <a name="assign-policies-using-powershell"></a>PowerShell を使用してポリシーを割り当てる

次の例は、[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) を使用して、DisallowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。

次の例は、[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOff 会議ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。
