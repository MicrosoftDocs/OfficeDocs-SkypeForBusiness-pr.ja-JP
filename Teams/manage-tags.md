---
title: Microsoft Teams でタグを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
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
description: Microsoft Teams での組織でのタグの使用方法を管理する方法について説明します。
ms.openlocfilehash: 3ade2f47474fe8aaf16c568e8c141dcd84526d86
ms.sourcegitcommit: 561b9bab7d6f5a621436bc85ea28ea14657e7868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034514"
---
# <a name="manage-tags-in-microsoft-teams"></a>Microsoft Teams でタグを管理する

> [!NOTE]
> Microsoft Teams 管理センターにこの機能が表示されていない場合 現在ロールアウト中であり、組織内でまだ利用できない可能性があります。 今後の Teams の機能については、 [Microsoft 365 のロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)をご覧ください。

Microsoft Teams のタグを使用すると、ユーザーはチームのメンバーのサブセットと連絡を取ることができます。 タグを1人または複数のチームメンバーに追加して、ユーザーの適切なサブセットに簡単に接続できます。 チーム所有者とメンバー (その機能が有効になっている場合) は、1つまたは複数のタグをユーザーに追加できます。 その後、タグは、そのタグが割り当てられているユーザーのみと通信するために、チャネル投稿内のチーム内のすべてのユーザーが @mentions で使用できます。

> [!NOTE]
> プライベートチャネルでは、タグはまだサポートされていません。

## <a name="how-tags-work"></a>タグのしくみ

タグは、特定のチームのメンバーに追加できます。 タグが追加されると、チームの任意の標準チャネルの @mentions でそのタグを使用できるようになります。 次に、Teams でタグを使用する方法の例をいくつか示します。

- ストアマネージャーが、チャネルにお知らせを投稿して、すべてのレジに通知する必要があります。
- グループの製品マネージャーは、チャネル内のすべての製品マネージャーにメッセージを送信したいと考えています。
- 病院の管理者が、チャネル内のすべての radiologists にメッセージを送信したい。

詳細については、「 [Teams でタグを使用する」](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)をご覧ください。

## <a name="manage-tags-for-your-organization"></a>組織のタグを管理する

管理者は、Microsoft Teams 管理センターにおいて、タグを追加できるユーザーと、タグを組織全体でどのように使用するかを制御することができます。

![Microsoft Teams 管理センターのタグ設定のスクリーンショット](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a>タグを追加できるユーザーを設定する

既定では、チームの所有者はタグを追加できます。 この設定を変更して、チーム所有者とチームメンバーがタグを追加できるようにするか、組織のタグをオフにすることができます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**組織全体の設定** > ]**チームの設定**をクリックします。
2. [**タグ付け**] で、[**タグ付けの対象] の**横にある次のいずれかのオプションを選択します。

    - **チームの所有者とメンバー**: チームの所有者とメンバーがタグを追加できるようにします。
    - **チームの所有者**: チーム所有者がタグを追加できるようにします。
    - **Disabled**: ノートシールをオフにします。

### <a name="configure-tags-settings"></a>タグ設定を構成する

次のタグ設定を構成して、組織全体でのタグの使用方法を制御できます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**組織全体の設定** > ]**チームの設定**をクリックします。
2. [**タグ付け**] で、組織のニーズに応じて次のように設定します。

    - **チーム所有者は、タグを適用できるユーザーを上書きでき**ます。この機能がオンになっていると、チームの所有者は、チーム設定でメンバーにタグを追加することを許可または禁止することができます。
    - **メンバーはタグ**を追加できます。チームメンバーがタグを追加できるようにするには、このオプションをオンにして、設定した既定のタグ以外のタグをチームメンバーが追加できるようにします。 この機能が無効になっている場合、チームメンバーは既定のタグのみを使用できます。
    - **提案**された既定のタグ: これを使用して、一連の既定のタグを追加します。 最大25個のタグを追加できます。各タグには最大25文字まで含めることができます。 チーム所有者とメンバー (機能が有効になっている場合) は、これらの候補を使用したり、それらを追加したり、新しいタグセットを作成したりすることができます。

## <a name="manage-tags-settings-for-a-team"></a>チームのタグ設定を管理する

チーム所有者が Microsoft Teams 管理センターの [**タグを適用できるユーザーを上書きできる**] 設定をオンにしている場合、チーム所有者は、メンバーがチームレベルでタグを追加できるかどうかを設定できます。 これを行うには、チームの [**設定**] タブで [**タグ**] に移動し、[タグを追加できるユーザー] を選択します。

![チームレベルの [タグ] 設定のスクリーンショット](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a>Teams でタグを追加する

Teams では、チームの [チームの管理] ページの [**メンバー** ] タブに [**タグ**] 列が含まれています。 チームの所有者とメンバー (機能が有効になっている場合) は、メンバーの横にある [**タグの管理**] をクリックすると、そのメンバーの候補タグの一覧が表示され、タグをリストに追加することができます。

![Teams クライアントでタグを適用する方法を示すスクリーンショット ](media/manage-tags-teams.png) 
