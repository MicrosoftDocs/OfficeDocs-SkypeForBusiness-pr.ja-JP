---
title: Microsoft Teams でのリソース固有の同意
author: LanaChin
ms.author: v-lanac
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織のチーム所有者がアプリに同意するかどうかを制御するために構成する必要がある設定について説明します。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54a0565f5126c899ed5fbf9527aa30f83c3bee3b
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256601"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Microsoft Teams でのリソース固有の同意

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft Teams でリソース固有の同意を得ることで、チームの所有者は、チームデータへのアクセスをアプリに承認することができます。 このようなアクセスの例としては、チャネルメッセージの読み取り、チャネルの作成と削除、チャネルタブの作成と削除などがあります。

管理者として、Azure Active Directory (Azure AD) PowerShell モジュールまたは Azure portal と Microsoft Teams 管理センターを使用して構成した設定によって、組織のチーム所有者が同意を得ることができるかどうかを制御できます。  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>チーム所有者がアプリに同意することを許可するかどうかを設定する

チーム所有者がアプリに同意するかどうかを制御するために設定する必要がある設定を次に示します。 次の設定を確認してください。

### <a name="settings-in-azure-ad"></a>Azure AD の設定

次の2つの設定では、チーム所有者がアプリに同意できるかどうかを決定します。

> [!IMPORTANT]
> これらの設定を変更しても、既に同意が付与されているアプリのデータアクセスには影響しません。 たとえば、これらの設定を構成して、チームの所有者が同意しないようにした場合、これらの変更では、既に許可されているデータアクセスが削除されることはありません。

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>"ユーザーの代わりに会社データにアクセスするアプリに同意することができます" 設定

この設定は、組織内のユーザーがアプリに代わって承認できるかどうかを制御します。 チーム所有者が同意を得ることができるようにするには、 **[はい]** に設定する必要があります。 この設定を管理するには、次の操作を行います。

1. Azure ポータルで、[**エンタープライズアプリケーション**の  >  **ユーザー設定**] に移動します。
2. [**エンタープライズアプリケーション**] では、ユーザーが [**いいえ**] または **[はい]** に**代わって会社のデータにアクセスするアプリに同意できる**ように設定します。

PowerShell を使用してこの設定を管理することもできます。 詳細については、「[ユーザーコンテンツをアプリケーションに構成](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)する」を参照してください。

#### <a name="the-enablegroupspecificconsent-setting"></a>"Enablegroup固有の同意" の設定

この設定は、組織内のユーザーが所有しているグループの会社データにアクセスするアプリに同意するかどうかを制御します。 チーム所有者が同意を得るためには、この設定を有効にしておく必要があります。 PowerShell を使用してこの設定を管理する手順については、「[グループデータにアクセスするアプリにグループの所有者の同意を構成](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)する」を参照してください。

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの設定

Azure AD の設定に加えて、[アプリ[の管理]](manage-apps.md#allow-and-block-apps)ページで、アプリがブロックされているか許可されているかにかかわらず、[アプリ[の管理] ページで](manage-apps.md)の[組織全体のアプリの設定](manage-apps.md#manage-org-wide-app-settings)、チーム所有者に割り当てられたアプリの[アクセス許可ポリシー](teams-app-permission-policies.md)が、チーム所有者が同意を得るかどうかを決定します。

> [!IMPORTANT]
> これらの設定を変更しても、既に同意が付与されているアプリのデータアクセスには影響しません。 たとえば、サードパーティ製のアプリを無効にした場合や、特定のアプリをブロックしてチームの所有者が同意を得られないようにした場合、これらの変更では、既に許可されているデータアクセスは削除されません。  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>組織全体のアプリ設定で [サードパーティ製アプリを許可する] 設定

この組織全体のアプリの設定では、組織内のユーザーがサードパーティ製のアプリを使用できるかどうかを制御します。 チーム所有者が同意を得るためには、この設定が有効になっている必要があります。 この設定を管理するには、次の操作を行います。

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動し、  >  **Manage apps**[**組織全体のアプリの設定**] をクリックします。
2. [**サードパーティ製のアプリ**] の下で、[**サードパーティ製のアプリを許可する**] をオンまたはオフにします。

    ![[Teams でサードパーティ製のアプリを許可する] 設定のスクリーンショット](media/resource-specific-consent-org-wide-setting.png)

変更が有効になるまで最大で 24 時間かかる場合があります。

#### <a name="allow-or-block-the-app-at-the-org-level"></a>組織レベルでアプリを許可またはブロックする

[[アプリの管理](manage-apps.md#allow-and-block-apps)] ページでアプリをブロックまたは許可すると、そのアプリは組織内のすべてのユーザーに対してブロックまたは許可されます。 チーム所有者は、アプリが許可されている場合にのみ、アプリへの同意を得ることができます。 組織レベルでアプリを許可またはブロックするには、次の操作を行います。

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。
2. [アプリの管理] ページでアプリを選択し、[**ブロック**] をクリックしてアプリをブロックするか、[**許可**] をクリックして許可します。

    ![組織全体の設定でブロックされているアプリのスクリーンショット](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>チーム所有者に割り当てられているアプリのアクセス許可ポリシー

チーム所有者は、アプリのアクセス許可ポリシーによって実行が許可されているアプリに対してのみ同意を得ることができます。 チーム所有者に割り当てられているアプリのアクセス許可ポリシーを表示および管理するには、次の操作を行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。
2. チーム所有者の表示名をダブルクリックし、[**ポリシー**] をクリックします。
3. チーム所有者に割り当てられているポリシーが [**アプリのアクセス許可ポリシー**] の下に表示されます。
    - 別のポリシーを割り当てるには、[**編集**] をクリックし、割り当てるポリシーを選択します。
    - チーム所有者に割り当てられているポリシーの設定を編集するには、ポリシー名をクリックして、必要な変更を加えます。  

## <a name="uploading-custom-apps"></a>カスタムアプリのアップロード

リソース固有の同意を使っているカスタムアプリ (とも呼ばれる) をアップロードする場合は、アプリがインストールされているテナントから取得される必要があります。 つまり、Azure AD アプリの登録はこのテナントからのものである必要があります。 グローバル管理者はこの制限から除外され、任意のテナントからチーム (サイドローディング) またはテナントアプリカタログに直接、カスタムアプリをアップロードできます。

## <a name="related-topics"></a>関連項目

- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
