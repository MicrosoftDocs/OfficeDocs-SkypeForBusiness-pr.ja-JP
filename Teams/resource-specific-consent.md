---
title: Microsoft Teamsでのリソース固有の同意
author: guptaashish
ms.author: guptaashish
ms.reviewer: nkramer
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織内のチームの所有者がアプリに同意できるかどうかを制御するために構成する必要がある設定について説明します。
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b5ef3f94c511dfe86ab7b153bfa8dd3ea1a04fa
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190498"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Microsoft Teamsでのリソース固有の同意

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft Teamsでのリソース固有の同意により、チームの所有者は、チーム データにアクセスするアプリに同意できます。 このようなアクセスの例には、チャネル メッセージの読み取り、チャネルの作成と削除、チャネル タブの作成と削除が含まれます。

管理者は、組織内のチーム所有者が、Azure Active Directory (Azure AD) PowerShell モジュールまたはAzure portalとMicrosoft Teams管理センターを使用して構成した設定を通じて同意を与えることができるかどうかを制御します。  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>チームの所有者がアプリに同意できるかどうかを設定する

チームの所有者がアプリに同意できるかどうかを制御するために設定する必要がある設定を次に示します。 次のすべての設定を確認してください。

### <a name="settings-in-azure-ad"></a>Azure AD での設定

次の 2 つの設定は、チーム所有者がアプリに同意できるかどうかを決定します。

> [!IMPORTANT]
> これらの設定を変更しても、既に同意が付与されているアプリのデータ アクセスには影響しません。 たとえば、チームの所有者が同意を与えないようにこれらの設定を構成した場合、これらの変更によって、既に付与されているデータ アクセスは削除されません。

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>[ユーザーは自分の代わりに会社のデータにアクセスするアプリに同意できます] 設定

この設定は、組織内のユーザーが自分の代わりにアプリに同意できるかどうかを制御します。 チームの所有者が同意を与えるようにするには、この設定を **[はい**] に設定する必要があります。 この設定を管理するには、次の操作を行います。

1. Azure portalで、**Enterprise アプリケーション** > **のユーザー設定** に移動します。
2. **[Enterprise アプリケーション**] で、[**ユーザーは自分の代わりに会社のデータにアクセスするアプリに同意できます**] を **[いいえ]** または **[はい**] に設定します。

PowerShell を使用してこの設定を管理することもできます。 詳細については、「 [アプリケーションへのユーザー コンテンツの構成」を](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)参照してください。

#### <a name="the-enablegroupspecificconsent-setting"></a>"EnableGroupSpecificConsent" 設定

この設定は、組織内のユーザーが所有するグループの会社のデータにアクセスするアプリに同意できるかどうかを制御します。 チーム所有者が同意を与えるには、この設定を有効にする必要があります。 PowerShell を使用してこの設定を管理する方法については、「 [グループ データにアクセスするアプリに対するグループ所有者の同意を構成する](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)」を参照してください。

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターの設定

Azure AD の設定に加えて、[アプリの管理] ページの [組織全体のアプリ設定](manage-apps.md#manage-org-wide-app-settings) 、 [アプリ](manage-apps.md) が [アプリの [管理](manage-apps.md#allow-and-block-apps) ] ページでブロックまたは許可されているかどうか、およびチーム所有者に割り当てられている [アプリのアクセス許可ポリシー](teams-app-permission-policies.md) によって、チーム所有者が同意を与えることができるかどうかが決まります。

> [!IMPORTANT]
> これらの設定を変更しても、既に同意が付与されているアプリのデータ アクセスには影響しません。 たとえば、組織全体でサード パーティ製アプリを無効にした場合や、チームの所有者が同意を与えないように特定のアプリをブロックした場合、これらの変更によって、既に付与されているデータ アクセスは削除されません。  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>組織全体のアプリ設定の [サードパーティアプリを許可する] 設定

この組織全体のアプリ設定は、組織内のユーザーがサードパーティのアプリを使用できるかどうかを制御します。 チームの所有者が同意を与えるには、この設定をオンにする必要があります。 この設定を管理するには、次の操作を行います。

1. Microsoft Teams管理センターの左側のナビゲーションで、**Teams アプリ** の **[アプリ** > の管理] に移動し、[**組織全体のアプリ設定**] をクリックします。
2. [ **サード パーティアプリ**] で、サード **パーティ** アプリを許可するをオフまたはオンにします。

    ![[Teamsでサード パーティ製アプリを許可する] 設定のスクリーンショット](media/resource-specific-consent-org-wide-setting.png)

変更が有効になるまで最大で 24 時間かかる場合があります。

#### <a name="allow-or-block-the-app-at-the-org-level"></a>組織レベルでアプリを許可またはブロックする

[ [アプリの管理](manage-apps.md#allow-and-block-apps) ] ページでアプリをブロックまたは許可すると、そのアプリは組織内のすべてのユーザーに対してブロックまたは許可されます。 チームの所有者は、アプリが許可されている場合にのみ、アプリに同意を与えることができます。 組織レベルでアプリを許可またはブロックするには、次の操作を行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. [アプリの管理] ページでアプリを選択し、[ **ブロック** ] をクリックしてブロックするか、[ **許可** ] をクリックして許可します。

    ![組織全体の設定でブロックされているアプリのスクリーンショット。](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>チーム所有者に割り当てられたアプリのアクセス許可ポリシー

チームの所有者は、アプリのアクセス許可ポリシーで実行が許可されているアプリにのみ同意できます。 チーム所有者に割り当てられているアプリのアクセス許可ポリシーを表示および管理するには、次の手順に従います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。
2. チーム所有者の表示名をダブルクリックし、[ **ポリシー**] をクリックします。
3. チームの所有者に割り当てられているポリシーは、[ **アプリのアクセス許可ポリシー**] の下に一覧表示されます。
    - 別のポリシーを割り当てるには、[ **編集]** をクリックし、割り当てるポリシーを選択します。
    - チーム所有者に割り当てられているポリシーの設定を編集するには、ポリシー名をクリックして、必要な変更を行います。  

## <a name="uploading-custom-apps"></a>カスタム アプリのアップロード

リソース固有の同意を使用するカスタム アプリ (既知のサイドローディング) をアップロードする場合、アプリはインストール先のテナントから取得する必要があります。 つまり、Azure AD アプリの登録はこのテナントから行う必要があります。 グローバル管理者はこの制限から除外され、チーム (サイドローディング) またはテナント アプリ カタログに直接、任意のテナントからカスタム アプリをアップロードできます。

## <a name="related-topics"></a>関連項目

- [使用可能な RSC アクセス許可](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。](manage-apps.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
