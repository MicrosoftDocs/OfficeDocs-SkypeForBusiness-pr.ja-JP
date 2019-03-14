---
title: Microsoft Teams でのデスクトップ共有を構成する
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 12/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Teams のチャットや会議でユーザーがデスクトップを共有できるように、会議ポリシーを構成します。
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 757f023d5f988e5a4f45c6274358aa51f3417ce0
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464461"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Microsoft Teams でのデスクトップ共有を構成する
============================================

デスクトップを共有すると、ユーザーは会議やチャット中に画面やアプリを表示できます。 管理者が Microsoft Teams で画面共有を構成すると、ユーザーは画面全体、アプリ、ファイルを共有できるようになります。 ユーザーによる制御の付与または要求の許可、PowerPoint 共有の許可、ホワイトボードの追加、共有メモの許可を設定できます。 匿名ユーザーや外部ユーザーが共有画面の制御を要求できるかどうかも構成できます。

画面共有を構成するには、新しい会議ポリシーを作成し、そのポリシーを管理対象ユーザーに割り当てます。

**Microsoft Teams 管理センターで**

1. **[会議]** > **[会議ポリシー]** の順に選択します。

    ![[会議ポリシー] を選択する](media/configure-desktop-sharing-image1.png)

2. **[会議ポリシー]** ページで、**[新しいポリシー]** を選択します。

    ![新しいポリシーを選択する](media/configure-desktop-sharing-image2.png)

3. ポリシーに一意のタイトルを指定し、簡単な説明を入力します。

4. **[コンテンツの共有]** の下にある、**[画面共有モード]** ドロップダウン リストから選択します。

   - **[画面全体]**: ユーザーはデスクトップ全体を共有できます。
   - **[1 つのアプリケーション]**: ユーザーの画面共有は 1 つのアクティブなアプリケーションに制限されます。
   - **[無効]**: 画面共有をオフにします。

    ![画面共有モードを選択する](media/configure-desktop-sharing-image3.png)

5. 次の設定をオンまたはオフにします。

    - **[参加者による制御の付与または要求を許可する]**: チームのメンバーによる、発表者のデスクトップまたはアプリケーションの制御の付与や要求を許可します。
    - **[外部の参加者による制御の付与または要求を許可する]**: ゲストや外部の (フェデレーション) ユーザーによる、発表者のデスクトップまたはアプリケーションの制御の付与や要求を許可します。
    - **[PowerPoint 共有を許可する]**: ユーザーによる、PowerPoint プレゼンテーションのアップロードや共有ができる会議の作成を許可します。
    - **[ホワイトボードを許可する]**: ユーザーによるホワイトボードの共有を許可します。
    - **[共有メモを許可する]**: ユーザーが共有メモを取ることを許可します。

6. **[保存]** をクリックします。

## <a name="use-powershell-to-configure-shared-desktop"></a>PowerShell を使用して共有デスクトップを構成する

[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) コマンドレットを使用して、デスクトップ共有を制御することもできます。 次のパラメーターを設定します。

- Description
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[csTeamsMeetingPolicy コマンドレットの使用方法に関する詳細情報](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)。

