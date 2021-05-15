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
description: 組織でタグを使用する方法を管理する方法についてMicrosoft Teams。
ms.openlocfilehash: ab57fe5a0528ad5e33b20929bd224cb33273197e
ms.sourcegitcommit: 745b37921a878f1b524a274bfb2fd0732716a5c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2021
ms.locfileid: "52498782"
---
# <a name="manage-tags-in-microsoft-teams"></a>Microsoft Teams でタグを管理する

## <a name="overview"></a>概要

タグをMicrosoft Teams、ユーザーがチームの一部のユーザーとすばやく簡単に接続できます。 カスタム タグを作成して割り当て、ロール、プロジェクト、スキル、場所などの属性に基づいてユーザーを分類できます。 または、Shifts アプリ のスケジュールとシフト情報に基づいて、タグをユーザーに自動的 [に割り当てることができます](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts)。 タグを 1 人または複数のチーム メンバーに追加した後は、チャネル投稿でチームの誰でも @mentions で使用したり、そのタグが割り当てられているユーザーのみと会話を開始したりすることができます。

前述のように、2 種類のタグがTeams。

- **カスタム タグ**: チーム所有者とチーム メンバー (機能が有効になっている場合) は、手動でタグを作成してユーザーに割り当てできます。 たとえば、"Designer" または "Radiradi" タグは、名前を入力することなく、チームのこれらのユーザー セットに到達します。
- **シフトによるタグ** 付け: この機能を使用すると、ユーザーには、スケジュールとシフト グループ名に一致するタグが、Teams の [Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)アプリで自動的に割り当てられます。 たとえば、"EngineerOnCall" タグは、チャットまたはチャネルの投稿でタグが使用された時点で、シフトで作業をスケジュールしているすべてのエンジニアに到達します。 シフトによるタグ付Teams、ユーザーが情報をすばやく中継する必要があるときに、シフト上のスタッフの名前を知ることから推測を取り出します。 シフトによるタグ付けは、JDA、Kronos、AMiON のような主要な従業員管理システムによってもサポートされ、Teams の Shifts と統合されます。 この機能を設定する方法の詳細については、「Shift でタグ [付けを設定する」を参照してください](#set-up-tagging-by-shift)。

> [!NOTE]
> タグは、プライベート チャネルではまだサポートされていません。 タグは、GCC国防総省 (DoD) 組織では使用できません。 

## <a name="how-tags-work"></a>タグの動作

タグは、手動で追加したり、特定のチームのユーザーに自動的に割り当てたりすることができます。 チャットの [to] @mentionsまたはチームの標準チャネルの投稿で使用できます。 次に、タグを使用する方法の例を示Teams。

- ストア マネージャーがチャネルにアナウンスを投稿して、すべてのレジ係に通知します。
- 病院の管理者は、チャネル内のすべてのラジオロジストにメッセージを送信します。
- マーケティング マネージャーは、すべてのデザイナーとグループ チャットを開始します。
- 看護師が、すべてのオンコールのカーディジストにメッセージを送信します。 (近日公開)
- システム エンジニアは、すべてのオンシフト フィールド エンジニアに通知するアナウンスをチャネルに投稿します。 (近日公開)

チャネル会話でタグ@mentionedすると、そのタグに関連付けられているチーム メンバーには、他のチーム メンバーと同様に通知が@mention。

## <a name="manage-custom-tags-for-your-organization"></a>組織のカスタム タグを管理する

管理者は、管理センターで組織全体でタグを使用する方法Microsoft Teamsできます。 現時点では、PowerShell を使用してタグを管理することはできません。

![管理センターのタグ設定Microsoft Teamsスクリーンショット](media/manage-tags-admin-settings.png)

チームには最大 100 のタグを含め、最大 100 人のチーム メンバーをタグに割り当て、1 人のユーザーに最大 25 のタグを割り当てることができます。 

### <a name="set-who-can-add-custom-tags"></a>カスタム タグを追加できるユーザーを設定する

既定では、チーム所有者はカスタム タグを追加できます。 この設定を変更して、チーム所有者とチーム メンバーがタグを作成、編集、削除、管理したり、組織のタグをオフにしたりすることができます。

1. 管理センターの左側のナビゲーションMicrosoft Teams、[**組織全体の** 設定] をクリックTeams  >  **します**。
2. [ **タグの管理**] の横 **にある**[タグの管理] で、次のいずれかのオプションを選択します。

    - **チームの所有者とメンバー**: チームの所有者とメンバーがタグを管理できます。
    - **チーム所有者**: チーム所有者がタグを管理できます。
    - **無効**: タグをオフにします。

### <a name="configure-custom-tags-settings"></a>カスタム タグ設定を構成する

次のタグ設定を構成して、組織全体でカスタム タグを使用する方法を制御できます。

1. 管理センターの左側のナビゲーションMicrosoft Teams、[**組織全体の** 設定] をクリックTeams  >  **します**。
2. [ **タグ付け]** で、組織のニーズに応じて、次の設定を行います。

    - **チーム** 所有者がタグを管理できるユーザーをオーバーライドする: この設定を有効にすると、チーム所有者は、チーム メンバーがチーム内でタグを作成および管理できるかどうかを設定できます。タグの値は、各チームの既定値を設定して管理されます。 この設定をオフにした場合、[ **タグ** は設定によって管理されます] をチームごとに変更することはできません。
    - **推奨される既定のタグ**: 既定のタグのセットを追加する場合に使用します。 最大 25 のタグを追加できます。各タグには最大 25 文字を含めることができます。 チームの所有者とメンバー (機能が有効になっている場合) は、これらの提案を使用したり、追加したり、新しいタグ セットを作成することができます。
    - **カスタム タグを作成する**: ユーザーが設定した推奨される既定のタグ以外のタグを追加するには、この設定をオンにします。 これがオフになっている場合、ユーザーは推奨される既定のタグのみを使用できます。 これをオフにした場合は、必ず既定のタグを 1 つ以上追加してください。

## <a name="manage-custom-tags-settings-for-a-team"></a>チームのカスタム タグ設定を管理する

Microsoft Teams 管理センターで[チーム所有者がタグを管理できるユーザーをオーバーライドする] 設定をオンにした場合、チーム所有者はメンバーがチーム レベルでタグを追加できるかどうかを設定できます。 これを行うには、チームの **[設定]** タブで 、[タグ]に移動し、タグを追加できるユーザーを選択します。

![チーム レベルでのタグ設定のスクリーンショット](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>タグを使用する

カスタム タグを追加する方法と、Shift でタグ付けを設定する方法を次に示します (Shifts アプリを使用している場合は、Teams)。 詳細については、「 でタグを[使用する 」をTeams。](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

### <a name="create-and-assign-custom-tags"></a>カスタム タグを作成して割り当てる

カスタム タグを作成して割り当てるには、アプリ **Teams** の左側にある [カスタム タグ] を選択し、一覧からチームを検索します。 **[その他のオプション] を選択し**、[タグの管理]**を選択します**。 ここでは、タグを作成し、チームのユーザーに割り当てできます。

![クライアントでタグを適用する方法Teamsスクリーンショット ](media/manage-tags-teams.png)

タグを削除するには、 **タグの横にある [その** 他のオプション] を選択し、[タグの削除] **を選択します**。

### <a name="set-up-tagging-by-shift"></a>シフトによるタグ付けを設定する

シフトによるタグ付けにより、ユーザーはリアルタイムでシフト上のユーザーにアクセスできます。 Teams、スケジュールとシフト グループ名に一致するタグを持つユーザーを Shifts アプリから自動的に割り当て、動的なロールベースのメッセージングを有効にできます。 通知は、タグがチャットの開始またはチャネルの投稿に使用された時点でシフト中のユーザーにのみ送信されます。 

1. このTeams、Shifts アプリ[に移動します](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)。
2. シフト [グループを作成](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) し、ロールなどの属性の後に名前を付えます。 たとえば、EngineerOnCall です。 シフト グループ名はタグの名前です。
3. [チームのメンバーにシフト](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) を割り当て、スケジュールを入力します。 完了したら、Shifts アプリの右上隅にある [チームと共有] **を選択します**。
4. スケジュールされたシフトがタグ付けサービスに設定されるのを 15 分待ちます。
5. タグは、タグを使用する場所Teams。

## <a name="related-topics"></a>関連トピック

[Teams でタグを使用する](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Teams で組織の Shifts アプリを管理する](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Shifts のヘルプ ドキュメント](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
