---
title: Microsoft Teams でのデスクトップ共有を構成する
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams のチャットや会議でユーザーがデスクトップを共有できるように、会議ポリシーを構成します。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 366aaeb4f48670ae04d4b53d21196ef2d9e81fb4
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825545"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Microsoft Teams でのデスクトップ共有を構成する
============================================

デスクトップを共有すると、ユーザーは会議やチャット中に画面やアプリを表示できます。 管理者が Microsoft Teams で画面共有を構成すると、ユーザーは画面全体、アプリ、ファイルを共有できるようになります。 ユーザーによる制御の付与または要求の許可、PowerPoint 共有の許可、ホワイトボードの追加、共有メモの許可を設定できます。 匿名ユーザーや外部ユーザーが共有画面の制御を要求できるかどうかも構成できます。

画面共有を構成するには、新しい会議ポリシーを作成し、そのポリシーを管理対象ユーザーに割り当てます。

**[Microsoft Teams 管理センター](https://admin.teams.microsoft.com/)で**

1. **[会議]** > **[会議ポリシー]** の順に選択します。

    ![選択された会議ポリシーを示すスクリーン ショット](media/configure-desktop-sharing-image1.png)

2. **[会議ポリシー]** ページで、**[新しいポリシー]** を選択します。

    ![会議ポリシーのメッセージを示すスクリーン ショット](media/configure-desktop-sharing-image2.png)

3. ポリシーに一意のタイトルを指定し、簡単な説明を入力します。

4. **[コンテンツの共有]** の下にある、**[画面共有モード]** ドロップダウン リストから選択します。

   - **[画面全体]**: ユーザーはデスクトップ全体を共有できます。
   - **[1 つのアプリケーション]**: ユーザーの画面共有は 1 つのアクティブなアプリケーションに制限されます。
   - **[無効]**: 画面共有をオフにします。

    ![共有モード オプションを示すスクリーン ショット](media/configure-desktop-sharing-image3.png)

5. 次の設定をオンまたはオフにします。

    - **[参加者による制御の付与または要求を許可する]**: チームのメンバーによる、発表者のデスクトップまたはアプリケーションの制御の付与や要求を許可します。
    - **[外部の参加者による制御の付与または要求を許可する]**: ゲストや外部の (フェデレーション) ユーザーによる、発表者のデスクトップまたはアプリケーションの制御の付与や要求を許可します。
    - **[PowerPoint 共有を許可する]**: ユーザーによる、PowerPoint プレゼンテーションのアップロードや共有ができる会議の作成を許可します。
    - **[ホワイトボードを許可する]**: ユーザーによるホワイトボードの共有を許可します。
    - **[共有メモを許可する]**: ユーザーが共有メモを取ることを許可します。

6. **[保存]** をクリックします。

## <a name="use-powershell-to-configure-shared-desktop"></a>PowerShell を使用して共有デスクトップを構成する

[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) コマンドレットを使用して、デスクトップ共有を制御することもできます。 次のパラメーターを設定します。

- Description
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[csTeamsMeetingPolicy コマンドレットの使用方法に関する詳細情報](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)。

