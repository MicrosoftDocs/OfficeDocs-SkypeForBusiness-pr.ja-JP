---
title: マイクロソフトのチームでデスクトップの共有を構成します。
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 12/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: チーム チャットや会議での自分のデスクトップを共有できるようにするのには会議ポリシーを構成します。
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 422d5fb3a19dad2e14e0cdf54a532b0afc6eed67
ms.sourcegitcommit: ea6ee8ce28e82fcd7c07554c3428ae242d6f04da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2018
ms.locfileid: "27202506"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>マイクロソフトのチームでデスクトップの共有を構成します。
============================================

デスクトップの共有には、ユーザーが会議出席依頼やチャット中に、画面またはアプリケーションを提示することができます。 管理者は、画面を画面全体、アプリケーション、またはファイルを共有できるようにするのには、マイクロソフトのチームで共有を構成できます。 ユーザーを与える制御を要求、PowerPoint の共有を許可する、ホワイト ボードの追加やノートの共有を許可することもできます。 匿名または外部のユーザーが共有画面のコントロールを要求できるかどうかを構成することもできます。

画面共有を構成するには、新しい会議ポリシーを作成し、管理するユーザーに割り当てます。

マイクロソフトのチームとビジネス管理センターの Skype。

1. **会議**を選択して > **ミーティングのポリシー**です。

    ![ミーティングのポリシーを選択します。](media/configure-desktop-sharing-image1.png)

2. [**ミーティングのポリシー** ] ページで、**新しいポリシー**を選択します。

    ![新しいポリシーを選択します。](media/configure-desktop-sharing-image2.png)

3. ポリシー固有のタイトルを提供し、簡単な説明を入力します。

4. **コンテンツの共有**の下にあるドロップ ダウン リストから**画面共有モード**を選択します。

   - **全体画面**– を使うと、その全体のデスクトップを共有できます。
   - **1 つのアプリケーション**では、1 つのアクティブなアプリケーションを制限画面の共有をユーザーことができます。
   - **無効**– 画面の共有を無効にします。

    ![共有モードの画面を選択します。](media/configure-desktop-sharing-image3.png)

5. 次の設定を有効または無効にします。

    - 提供または、発表者のデスクトップまたはアプリケーションの制御を要求**したり制御を要求する参加者を許可する**: チームのメンバーを使用します。
    - 来園者は、**制御を要求したりする外部の参加者を許可する**- と (連合) の外部のユーザーが付与または、発表者のデスクトップまたはアプリケーションの制御を要求します。
    - **PowerPoint の共有**- には、ユーザーが PowerPoint のプレゼンテーションをアップロードして共有できるように会議を作成することができます。
    - **許可するホワイト ボード**-では、ホワイト ボードを共有することができます。
    - **ノートの共有を許可する**-には、ユーザーが共有ノートを取ることができます。

6. [**保存**] をクリックします。

## <a name="use-powershell-to-configure-shared-desktop"></a>PowerShell を使用して、デスクトップの共有を構成するには

デスクトップの共有を制御する[セット CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)コマンドレットを使用することもできます。 次のパラメーターを設定します。

- 説明
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[CsTeamsMeetingPolicy コマンドレットを使用してに関する詳細を表示](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)します。

