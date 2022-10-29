---
title: Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.date: 09/29/2022
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.reviewer: kojika
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Teams アプリを管理する方法について説明します。 アプリの許可またはブロック、組織レベルの状態とアプリのプロパティの確認、カスタム アプリのアップロード、アプリ設定の管理について説明します。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 902b32be43e25c8262ba85bbbb56bd79d424e75c
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784192"
---
# <a name="overview-of-app-management-and-governance-in-teams-admin-center"></a>Teams 管理センターでのアプリ管理とガバナンスの概要

Teams 管理センター ポータルで、**Teams アプリ** の組織向けアプリを管理します。 [アプリの管理] ページを使用すると、組織のアプリ カタログ内のすべての Teams アプリを表示および管理したり、アプリ管理の明確なユース ケースに対応したり、ポリシーを使用してアプリへのアクセスを定義したりできます。

:::image type="content" source="media/manage-apps.png" alt-text="[アプリの管理] ページのスクリーンショット。" lightbox="media/manage-apps.png":::

アプリを管理するには、ポリシーを使用して、ユーザーのアクセス許可、アプリのインストール、組織内で作成されたカスタム アプリのアップロードを制御します。 ポリシーについては、「[アプリ ポリシーの概要](app-policies.md)」を参照してください。

Teams 管理センターを使用するには、グローバル管理者ロールまたは Teams 管理者ロールが必要です。 詳細については、[Teams 管理者ロール](./using-admin-roles.md)と [Microsoft 365 管理者ロール](/microsoft-365/admin/add-users/about-admin-roles)に関するページを参照してください。

> [!NOTE]
> Teams の Microsoft 365 Government Community Cloud High (GCCH) または国防総省 (DoD) のデプロイでは、[アプリの管理] ページは利用できません。

## <a name="app-management-use-cases-and-the-available-interfaces"></a>アプリ管理のユース ケースと使用可能なインターフェイス

ほとんどのアプリ管理ユース ケースを実現するためのオプションは、Teams 管理センターで使用できます。 さらに、一部のオプションは、他のポータルまたは Teams 管理センターの別のページで使用できます。

管理センターでサポートされているアプリ管理タスクを次の表に示します。

| アプリ管理のユース ケース | インターフェイスへのリンク | ドキュメント |
|:----|:----|:----|
| アプリを許可およびブロックすることで、組織内のユーザーが使用できるアプリを制御します。 カスタム アプリをアップロードして承認することもできます。 このページでアプリを管理した後、アプリのアクセス許可とアプリのセットアップ ポリシーを使用して、組織のアプリ ストア内の特定のユーザーが利用できるアプリを構成できます。 | [Teams 管理センターでアプリを管理する](https://admin.teams.microsoft.com/policies/manage-apps) | 現在の記事 |
| アプリのアクセス許可ポリシーは、組織内の Teams ユーザーが使用できるようにするアプリを制御します。 グローバル (組織全体の既定) ポリシーを使用してカスタマイズするか、組織のニーズを満たすために、1 つ以上のポリシーを作成できます。 | [アクセス許可ポリシー](https://admin.teams.microsoft.com/policies/app-permission) | [アプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md) |
| アプリのセットアップ ポリシーは、Teams アプリを使用してユーザーがアプリを使用できるようにする方法を制御します。 グローバル (組織全体の既定) ポリシーを使用してカスタマイズするか、カスタム ポリシーを作成してユーザーのセットに割り当てます。 | [セットアップ ポリシー](https://admin.teams.microsoft.com/policies/app-setup) | [アプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md) |
| カスタム アプリを開発してアプリ パッケージとしてアップロードし、組織のアプリ ストアで利用できるようにすることができます。 | [[アプリの管理]](https://admin.teams.microsoft.com/policies/manage-apps) の組織全体のアプリ設定 | [カスタム アプリのポリシー設定を管理する](teams-custom-app-policies-and-settings.md) |
| 組織のロゴおよびカスタムの背景や色を使用して、Teams アプリ ストアをカスタマイズできます。 | [ストアをカスタマイズする](https://admin.teams.microsoft.com/policies/customize-appstore) | [組織のアプリ ストアをカスタマイズする](customize-your-app-store.md) |
| Teams アプリの使用状況レポートには、使用中のアプリ、アクティブなユーザー、その他のアプリの使用状況に関する情報が表示されます。 | [利用状況レポート](https://admin.teams.microsoft.com/analytics/reports) | [Teams アプリの使用状況レポート](teams-analytics-and-reports/app-usage-report.md) |
| ユーザーは、ゲストとの会議やチャットをホストするときにアプリを追加できます。 外部からホストする会議やチャットに参加するときに、ゲストが共有するアプリを使用することもできます。 ホストしているユーザーの組織のデータ ポリシーと、そのユーザーの組織が共有するサードパーティ アプリのデータ共有の慣行が適用されます。 | [外部アクセス](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [ユーザーの種類に応じたアプリの動作](non-standard-users.md) |
| ゲスト アクセスを使用すると、企業データの管理を維持しながら、アプリケーションやその他の Teams 機能へのアクセスを組織外の人々に提供できます。 | [ゲスト アクセス](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Teams でのゲスト アクセス](guest-access.md) |
| Teams 更新ポリシーは、Teams アプリでプレリリース機能またはプレビュー機能を表示できる Teams および Office プレビュー ユーザーを管理するために使用されます。 | [Teams 更新ポリシー](https://admin.teams.microsoft.com/policies/updatemanagement) | [Teams パブリック プレビュー](public-preview-doc-updates.md) |

他のポータルでサポートされているアプリ管理タスクを次の表に示します。

| アプリ管理のユース ケース | インターフェイスへのリンク | ドキュメント |
|:----|:----|:----|
| Microsoft 365 管理センターでサード パーティ製アプリのライセンスとサブスクリプションを管理する | [Microsoft 365 管理センター](https://admin.microsoft.com/#/licenses) | [サード パーティ製アプリのサブスクリプションを管理する](/microsoft-365/commerce/manage-saas-apps) |
| Microsoft Purview コンプライアンス ポータルで Teams アプリ イベントを監査します。 | [監査](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Teams アクティビティ](audit-app-management-activities.md) |
| アプリケーションで組織とそのデータに対するアクセス許可を付与するには、管理者がすべてのユーザーのアプリケーションに同意する方法、ユーザーがアプリケーションに同意を付与する方法、または管理者がアプリケーションを統合してセルフサービス アクセスを有効にしたり、ユーザーをアプリケーションに直接割り当てたりする 3 つの方法があります。 アプリの Graph アクセス許可を確認します。 ユーザーが提供したアクセス許可、または管理者が委任したアクセス許可を確認します。 | [Azure AD portal](https://aad.portal.azure.com/) | [アプリケーションに付与されたアクセス許可を確認する](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="allow-and-block-apps"></a>アプリの許可とブロック

管理者は、すべてのユーザーがすべてのコンテキストで使用するすべての種類のアプリへのアクセスを制御します。 Teams では、各アプリと各ユーザーのアクセスを構成するための詳細な制御が提供されます。

アプリを許可するには、次のすべての設定を行う必要があります。 アプリをブロックするには、次のいずれかの設定でブロックします。

* [組織全体のアプリ設定](manage-apps.md#manage-org-wide-app-settings): この設定を使用して、組織内のアプリの使用を許可します。使用する特定のアプリを決定します。
* [個々のアプリを許可する](manage-apps.md#allow-and-block-apps): この設定を使用して、組織内の特定のアプリを許可します。アプリを使用できるユーザーを決定します。
* [アプリのアクセス許可ポリシー](teams-app-permission-policies.md): ポリシーを使用して、すべてのユーザーにアプリの使用を許可するか、特定のユーザーにアプリの使用を許可します。 ユーザーごとおよびアプリごとにアクセスを決定します。

[アプリの管理] ページは、組織レベルで個々のアプリを許可またはブロックする場所です。 ページには、使用可能なすべてのアプリとその現在の組織レベルのアプリの状態が表示されます。 アプリを許可またはブロックするには、次の手順に従います。

1. Teams 管理センターにサインインし、**Teams アプリ** > にアクセス **[アプリを管理する](https://admin.teams.microsoft.com/policies/manage-apps)**
1. アプリを見つけて選択します。
1. **[許可]** または **[ブロック]** オプションを選択します。

特定のユーザーのアプリを許可するには、 [アプリのアクセス許可ポリシーに関するページを](teams-app-permission-policies.md)参照してください。

## <a name="manage-org-wide-app-settings"></a>組織全体のアプリ設定の管理

組織全体のアプリ設定を使用して、[F ライセンス](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)を持つユーザーがカスタマイズされた現場アプリ エクスペリエンスを取得するかどうか、ユーザーがサードパーティ製アプリをインストールできるかどうか、ユーザーが組織内のカスタム アプリをアップロードまたは操作できるかどうかを制御します。

> [!NOTE]
> Microsoft 365 Government - Government Community Cloud High GCCH および国防総省 (DoD) の Teams のデプロイで組織全体のアプリ設定を使用する方法については、「[Teams でアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」を参照してください。

1. [ **[アプリの管理](https://admin.teams.microsoft.com/policies/manage-apps)** ] ページ **で、[組織全体のアプリ設定**] を選択します。 次に、パネルで必要な設定を構成できます。

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="[アプリの管理] ページの [組織全体のアプリ設定] ウィンドウを示すスクリーンショット":::

1. **[カスタマイズされたアプリ]** で、**[カスタマイズされたアプリの表示]** をオンまたはオフにします。 この設定をオンにすると、 [F ライセンスを持つユーザー](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)は、カスタマイズされた現場アプリのエクスペリエンスを利用できます。 このエクスペリエンスにより、現場担当者にとって Teams で最も関連性の高いアプリがピン留めされます。 詳細については、「[現場担当者向けに Teams アプリを調整する](pin-teams-apps-based-on-license.md)」を参照してください。

    この機能は F ライセンスで使用できます。 その他のライセンスの種類は、今後サポートされる予定です。
1. **[サードパーティ アプリ]** で、次の設定をオフまたはオンにして、サードパーティ アプリへのアクセスを制御します。

    * **[サードパーティ アプリを許可する]**: ここで、ユーザーがサードパーティ アプリを使用できるかどうかを制御します。 この設定をオフにした場合、ユーザーはサードパーティ製アプリをインストールまたは使用できず、これらのアプリのアプリ状態は、"**組織全体でブロック**" としてテーブルに表示されます。

        > [!NOTE]
        > **[サードパーティ製アプリのを許可]** がオフの場合、[送信 Webhook](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) は引き続きすべてのユーザーに対して有効になりますが、[[アプリのアクセス許可ポリシー]](teams-app-permission-policies.md) を使用して送信 Webhook アプリを許可またはブロックすることで、ユーザー レベルの制御ができます。 **[特定のアプリを許可し、他のすべてをブロックする]** 設定を使用する **Microsoft アプリ** に対して既存の [アプリアクセス許可ポリシー](teams-app-permission-policies.md)があり、ユーザーに対して送信 Webhook を有効にする場合は、送信 Webhook アプリを一覧に追加します。

        > [!NOTE]
        > Teams ユーザーは、他の組織のユーザーとの会議やチャットをホストするときにアプリを追加できます。 他の組織がホストする会議やチャットに参加するときに、他の組織のユーザーが共有するアプリを使用することもできます。 ホストしているユーザーの組織のデータ ポリシーと、そのユーザーの組織が共有するサードパーティ アプリのデータ共有の慣行が適用されます。

    * **Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams. You can only set this option if you allow third-party apps.

1. **[カスタム アプリ]** で、**[カスタム アプリとの対話を許可する]** をオフまたはオンにします。 この設定は、ユーザーがカスタム アプリを操作できるかどうかを制御します。 詳細については、「 [カスタム アプリのポリシーと設定を管理する」を](teams-custom-app-policies-and-settings.md)参照してください。

1. **[保存]** を選択します。 設定は数時間後に有効になります。

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Microsoft 365 Government の組織全体のアプリ設定を管理する  

Microsoft 365 Government の場合 - Teams の GCCH および DoD 展開では、すべてのサードパーティ アプリが既定でブロックされています。 GCCH および DOD クラウドでは、サード パーティ製アプリは使用できません。 さらに、GCC では、Microsoft Teams の管理センターのアプリ許可ポリシーページで、サードパーティ アプリの管理について以下のような注意事項が表示されます。

:::image type="content" source="media/app-permission-policies-gcc.png" alt-text="GCCH および DoD 内のアプリのアクセス許可ポリシーのスクリーンショット。":::

組織全体のアプリ設定を使用して、ユーザーがサード パーティのアプリをインストールできるかどうかを制御します。 組織全体のアプリ設定は、すべてのユーザーの動作を管理し、ユーザーに割り当てられた他のアプリ権限ポリシーを上書きします。

<!---1. On the **Permission policies** page, select **Org-wide app settings**. You can then configure the settings you want in the panel. 
--->

### <a name="for-gcc-clouds"></a>GCC クラウドの場合

1. **[Teams Apps の****[アプリの管理](https://admin.teams.microsoft.com/policies/manage-apps)**]  >  ページ **で、[組織全体のアプリ設定**] を選択します。 次に、パネルで必要な設定を構成できます。

   :::image type="content" source="media/app-permission-policies-gcc-org-wide.png" alt-text="GCC の組織全体のアプリ設定を示すスクリーンショット。":::

1. **[サードパーティ アプリ]** で、次の設定をオフまたはオンにして、サードパーティ アプリへのアクセスを制御します。

    * **[サードパーティ アプリを許可する]**: このオプションはユーザーがサードパーティ アプリを使用できるかどうかを制御します。 この設定をオフにすると、ユーザーはサードパーティ アプリをインストールしたり使用したりできなくなります。 Microsoft 365 Governmentの場合 - Teams の GCCH および DoD 展開では、この設定は既定でオフになっています。
    * **ストアに公開された新しいサードパーティ アプリを既定で許可する**: このオプションは Teams アプリ ストアに公開された新しいサードパーティ アプリを Teams で自動的に利用可能にするかどうかを制御します。 このオプションは、サードパーティのアプリを許可する場合にのみ設定できます。

1. **[ブロック済みのアプリ]** で、組織全体でブロックするアプリを追加します。 Microsoft 365 Government の場合 - Teams の GCCH および DoD 展開では、すべてのサードパーティ アプリが既定でこのリストに追加されます。 組織で許可するサードパーティのアプリについては、このブロック済みのアプリのリストからアプリを削除します。 組織全体でアプリをブロックすると、アプリのアクセス許可ポリシーで許可されているかどうかに関係なく、アプリはすべてのユーザーに対して自動的にブロックされます。

1. 組織全体のアプリ設定を有効にするには、**[保存]** を選択します。

サード パーティ製アプリを許可するには、グローバル (組織全体の既定) ポリシーを編集して使用するか、管理者が作成したポリシーを作成して割り当てます。

### <a name="for-gcch-and-dod-clouds"></a>GCCH および DoD クラウドの場合

1. Teams 管理センターにサインインし、 **Teams アプリ** > **[のアクセス許可ポリシーにアクセスします](https://admin.teams.microsoft.com/policies/app-permission)**。

1. [ **組織全体のアプリ設定] を選択します**。 **[ブロック済みのアプリ]** で、組織全体でブロックするアプリを追加します。 Microsoft 365 Government の場合 - Teams の GCCH および DoD 展開では、すべてのサードパーティ アプリが既定でこのリストに追加されます。 組織全体でアプリをブロックすると、アプリのアクセス許可ポリシーで許可されているかどうかに関係なく、アプリはすべてのユーザーに対して自動的にブロックされます。

   :::image type="content" source="media/app-permission-policies-gcch-dod-org-wide.png" alt-text="GCCH および DoD で組織全体のアプリ設定のスクリーンショット。スクリーンショット。":::

1. 組織全体のアプリ設定を有効にするには、**[保存]** を選択します。

## <a name="allow-the-apps-that-are-blocked-by-the-developers"></a>開発者がブロックしているアプリを許可する

開発者が Teams アプリ ストアにアプリを発行する場合、アプリ エクスペリエンスを構成またはカスタマイズするために管理者が必要になる場合があります。 管理者は、アプリのセットアップ時にエンド ユーザーがアプリを利用できるようにします。

たとえば、Contoso Electronics は、Microsoft Teams のヘルプ デスク アプリを作成したアプリ開発者です。 Contoso Electronics は、その顧客がアプリを操作するときに期待どおりに機能するように、顧客がアプリの特定のプロパティを設定することを望んでいます。 管理者がアプリケーションを許可する前に、Teams 管理センターで "**発行元 によってブロック済み**" として表示され、既定ではエンド ユーザーから非表示になっています。 発行元のガイダンスに従ってアプリを設定した後、状態を **[許可]** に変更してユーザーが利用できるようにすることができます。

:::image type="content" source="media/blocked-by-publisher.png" alt-text="Teams 管理センターの発行元の状態によってブロックされていることを示すスクリーンショット。":::

開発者が既定でアプリをブロックする方法については、「 [管理者がアプリを許可するまでアプリをブロック](/microsoftteams/platform/concepts/design/enable-app-customization#hide-teams-app-until-admin-approves)できるようにする」を参照してください。

## <a name="related-article"></a>関連記事

* [アプリを許可するユーザー要求を管理します](user-requests-approve-apps.md)。
