---
title: リモート Teamsサービスでアプリを使用する
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: リモート デスクトップ サービスで Microsoft Teamsを使用する方法について学習します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7090aac3c5e7ff724a079e7f9d9ffe9d712cd447
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119096"
---
# <a name="teams-in-remote-desktop-services"></a>Teams デスクトップ サービスの設定

この記事では、リモート デスクトップ サービス (RDS) 環境でMicrosoft Teamsの要件と制限事項について説明します。

## <a name="what-is-rds"></a>RDS とは

リモート デスクトップ サービス (RDS) は、エンド ユーザーのニーズに応じて仮想化ソリューションを構築するためのプラットフォームです。 RDS を使用すると、個々の仮想化アプリケーションを提供し、セキュリティで保護されたモバイル およびリモート デスクトップ アクセスを提供し、エンド ユーザーにクラウドからアプリケーションとデスクトップを実行する機能を提供できます。

RDS は、デプロイの柔軟性、コスト効率、拡張性を提供します。 RDS は、オンプレミスデプロイ用の Windows Server 2016、クラウド デプロイ用の Microsoft Azure、堅牢なパートナー ソリューションなど、さまざまなデプロイ オプションを通じて提供されます。
環境と設定に応じて、セッション ベースの仮想化用の RDS ソリューションを仮想デスクトップ インフラストラクチャ (VDI) として設定できます。

現在、Teamsサービス環境内の共有機能は、コラボレーション機能とチャット機能をサポートしています。 最適なユーザー エクスペリエンスを確保するには、この記事のガイダンスに従ってください。

## <a name="teams-on-rds-with-chat-and-collaboration"></a>Teamsコラボレーションを使用して RDS を使用する

組織で Teams のチャットおよび共同作業機能のみを使用する場合は、ユーザーレベル ポリシーを設定して、Teams の通話および会議機能を無効にすることができます。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>通話および会議機能を無効にするポリシーを設定する

Microsoft Teams 管理センターまたは PowerShell を使用してポリシーを設定できます。 ポリシーの変更が反映されるまでに時間がかかる場合があります (数時間)。 指定したアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。

[**通話ポリシー**](teams-calling-policy.md): Teams には、すべての通話機能が無効になっている組み込みの DisallowCalling 通話ポリシーが含まれています。 DisallowCalling ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。

[**会議ポリシー**](meeting-policies-in-teams.md): Teams には、すべての会議機能が無効になっている組み込みの AllOff 会議ポリシーが含まれています。 AllOff ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターを使用してポリシーを割り当てる

DisallowCalling 通話ポリシーと AllOff 会議ポリシーをユーザーに割り当てるには、以下を実行します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。
2. ユーザー名の左側にある を選択してユーザーを選択し、[設定の編集] **を選択します**。
3. 次の手順を実行します。

    a.  [通話 **ポリシー] で** **、[DisallowCalling] を選択します**。

    b.  [会議 **ポリシー] で**、[ **すべてオフ] を選択します**。

4. **[適用]** を選択します。

複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。
2. [**&#x2713;** (チェックマーク)] の列からユーザーを選択します。 すべてのユーザーを選択するには、表の&#x2713;にある [チェック マーク] を選択します。
3. [設定 **の編集]** を選択し、必要な変更を行い、[適用] を **選択します**。

または、次の手順を実行できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。 次に例を示します。

    - [音声通話 **ポリシー**  >  **] に移動し****、[DisallowCalling] を選択します**。
    - [会議の **会議**  >  **ポリシー] に移動し、[** すべてオフ]**を選択します**。

2. **[ユーザーを管理する]** を選択します。
3. [**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。 追加するユーザーごとに、この手順を繰り返します。
4. ユーザーの追加が完了したら、**[保存]** を選択します。

#### <a name="assign-policies-using-powershell"></a>PowerShell を使用してポリシーを割り当てる

次の例は、[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) を使用して、DisallowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。

次の例は、[Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOff 会議ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。