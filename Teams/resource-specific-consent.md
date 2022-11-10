---
title: Microsoft Teams でのリソース固有の同意
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.date: 09/26/2022
search.appverid: MET150
description: 組織内のチームの所有者がアプリに同意できるかどうかを制御するために構成する必要がある設定について説明します。
ms.localizationpriority: high
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb7e4a4487a5411386978fb91a70c485bfa0ddc6
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912596"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Microsoft Teams でのリソース固有の同意

[!INCLUDE [preview-feature](includes/preview-feature.md)]

リソース固有の同意 (RSC) は、アプリが API エンドポイントを使用して組織内のチームの特定のリソースを管理できるようにする Microsoft Teams と Microsoft のGraph API統合です。 RSC アクセス許可を使用すると、チームの所有者は、アプリケーションがチームのデータにアクセスして変更するための同意を付与できます。 Microsoft Teams のリソース固有の同意により、チーム所有者はアプリがチーム データにアクセスすることに同意できます。 このようなアクセスの例には、チャネル メッセージの読み取り、チャネルの作成と削除、およびチャネル タブの作成と削除の機能が含まれます。

管理者は、Azure Active Directory (Azure AD) PowerShell モジュールまたは Azure portal と Microsoft Teams 管理センターを使用して構成した設定を通じて、組織内のチーム所有者が同意できるかどうかを制御します。  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>チームの所有者がアプリに同意できるかどうかを設定する

チームの所有者がアプリに同意できるかどうかを制御するために設定する必要がある設定を次に示します。 次のすべての設定を確認してください。

### <a name="settings-in-azure-active-directory-portal"></a>Azure Active Directory ポータルの設定

次の 2 つの設定は、チームの所有者がアプリに同意できるかどうかを決定します。

> [!IMPORTANT]
> これらの設定を変更しても、既に同意が付与されているアプリのデータ アクセスには影響しません。 たとえば、チームの所有者が同意を与えないようにこれらの設定を構成した場合、これらの変更によって、既に付与されているデータ アクセスは削除されません。

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>ユーザーは、自分の代わりに会社のデータにアクセスするアプリの設定に同意できます

この設定は、組織内のユーザーが自分の代わりにアプリに同意できるかどうかを制御します。 チームの所有者が同意を与えるようにするには、この設定を **[はい]** に設定する必要があります。 これを行うには、次の操作を行います。

1. Azure ポータルで、**[エンタープライズ アプリケーション]** > **[ユーザー設定]** の順に移動します。
2. **[エンタープライズ アプリケーション]** で、**[ユーザーは自分の代わりに会社のデータにアクセスするアプリに同意できます]** を **[いいえ]** または **[はい]** に設定します。

PowerShell を使用してこの設定を管理することもできます。 詳細については、「[アプリケーションへのユーザー コンテンツの構成](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)」を参照してください。

#### <a name="the-enablegroupspecificconsent-setting"></a>"EnableGroupSpecificConsent" 設定

この設定は、組織内のユーザーが、所有するグループの会社データにアプリがアクセスすることに同意できるかどうかを制御します。 チームの所有者が同意するには、この設定を有効にする必要があります。 PowerShell を使用してこの設定を管理する方法については、「[グループ データにアクセスするアプリに対するグループ所有者の同意を構成する](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)」を参照してください。

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでの設定

Azure AD の設定に加えて、[[アプリの管理]](manage-apps.md) ページの[組織全体のアプリ設定](manage-apps.md#manage-org-wide-app-settings)、[[アプリの管理]](manage-apps.md#allow-and-block-apps) ページでアプリがブロックされているか許可されているか、チーム所有者に割り当てられた[アプリのアクセス許可ポリシー](teams-app-permission-policies.md)によって、チーム所有者が同意できるかどうかが決まります。 .

> [!IMPORTANT]
> これらの設定を変更しても、既に同意が付与されているアプリのデータ アクセスには影響しません。 たとえば、組織全体でサードパーティ アプリを無効にしたり、特定のアプリをブロックしてチーム オーナーが同意できないようにしたりした場合、これらの変更によって、既に許可されているデータ アクセスが削除されることはありません。  

#### <a name="the-allow-third-party-apps-option-in-org-wide-app-settings"></a>組織全体のアプリ設定で [サード パーティ製アプリを許可する] オプション

この組織全体のアプリ設定は、組織内のユーザーがサードパーティのアプリを使用できるかどうかを制御します。 チームの所有者が同意を与えるには、この設定をオンにする必要があります。 これを行うには、次の操作を行います。

1. Teams 管理センターにサインインし、**Teams アプリ** にアクセス **[してアプリ](https://admin.teams.microsoft.com/policies/manage-apps)** > を管理します。
1. [ **組織全体のアプリ設定** ] を選択し、[ **サード パーティ製アプリ] で [サード パーティ製アプリ** を **許可する]** をオフまたはオフにします。

   :::image type="content" source="media/resource-specific-consent-org-wide-setting.png" alt-text="Teams でサード パーティ製アプリを許可する設定を示すスクリーンショット。":::

変更が有効になるまでに最大 24 時間かかる場合があります。

#### <a name="allow-or-block-the-app-at-the-org-level"></a>組織レベルでアプリを許可またはブロックする

[[アプリの管理]](manage-apps.md#allow-and-block-apps) ページでアプリをブロックまたは許可すると、そのアプリは組織内のすべてのユーザーに対してブロックまたは許可されます。 チームの所有者は、アプリが許可されている場合にのみ、アプリに同意することができます。 組織レベルでアプリを許可またはブロックするには、次の操作を行います。

1. Teams 管理センターにサインインし、**Teams アプリ** にアクセス **[してアプリ](https://admin.teams.microsoft.com/policies/manage-apps)** > を管理します。
1. [アプリの管理] ページでアプリを選択し、[ **ブロック** ] を選択してブロックするか、[ **許可** ] を選択して許可します。

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>チーム所有者に割り当てられたアプリのアクセス許可ポリシー

チームの所有者は、アプリのアクセス許可ポリシーで実行が許可されているアプリにのみ同意できます。 チーム所有者に割り当てられているアプリのアクセス許可ポリシーを表示および管理するには、次の手順に従います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。
1. チーム所有者の表示名をダブルクリックし、[ポリシー] を選択 **します**。
1. チームの所有者に割り当てられているポリシーは、**[アプリのアクセス許可ポリシー]** の下に一覧表示されます。

    * 別のポリシーを割り当てるには、[ **編集]** を選択し、割り当てるポリシーを選択します。
    * チーム所有者に割り当てられているポリシーの設定を編集するには、ポリシー名を選択し、必要な変更を行います。  

## <a name="upload-custom-apps"></a>カスタム アプリをアップロードする

リソース固有の同意を使用するカスタム アプリ (サイドローディングとも呼ばれます) をアップロードする場合、アプリはインストール先のテナントから取得する必要があります。 つまり、Azure AD アプリの登録はこのテナントから行う必要があります。 グローバル管理者はこの制限から除外され、チーム (サイドローディング) またはテナント アプリ カタログに直接、任意のテナントからカスタム アプリをアップロードできます。

## <a name="related-articles"></a>関連記事

* [Microsoft Graph で Teams のデータを利用するための RSC アクセス許可](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* [Microsoft Graph](https://developer.microsoft.com/graph)
* [Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。](manage-apps.md)
* [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
