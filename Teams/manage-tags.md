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
description: Microsoft Teams で組織でタグがどのように使用されるのかについて説明します。
ms.openlocfilehash: 9d9ba4584572ad1e1707c250ee92c49e9aaec7fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831237"
---
# <a name="manage-tags-in-microsoft-teams"></a>Microsoft Teams でタグを管理する

> [!NOTE]
> この記事で説明されている機能の 1つ、シフトによるタグ付けはまだリリースされていません。 これは発表され、近日公開される予定です。 管理者は、メッセージ センター ([Microsoft 365 管理センター](https://portal.office.com/adminportal/home)) でこの機能のリリース日を確認できます。 Teams 機能の最新情報を入手するには、「[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)」を参照してください。

## <a name="overview"></a>概要

Microsoft Teams のタグを使用すると、ユーザーはチームの一部のユーザーとすばやく簡単に接続できます。 カスタム タグを作成して割り当て、役割、プロジェクト、スキル、場所などの属性に基づいてユーザーを分類できます。 または [、Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) アプリのスケジュールとシフト情報に基づいて、タグをユーザーに自動的に割り当てることができます (近日公開予定)。 1 人または複数のチーム メンバーにタグを追加した後は、チャネルの投稿でチームの誰でも @mentions でタグを使用したり、そのタグが割り当てられているユーザーのみと会話を開始したりするために使用できます。

前述のように、Teams には 2 種類のタグがあります。

- **カスタム タグ**: チーム所有者とチーム メンバー (機能が有効な場合) は、手動でタグを作成してユーザーに割り当てできます。 たとえば、"Designer" タグまたは "Radiradiradi" タグは、名前を入力することなく、チーム内のユーザー のセットに到達します。
- **シフトによるタグ付** け (近日公開): この機能を使用すると、Teams の [Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) アプリでスケジュールとシフト グループ名に一致するタグが自動的に割り当てられます。 たとえば、"EngineerOnCall" タグは、チャットまたはチャネル投稿でタグが使用された時点で作業するためにシフトでスケジュールされているすべてのエンジニアに到達します。 シフトによるタグ付けにより、Teams は、ユーザーが情報をすばやく中継する必要があるときに、シフト上のスタッフの名前を知ることから推測を取り出します。 シフト別のタグ付けは、Teams の Shifts と統合することで、JDA、Kronos、AMiON のような主要な人員管理システムによってもサポートされます。 この機能の設定方法の詳細については、「シフトでタグ付けを設定する [」を参照してください](#set-up-tagging-by-shift-coming-soon)。

> [!NOTE]
> プライベート チャネルでは、タグはまだサポートされていません。 タグは、米国政府機関コミュニティ クラウド (GCC)、GCC High、または国防総省 (DoD) 組織ではまだ利用できません。 

## <a name="how-tags-work"></a>タグの動作

タグは、手動で追加したり、特定のチームのユーザーに自動的に割り当てたりすることができます。 チャットの [to] 行@mentions、またはチームの標準チャネルの投稿で、この機能を使用できます。 Teams でタグを使用する方法の例を次に示します。

- 店舗管理者は、すべての店舗に通知するアナウンスをチャネルに投稿します。
- 病院の管理者がチャネル内のすべてのラジオロジストにメッセージを送信します。
- マーケティング マネージャーは、すべてのデザイナーとグループ チャットを開始します。
- 看護師が、すべてのオンコール カーディロジストにメッセージを送信します。 (近日公開)
- システム エンジニアは、シフト上のすべてのフィールド エンジニアに通知するアナウンスをチャネルに投稿します。 (近日公開)

チャネルの会話@mentionedタグが追加された場合、他の会話と同様に、タグに関連付けられているチーム メンバーに通知が@mention。

## <a name="manage-custom-tags-for-your-organization"></a>組織のカスタム タグを管理する

管理者は、Microsoft Teams 管理センターで組織全体でタグを使用する方法を制御できます。 現時点では、PowerShell を使用してタグを管理することはできません。

![Microsoft Teams 管理センターのタグ付け設定のスクリーンショット](media/manage-tags-admin-settings.png)

チームには最大 100 のタグを割り当て、最大 100 人のチーム メンバーをタグに割り当て、1 人のユーザーに最大 25 のタグを割り当てることができます。 

### <a name="set-who-can-add-custom-tags"></a>カスタム タグを追加できるユーザーを設定する

既定では、チーム所有者はカスタム タグを追加できます。 この設定を変更して、チーム所有者とチーム メンバーがタグの作成、編集、削除、管理を行えるか、組織のタグをオフにできます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[組織全体の設定チームの **設定]**  >  **をクリックします**。
2. [ **タグ付け] の**[ **タグの管理** 方法] の横で、次のいずれかのオプションを選択します。

    - **チームの所有者とメンバー**: チームの所有者とメンバーがタグを管理できます。
    - **チーム所有者**: チーム所有者にタグの管理を許可します。
    - **無効**: タグをオフにします。

### <a name="configure-custom-tags-settings"></a>カスタム タグの設定を構成する

組織全体でカスタム タグを使用する方法を制御するために、次のタグ設定を構成できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[組織全体の設定チームの **設定]**  >  **をクリックします**。
2. [ **タグ付け]** で、組織のニーズに応じて、次を設定します。

    - チーム所有者がタグを管理できるユーザーを上書き **する:** この設定をオンにすると、チーム所有者はチーム メンバーがチーム内でタグを作成および管理できるかどうかを設定できます。タグの値は、各チームの既定値に設定することで管理されます。 この設定をオフにすると、タグ **は** 設定によって管理され、チームごとに変更することはできません。
    - **推奨される既定のタグ**: 既定のタグのセットを追加する場合に使用します。 最大 25 のタグを追加できます。各タグには最大 25 文字を含めることができます。 チーム所有者とメンバー (機能が有効になっている場合) は、これらの候補を使用したり、それらの候補に追加したり、新しいタグ セットを作成することができます。
    - **カスタム タグを作成する**: ユーザーが設定した推奨される既定のタグ以外のタグを追加するには、この設定をオンにします。 この設定をオフにすると、ユーザーは推奨される既定のタグのみを使用できます。 これをオフにする場合は、1 つ以上の既定のタグを追加してください。

## <a name="manage-custom-tags-settings-for-a-team"></a>チームのカスタム タグ設定を管理する

Microsoft Teams 管理センターで [チーム所有者がタグを管理できるユーザーを上書きする] 設定をオンにした場合、チーム所有者はメンバーがチーム レベルでタグを追加できるかどうかを設定できます。 これを行うには、チームの[設定] タブで[タグ] に移動し、タグを追加できるユーザーを選択します。

![チーム レベルでのタグ設定のスクリーンショット](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>タグを使用する

カスタム タグを追加する方法と、シフトでタグを設定する方法を示します (Teams で Shifts アプリを使用している場合)。 詳細については、「Teams でタグを [使用する」を参照してください](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。

### <a name="create-and-assign-custom-tags"></a>カスタム タグを作成して割り当てる

カスタム タグを作成して割り当てるには、アプリの左側にある **[Teams]** を選択し、一覧から自分のチームを見つける必要があります。 **[ 1] を選択し、[** その他のオプション] を選択し、[タグ **の管理] を選択します**。 ここでは、タグを作成し、チームのユーザーに割り当てできます。

![Teams クライアントでタグを適用する方法のスクリーンショット ](media/manage-tags-teams.png)

タグを削除するには、タグの横にある [その他のオプション] **を選択** し、[タグの削除] を **選択します**。

### <a name="set-up-tagging-by-shift-coming-soon"></a>シフトによるタグ付けを設定する (近日公開予定)

1. Teams で [、Shifts アプリに移動します](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)。
2. シフト [グループを作成し](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) 、役割などの属性の後に名前を付けします。 たとえば、EngineerOnCall などです。 シフト グループ名はタグの名前です。
3. [チームのメンバーにシフト](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) を割り当て、スケジュールを入力します。 完了したら、Shifts アプリの右上隅にある [チームと共有] を **選択します**。
4. スケジュールされたシフトがタグ付けサービスに追加されるのを 15 分待ちます。
5. Teams でタグを使用する任意の場所でタグを使用します。

シフトによるタグ付けにより、ユーザーはリアルタイムでシフト上のユーザーにアクセスできます。 通知は、タグを使用してチャットを開始した時点またはチャネルの投稿にシフトしているユーザーにのみ送信されます。

## <a name="related-topics"></a>関連項目

[Teams でタグを使用する](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Teams で組織の Shifts アプリを管理する](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Shifts のヘルプ ドキュメント](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
