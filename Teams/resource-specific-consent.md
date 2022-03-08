---
title: リソース固有の同意 (Microsoft Teams
author: guptaashish
ms.author: guptaashish
ms.reviewer: nkramer
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織内のチーム所有者がアプリに同意できるかどうかを制御するために構成する必要がある設定について学習します。
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9e6e2f0e7827dab36645fec7105a9cbe0c439472
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070656"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>リソース固有の同意 (Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

リソース固有の同意を使用するとMicrosoft Teams所有者は、チーム データにアクセスするアプリに同意できます。 このようなアクセスの例としては、チャネル メッセージの読み取り、チャネルの作成と削除、チャネル タブの作成と削除が含まれます。

管理者は、Azure Active Directory (Azure AD) PowerShell モジュールまたは Azure portal と Microsoft Teams 管理センターを使用して構成した設定を使用して、組織内のチーム所有者が同意できるかどうかを制御します。  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>チーム所有者がアプリに同意できるかどうかを設定する

チーム所有者がアプリに同意できるかどうかを制御するために設定する必要がある設定を次に示します。 次のすべての設定を確認してください。

### <a name="settings-in-azure-ad"></a>設定のAzure AD

次の 2 つの設定は、チーム所有者がアプリに同意できるかどうかを決定します。

> [!IMPORTANT]
> これらの設定を変更しても、既に同意が付与されているアプリのデータ アクセスには影響しません。 たとえば、チームの所有者が同意を与えなかねない設定を構成した場合、これらの変更によって、既に付与されているデータ アクセスは削除されません。

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>[ユーザーは、ユーザーに代わって会社のデータにアクセスするアプリに同意できます] 設定

この設定は、組織内のユーザーがアプリに代わって同意できるかどうかを制御します。 チーム所有者が同意するには、この設定を [はい] に設定する必要 **があります**。 この設定を管理するには、次の操作を行います。

1. Azure portal で、[アプリケーションの設定] **Enterpriseに** > **移動します**。
2. [**Enterprise] で、[** ユーザーは自分の代わりに会社のデータにアクセスするアプリに同意できます] を [いいえ] または [はい **]** に設定 **します**。

この設定は、PowerShell を使用して管理できます。 詳細については、「アプリケーションへのユーザー [コンテンツの構成」を参照してください](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)。

#### <a name="the-enablegroupspecificconsent-setting"></a>"EnableGroupSpecificConsent" 設定

この設定は、組織内のユーザーが、所有するグループの会社データにアクセスするアプリに同意できるかどうかを制御します。 チーム所有者が同意するには、この設定を有効にする必要があります。 PowerShell を使用してこの設定を管理する手順については、「グループ データにアクセスするアプリに対するグループ所有者の同意を構成 [する」を参照してください](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)。

### <a name="settings-in-the-microsoft-teams-admin-center"></a>設定管理センター Microsoft Teams表示

Azure AD の設定に加えて、[アプリの管理[](manage-apps.md#manage-org-wide-app-settings)] ページの組織全体のアプリ[](manage-apps.md)設定、[アプリの管理] ページでアプリがブロックまたは許可されるかどうか、チーム所有者に割り当[](teams-app-permission-policies.md)てられているアプリのアクセス許可ポリシーによって、チーム所有者が同意できるかどうかが決されます。[](manage-apps.md#allow-and-block-apps)

> [!IMPORTANT]
> これらの設定を変更しても、既に同意が付与されているアプリのデータ アクセスには影響しません。 たとえば、組織全体でサード パーティ製アプリを無効にした場合や、チーム所有者が同意を得るのを防ぐために特定のアプリをブロックした場合、これらの変更によって、既に付与されているデータ アクセスは削除されません。  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>組織全体のアプリ設定の [サード パーティ製アプリを許可する] 設定

この組織全体のアプリ設定は、組織内のユーザーがサードパーティ製アプリを使用できるかどうかを制御します。 チーム所有者が同意を与えるためには、この設定をオンにする必要があります。 この設定を管理するには、次の操作を行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[Teams **アプリ** > の管理] に移動し、[組織全体のアプリ設定] **をクリックします**。
2. [ **サード パーティ製アプリ] で**、[サード パーティ製アプリを許可する **] をオフまたはオンにします**。

    ![[Allow third party apps in Teams]/[Allow third party apps in Teams])[Allow third party apps in Teams])[Allow third party apps in Teams]](media/resource-specific-consent-org-wide-setting.png)

変更が有効になるまで最大で 24 時間かかる場合があります。

#### <a name="allow-or-block-the-app-at-the-org-level"></a>組織レベルでアプリを許可またはブロックする

[アプリの管理] ページでアプリを[](manage-apps.md#allow-and-block-apps)ブロックまたは許可すると、そのアプリは組織内のすべてのユーザーに対してブロックまたは許可されます。 チーム所有者は、アプリが許可されている場合にのみ、アプリに同意できます。 組織レベルでアプリを許可またはブロックするには、次の操作を行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. [アプリの管理] ページでアプリを選択し、[ブロック] をクリックしてブロックするか、[許可 **]** をクリックしてアプリを許可します。

    ![組織全体の設定でブロックされているアプリのスクリーンショット。](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>チーム所有者に割り当てられたアプリのアクセス許可ポリシー

チーム所有者は、アプリのアクセス許可ポリシーで実行を許可するアプリにのみ同意できます。 チーム所有者に割り当てられているアプリのアクセス許可ポリシーを表示および管理するには、次の操作を行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。
2. チーム所有者の表示名をダブルクリックし、[ポリシー] を **クリックします**。
3. チーム所有者に割り当てられたポリシーが、[アプリのアクセス許可ポリシー **] の下に一覧表示されます**。
    - 別のポリシーを割り当てるには、[ **編集] を** クリックし、割り当てるポリシーを選択します。
    - チーム所有者に割り当てられているポリシーの設定を編集するには、ポリシー名をクリックし、必要な変更を加えます。  

## <a name="uploading-custom-apps"></a>カスタム アプリのアップロード

リソース固有の同意を使用するカスタム アプリ (サイドローディングとも呼ばれる) をアップロードする場合、アプリはインストール先のテナントから取得する必要があります。 言い換えると、Azure AD登録は、このテナントから行う必要があります。 グローバル管理者は、この制限から除外され、任意のテナントから直接チーム (サイドローディング) またはテナント アプリ カタログにカスタム アプリをアップロードできます。

## <a name="related-topics"></a>関連項目

- [使用可能な RSC アクセス許可](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [管理センターでアプリMicrosoft Teamsする](manage-apps.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)