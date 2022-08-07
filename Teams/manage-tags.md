---
title: Microsoft Teams でタグを管理する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams で組織でのタグの使用方法を管理する方法について説明します。
ms.openlocfilehash: bdb4fcbdd4c4d197dcdc778b9c15130071ad37fc
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267952"
---
# <a name="manage-tags-in-microsoft-teams"></a>Microsoft Teams でタグを管理する

## <a name="overview"></a>概要

Microsoft Teams のタグを使用すると、チーム内の一部のユーザーとすばやく簡単につながることができます。 役割、プロジェクト、スキル、場所などの属性に基づいてユーザーを分類するカスタム タグを作成して割り当てることができます。 または、[シフト アプリ](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts)のスケジュールとシフト情報に基づいて、ユーザーにタグを自動的に割り当てることができます。 1 つまたは複数のチーム メンバーにタグを追加した後は、チャネル投稿内のチームのすべてのユーザーが@mentionsで使用したり、会話のそのタグを割り当てられたユーザーのみに通知したりできます。

前述のとおり、Teams には 2 種類のタグがあります。

- **カスタム タグ**: チームの所有者とチーム メンバー (機能が有効になっている場合) は、手動でタグを作成し、ユーザーに割り当てることができます。 たとえば、"デザイナー" タグまたは "Radi digest" タグは、名前を入力しなくてもチームのユーザーのセットに到達します。
- **シフトでのタグ付け**: この機能を使用すると、Teams の [シフトアプリ](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)内のスケジュールとシフト グループの名前に一致するタグが自動的にユーザーに割り当てられます。 たとえば、"EngineerOnCall" タグは、Shifts でスケジュールされているすべてのエンジニアに、チャットまたはチャネルの投稿でタグが使用された時点で作業するように到達します。 シフトでのタグ付けを使用すると、ユーザーが情報をすばやく伝える必要がある場合に、シフト中のスタッフの名前を推測することなく知ることができます。

> [!NOTE]
> タグは、プライベート チャネルまたは共有チャネルではサポートされていません。

## <a name="how-tags-work"></a>タグの動作

タグは、特定のチームのユーザーに手動で追加することも、自動的に割り当てることもできます。 その後、チャットまたはチームの標準チャネルの投稿の **宛先** 行の @メンションで使用できます。 Teams でタグを使用する方法の例を次に示します。

- ストア マネージャーがチャネルにお知らせを投稿して、すべてのレジ係に通知する。
- 病院の管理者が、チャネル内のすべての放射線科医にメッセージを送信する。
- マーケティング マネージャーが、すべてのデザイナーとグループ チャットを開始する。

チャネルの会話でタグが @メンションされると、他の @メンションと同様に、タグに関連付けられているチーム メンバーに通知が送信されます。

## <a name="manage-custom-tags-for-your-organization"></a>組織のカスタム タグを管理する

管理者は、Microsoft Teams 管理センターで、タグを組織全体で使用する方法を制御できます。 PowerShell を使用してタグを管理することはできません。

:::image type="content" source="media/manage-tags-admin-settings.png" alt-text="Microsoft Teams 管理センターのタグ付け設定のスクリーンショット。":::

各チームは最大 100 個のタグを持つことができ、1 つのタグに対して最大 100 人のチーム メンバーを、1 人のユーザーに対して最大 25 個のタグを割り当てることができます。

### <a name="set-who-can-add-custom-tags"></a>カスタム タグを追加できるユーザーを設定する

既定では、チームの所有者がカスタム タグを追加できます。 この設定を変更して、チームの所有者とチーム メンバーがタグを作成、編集、削除、管理できるようにしたり、組織のタグを無効にしたりできます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[ **Teams** \> の **設定**] をクリックします。

2. **[タグ付け]** で、**[タグの管理者]** の横で、次のいずれかのオプションを選択します。

    - **[チームの所有者とメンバー]**: チームの所有者とメンバーにタグの管理を許可します。
    - **[チームの所有者]**: チームの所有者にタグの管理を許可します。
    - **[無効]**: タグをオフにします。

### <a name="configure-custom-tags-settings"></a>カスタム タグの設定を構成する

次のタグ設定を構成して、組織全体でのカスタム タグの使用方法を制御できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[ **Teams** \> の **設定**] をクリックします。

2. **[タグ付け]** で、組織のニーズに応じて次の設定を行います。

    - **[チーム所有者に、タグの管理が可能なユーザーを上書きしてもらいます]**: この設定をオンにすると、チーム の所有者はチーム メンバーがチーム内でタグを作成および管理できるかどうかを設定できます。また、**[タグの管理者]** 設定の値を各チームの既定値に設定することができます。 この設定をオフにした場合、 **タグは** チームごとに変更できない設定によって管理されます。
    - **[おすすめの既定のタグ]**: 既定のタグのセットを追加するには、これを使用します。 最大 25 個のタグを追加でき、各タグには最大 25 文字を含めることができます。 チームの所有者とメンバー (機能が有効になっている場合) は、これらの推奨タグを使用したり、追加、または新しいタグのセットを作成したりできます。
    - **[カスタム タグの作成を許可する]**: この設定をオンにすると、ユーザーが設定したおすすめの既定のタグ以外のタグを追加できるようになります。 これがオフになっている場合、ユーザーはおすすめの既定のタグのみを使用できます。 これをオフにする場合は、必ず 1 つ以上の既定のタグを追加してください。

## <a name="related-topics"></a>関連トピック

[Teams でのタグの使用](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Teams で組織のシフト アプリを管理する](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[シフトのヘルプ ドキュメント](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
