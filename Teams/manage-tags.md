---
title: Microsoft Teams でタグを管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams での組織内でのタグの使用方法を管理する方法について説明します。
ms.openlocfilehash: c63817f5b3ee9c736311982b54dbc9a220564229
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030107"
---
# <a name="manage-tags-in-microsoft-teams"></a>Microsoft Teams でタグを管理する

## <a name="overview"></a>概要

Microsoft Teams のタグを使用すると、ユーザーはチームの一部のユーザーとすばやく簡単に接続できます。 カスタム タグを作成して割り当て、ロール、プロジェクト、スキル、場所などの属性に基づいてユーザーを分類できます。 または [、Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) アプリのスケジュールとシフト情報に基づいて、タグを自動的にユーザーに割り当てることができます (近日公開予定)。 1 人または複数のチーム メンバーにタグを追加した後、@mentions でチャネル投稿のチームの誰でも使用したり、そのタグを割り当てられているユーザーのみを使用して会話を開始したりできます。

前述のように、Teams には 2 種類のタグがあります。

- **カスタム タグ**: チーム所有者とチーム メンバー (機能が有効になっている場合) は、手動でタグを作成してユーザーに割り当てできます。 たとえば、"Designer" タグまたは "Radiologist" タグは、名前を入力することなく、チーム内のユーザーのそれらのセットに到達します。
- **シフトによるタグ** 付け : この機能では、Teams の Shifts アプリでスケジュールとシフト グループ名に一致するタグ [が自動的に割](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) り当てられます。 たとえば、"EngineerOnCall" タグは、チャットまたはチャネル投稿でタグが使用された時点で、Shifts で作業をスケジュールしているすべてのエンジニアに到達します。 シフトによるタグ付けにより、Teams は、ユーザーが情報をすばやく中継する必要があるときに、シフト上のスタッフの名前を知らずに推測を行います。 シフト別のタグ付けは、JDA、Kronos、AMiON のような主要な従業員管理システムによっても、それらを Teams の Shifts と統合することでサポートできます。 この機能を設定する方法の詳細については、「Shift でタグ付けを設定 [する」を参照してください](#set-up-tagging-by-shift)。

> [!NOTE]
> タグはまだプライベート チャネルではサポートされていません。 タグは、GCC High または国防総省 (DoD) 組織では使用できません。 

## <a name="how-tags-work"></a>タグの動作

タグは、手動で追加するか、特定のチームのユーザーに自動的に割り当てることができます。 その後、チャットの [to] @mentionsまたはチームの標準的なチャネルの投稿で、このファイルを使用できます。 Teams でタグを使用する方法の例を次に示します。

- ストア マネージャーがチャネルにアナウンスを投稿して、すべてのレジ係に通知します。
- 病院管理者は、チャネル内のすべてのラジオロジストにメッセージを送信します。
- マーケティング マネージャーは、すべてのデザイナーとグループ チャットを開始します。
- 看護師は、すべてのオンコールカーディロジストにメッセージを送信します。 (近日公開)
- システム エンジニアがチャネルにアナウンスを投稿して、シフト中のすべてのフィールド エンジニアに通知します。 (近日公開)

チャネル会話でタグ@mentionedすると、他のメンバーと同様に、タグに関連付けられているチーム メンバーに通知@mention。

## <a name="manage-custom-tags-for-your-organization"></a>組織のカスタム タグを管理する

管理者は、Microsoft Teams 管理センターで組織全体でタグを使用する方法を制御できます。 現時点では、PowerShell を使用してタグを管理することはできません。

![Microsoft Teams 管理センターのタグ付け設定のスクリーンショット](media/manage-tags-admin-settings.png)

チームには最大 100 のタグを含め、最大 100 人のチーム メンバーをタグに割り当て、1 人のユーザーに最大 25 のタグを割り当てることができます。 

### <a name="set-who-can-add-custom-tags"></a>カスタム タグを追加できるユーザーを設定する

既定では、チーム所有者はカスタム タグを追加できます。 この設定を変更して、チーム所有者とチーム メンバーがタグを作成、編集、削除、管理したり、組織のタグをオフにしたりすることができます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[組織全体 **の設定チーム** の設定]  >  **をクリックします**。
2. [ **タグ付け]** で、[ **タグの** 管理] の横にある次のいずれかのオプションを選択します。

    - **チームの所有者とメンバー**: チームの所有者とメンバーがタグを管理できます。
    - **チーム所有者**: チーム所有者がタグを管理できます。
    - **無効**: タグをオフにします。

### <a name="configure-custom-tags-settings"></a>カスタム タグの設定を構成する

次のタグ設定を構成して、組織全体でのカスタム タグの使用方法を制御できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[組織全体 **の設定チーム** の設定]  >  **をクリックします**。
2. [ **タグ付け**] で、組織のニーズに応じて次の設定を行います。

    - チーム所有者がタグを管理できるユーザーを上書きする **:** この設定を有効にすると、チーム所有者はチーム メンバーがチーム内でタグを作成および管理できるかどうかを設定できます。タグの値は、設定によって管理されるのが各チームの既定値です。 この設定をオフにした場合、チームごとに [タグの管理] 設定を変更することはできません。
    - **推奨される既定のタグ**: これを使用して、既定のタグのセットを追加します。 最大 25 のタグを追加できます。各タグには最大 25 文字を含めることができます。 チームの所有者とメンバー (機能が有効になっている場合) は、これらの提案を使用したり、追加したり、新しいタグセットを作成することができます。
    - **カスタム タグを作成する**: この設定をオンにすると、ユーザーが設定した推奨される既定のタグ以外のタグを追加できます。 これをオフにすると、ユーザーは推奨される既定のタグのみを使用できます。 これをオフにする場合は、1 つ以上の既定のタグを追加してください。

## <a name="manage-custom-tags-settings-for-a-team"></a>チームのカスタム タグ設定を管理する

Microsoft Teams 管理センターで [チーム所有者がタグを管理できるユーザーを上書きする] 設定をオンにした場合、チーム所有者は、メンバーがチーム レベルでタグを追加できるかどうかを設定できます。 これを行うには、チームの **[設定**] タブで、[タグ] に移動し、タグを追加できるユーザーを選択します。

![チーム レベルでのタグ設定のスクリーンショット](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>タグを使用する

カスタム タグを追加する方法と、シフトでタグ付けを設定する方法を次に示します (Teams で Shifts アプリを使用している場合)。 詳細については、「Teams でのタグの [使用」を参照してください](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。

### <a name="create-and-assign-custom-tags"></a>カスタム タグを作成して割り当てる

カスタム タグを作成して割り当てるには、アプリの左側にある **[Teams]** を選択し、一覧からチームを探します。 [ **その他のオプション] を選択し**、[タグの管理] **を選択します**。 ここでは、タグを作成し、チームのユーザーに割り当てできます。

![Teams クライアントでタグを適用する方法のスクリーンショット ](media/manage-tags-teams.png)

タグを削除するには、タグの **横にある [その** 他のオプション] を選択し、[タグの削除] **を選択します**。

### <a name="set-up-tagging-by-shift"></a>シフトでタグ付けを設定する

1. Teams で [、Shifts アプリに移動します](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)。
2. シフト [グループを作成](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) し、ロールなどの属性の後に名前を付けします。 たとえば、EngineerOnCall です。 シフト グループ名はタグの名前です。
3. [チームのメンバーにシフト](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) を割り当て、スケジュールを入力します。 完了したら、Shifts アプリの右上隅にある [チームと共有] を **選択します**。
4. スケジュールされたシフトがタグ付けサービスに設定されるのを 15 分待ちます。
5. Teams でタグを使用する任意の場所でタグを使用します。

シフトによるタグ付けにより、ユーザーはリアルタイムでシフト中のユーザーにリーチできます。 通知は、タグを使用してチャットを開始したり、チャンネル投稿でシフト中のユーザーにのみ送信されます。

## <a name="related-topics"></a>関連項目

[Teams でのタグの使用](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Teams で組織の Shifts アプリを管理する](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Shifts のヘルプ ドキュメント](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
