---
title: Microsoft Teams のゲスト アクセスのチェックリスト
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 03/25/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: このチェックリストを使用すると、Microsoft Teams の設定が容易になります。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0273a9b6c308d8d53fdb640bac6787568398c5be
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865099"
---
<a name="teams-guest-access-checklist"></a>Teams のゲスト アクセスのチェックリスト
==========================================

このチェックリストを使用すると、自分の組織の基本設定に応じて Microsoft Teams のゲスト アクセス機能を有効にしたり、設定したりすることができるようになります。

## <a name="understand-the-limitations-for-guests"></a>ゲストに対する制限事項を理解する

ゲスト エクスペリエンスでは、デザインによる制限があります。問題ではないものを修正しようとしないために、必ずゲスト エクスペリエンスを理解してください。たとえば、Microsoft Teams のゲストが利用できない一部の機能を以下にリストします。

- OneDrive for Business
- Teams 外部のユーザーの検索
- カレンダー、予約済みの会議、会議の詳細
- PSTN
- 組織図
- チームの作成または修正
- チームの参照
- 個人対個人のチャットへのファイルのアップロード

詳細については、「[ゲストのエクスペリエンスについて](guest-experience.md)」および「[Office 365 グループのゲスト アクセス](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)」をご覧ください。

### <a name="guest-access-vs-external-access-federation"></a>ゲスト アクセスと外部アクセス (フェデレーション)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>ゲストに対してライセンスのエラーが表示されている場合

Microsoft Teams のゲスト アクセスではAzure Active Directory ビジネス ツー ビジネス (B2B) およびそのライセンス モデルを使用しています。 ライセンスのエラーが表示される場合は、B2B ライセンスのガイダンスを必ず読んで自分の組織でのライセンスの要件を理解して、自分たちのユーザーが自分の組織でゲストを招待することができる状態になるようにしてください。

次の点にご注意ください。

- ユーザーに割り当てた有料の Azure AD ライセンスの場合、1 つのライセンスで 5 人までのゲスト ユーザーを外部ユーザー無料利用分として招待することができます。
- ゲストとは、自分の組織の外部のユーザーのことです。 社内の従業員、オンサイトの請負業者、オンサイトの代理業者などは、ゲストとして追加することはできません。 これは、関連会社にも提供されます。
- ゲスト ライセンスは、招待する組織に対してカウントされます。 必要なライセンスの数を算出するときは、このことを考慮に入れます。
- 招待されたゲストが別の Office 365 テナントからのユーザーであろうと、個人のメール アドレスを使用していようと、ライセンスがカウントされる対象は自分の組織になります。

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□  手順 1: Azure AD ビジネス ツー ビジネスの設定を構成する

1. サインインします。https://portal.azure.com
2. 左ペインで **Azure Active Directory** をクリックします。
3. [**管理**] の下で、[**ユーザー設定**] をクリックします。
4. [**外部ユーザー**] の下で、[**外部コラボレーションの設定を管理します**] をクリックします。
5. [**外部コラボレーションの設定**] ページで [**メンバーが招待可能**] が [**はい**] に設定されていることを確認します。

      ![スクリーンショットに AAD 設定の切り替えの例が示されます。 ](media/guest-access-checklist-AADSettings1.png)

    ゲストをサポートするために、[**メンバーが招待可能**] を [**はい**] に設定する必要があります。 
   
> [!NOTE] 
> [**メンバーが招待可能**] を [**いいえ**] に設定して、Office 365 グループおよび Microsoft Teams でのゲスト アクセスを有効にすると、自分のディレクトリへのゲストの招待を管理者が制御することができます。 ゲストはディレクトリに入った後、管理者ではない、チーム所有者としてのメンバーによってチームに追加されることができます。

詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。


## <a name="-step-2-configure-office-365-groups"></a>□ 手順 2: Office 365 グループを構成する

1. Microsoft 365 管理センターで、[**設定**] > [**サービスとアドイン**] > [**Office 365 グループ**] に移動します。
2. [**組織外部のグループ メンバーがグループ コンテンツにアクセスすることを許可**] が [**オン**] に設定されていることを確認します。 この設定がオフになっていると、ゲストはどのグループ コンテンツにもアクセスすることはできません。
3. [**グループ所有者が組織外部のユーザーをグループに追加することを許可**] が [**オン**] に設定されていることを確認します。 この設定がオフになっていると、チームの所有者は新しいゲストを追加することができません。 少なくとも、ゲスト アクセスをサポートするためにこの設定をオンにする必要があります。

     ![Office 365 グループの切り替えスイッチを示すスクリーンショット](media/guest-access-checklist-office365.png)

これらの設定の構成方法の詳細については、「[Office 365 グループのゲスト アクセスを管理する](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)」と、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」の「Office 365 グループ」セクションをご覧ください。
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□ 手順 3: テナント レベルでのゲスト アクセスを有効にする

少なくとも、**Microsoft Teams 管理センター**で Microsoft Teams のゲスト アクセスをオンにする必要があります。 

1. Teams 管理センターで、**[組織全体の設定]** > **[ゲスト アクセス]** を選択します。
2. **[Microsoft Teams でのゲスト アクセスを許可]** のスイッチを **[オン]** に設定します。

    ![Teams 設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-set-up-guests-image1.png)

3. この同じページで、必要な他のゲストの設定を構成します。
4. **[保存]** をクリックします。

詳細については、「[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)」をご覧ください。


## <a name="--step-4-configure-sharing-in-office-365"></a>□  手順 4: Office 365 での共有を構成する 

ユーザーがゲストを追加できることを確認します。 次の操作を実行してください。

1. Microsoft 365 管理センターで、[**設定**] > [**セキュリティとプライバシー**] に移動します。

     ![サービスの設定の例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. **[共有]** で **[編集]** を選択します。

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. **[ユーザーがこの組織に新しいゲストを追加できるようにする]** を **[オン]** に設定し、**[保存]** をクリックします。

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> この設定は、Azure AD の [**ユーザー設定**] > [**外部ユーザー**] の [**メンバーが招待可能**] 設定と同等です。  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a>□ 手順 5: SharePoint での共有設定を確認する

1. Microsoft 365 管理センターにサインインします。
2. [**管理センター**] をクリックして [**SharePoint**] を選びます。
3. SharePoint 管理センターで、[**共有**] を選択します。
4. [**組織外との共有を許可しない**] の選択が*解除*されていることを確認します。
 
     ![スクリーンショットに Sparepoint Online の設定の切り替えの例が示されます。](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a>□ 手順 6: チャネルの特定の設定を有効にする 

Teams アプリケーションで、個人のチーム レベルにおいて、ゲストがチャネルを作成、更新、削除することができるようにゲストのアクセス許可を設定します。 管理者に加えて、チーム所有者もこの設定を構成することができます。

![チーム/チャネルの設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-TeamsSettings2.png)

詳細については、使い方ビデオを含む「[Microsoft Teams でのゲスト アクセス](guest-access.md)」をご覧ください。


## <a name="troubleshooting"></a>トラブルシューティング

Microsoft Teams でのゲストの追加に問題がある場合は、「[ゲスト アクセスのトラブルシューティング ガイド](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)」を参照してください。


