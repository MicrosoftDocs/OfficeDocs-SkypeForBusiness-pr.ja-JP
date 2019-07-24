---
title: Microsoft Teams のゲスト アクセスのチェックリスト
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
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
ms.openlocfilehash: 3142a30a5131ed18a76a130c420b3af214c5190b
ms.sourcegitcommit: 67282b5f2f1aac3e675c4a485f4846deba15deb4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "35841377"
---
<a name="teams-guest-access-checklist"></a>Teams のゲスト アクセスのチェックリスト
==========================================

このチェックリストを使用すると、自分の組織の基本設定に応じて Microsoft Teams のゲスト アクセス機能を有効にしたり、設定したりすることができるようになります。

> [!NOTE] 
> 共同作業の制限については[、「B2B 外部コラボレーションを有効にする」と「ゲストを招待できるユーザーを管理する](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)」をご覧ください

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
- ユーザーの完全なメール ID がわかっている場合でも、ゲストはユーザーを検索して検索できます。 このようなことを防ぐため、IT 管理者は、ゲストを仮想 GAL に制限する機能を持つ、スコープ指定された[ディレクトリ検索](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search)などのパターンを使用できます。

詳細については、「 [Office 365 グループで](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)の[ゲストエクスペリエンスの概要](guest-experience.md)」と「ゲストアクセス」を参照してください。

### <a name="guest-access-vs-external-access-federation"></a>ゲスト アクセスと外部アクセス (フェデレーション)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> 現時点では、Microsoft Teams はゲスト残っの役割をサポートしていません。 少なくとも、Microsoft Teams でのゲストアクセスを有効にするには、[メンバーが招待できる] トグルを [はい] に設定する必要があります。 "メンバーは招待できます" を "いいえ" に設定して、Office 365 グループおよび Microsoft Teams でゲストアクセスを有効にすると、管理者はディレクトリへのゲストの招待を制御できます。 ゲストはディレクトリに入った後、管理者ではない、チーム所有者としてのメンバーによってチームに追加されることができます。

## <a name="if-your-guests-are-seeing-license-errors"></a>ゲストに対してライセンスのエラーが表示されている場合

Microsoft Teams のゲストアクセスでは、Azure Active Directory (Azure AD) Business to Business (B2B) とライセンスモデルが使用されます。 ライセンスエラーが表示される場合は、組織のユーザーが組織にゲストを招待できるように、組織のライセンス要件を理解するために、 [B2B ライセンスガイダンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)をお読みください。

次の点にご注意ください。

- ゲストとは、自分の組織の外部のユーザーのことです。 社内の従業員、オンサイトの請負業者、オンサイトの代理業者などは、ゲストとして追加することはできません。 これは、関連会社にも提供されます。
- ゲスト ライセンスは、招待する組織に対してカウントされます。 必要なライセンスの数を算出するときは、このことを考慮に入れます。
- 招待されたゲストが別の Office 365 テナントからのユーザーであろうと、個人のメール アドレスを使用していようと、ライセンスがカウントされる対象は自分の組織になります。

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□  手順 1: Azure AD ビジネス ツー ビジネスの設定を構成する

1. テナント管理者として[Azure ポータル](https://portal.azure.com)にサインインします。
2. **Azure Active Directory** > **ユーザー** > の**ユーザー設定**を選択します。
3. [**外部ユーザー**] で、[**外部グループ作業設定の管理**] を選択します。
   > [!NOTE]
   > **外部コラボレーションの設定**は、[**組織関係**] ページからも利用できます。 Azure Active Directory で、[**管理**] の [**組織の関係** > の**設定**] に移動します。
4. [**外部コラボレーションの設定**] ページで、有効にするポリシーを選択します。

   ![外部コラボレーションの設定](media/control-who-to-invite.png)

  - **ゲストユーザーのアクセス許可は制限され**ます: このポリシーは、ディレクトリ内のゲストに対するアクセス許可を決定します。 ユーザー、グループ、またはその他のディレクトリリソースを列挙するなど、特定のディレクトリタスクのゲストをブロックするには、[**はい**] を選択します。 [**いいえ**] を選択して、ディレクトリの通常ユーザーと同じアクセス権をゲストに与えます。
   - **ゲスト残っロールの管理者とユーザーは、招待でき**ます。 "ゲスト残っ" ロールの管理者とユーザーがゲストを招待できるようにするには、このポリシーを **[はい]** に設定します。
   - **招待できるメンバー**: ディレクトリの管理者以外のメンバーにゲストの招待を許可するには、このポリシーを **[はい]** に設定します。
   
       > [!NOTE]
       > [**メンバーが招待可能**] を [**いいえ**] に設定して、Office 365 グループおよび Microsoft Teams でのゲスト アクセスを有効にすると、自分のディレクトリへのゲストの招待を管理者が制御することができます。 ゲストはディレクトリに入った後、管理者ではない、チーム所有者としてのメンバーによってチームに追加されることができます。 詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。
   
   - **招待できる**ゲスト: ゲストが他のゲストを招待できるようにするには、このポリシーを **[はい]** に設定します。
   - **ゲストのメールの1回限りのパスコードを有効にする (プレビュー)**: 1 回限りのパスコード機能の詳細については、「[ワンタイムパスコードの認証 (プレビュー)](one-time-passcode.md)」を参照してください。
   - **共同作業の制限**: 特定のドメインへの招待の許可または禁止の詳細については、「[特定の組織からの B2B ユーザーへの招待を許可またはブロック](allow-deny-list.md)する」を参照してください。

## <a name="-step-2-configure-office-365-groups"></a>□ 手順 2: Office 365 グループを構成する

1. Microsoft 365 管理センターで、[**設定**] > [**サービスとアドイン**] > [**Office 365 グループ**] に移動します。
2. [**組織外部のグループ メンバーがグループ コンテンツにアクセスすることを許可**] が [**オン**] に設定されていることを確認します。 この設定がオフになっていると、ゲストはどのグループ コンテンツにもアクセスすることはできません。
3. [**グループ所有者が組織外部のユーザーをグループに追加することを許可**] が [**オン**] に設定されていることを確認します。 この設定がオフになっていると、チームの所有者は新しいゲストを追加することができません。 少なくとも、ゲスト アクセスをサポートするためにこの設定をオンにする必要があります。

     ![Office 365 グループの切り替えを示すスクリーンショット](media/guest-access-checklist-office365.png)

これらの設定を構成する詳細な手順については、「 [office 365 グループでゲストアクセスを管理](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)する」および「 [office 365 グループのゲストアクセスを制御](Teams-dependencies.md#control-guest-access-in-office-365-groups)する」を参照してください。
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□ 手順 3: テナント レベルでのゲスト アクセスを有効にする

少なくとも、microsoft **teams 管理センター**で microsoft teams のゲストアクセスを有効にする必要があります。 

1. Teams 管理センターで、**[組織全体の設定]** > **[ゲスト アクセス]** を選択します。
2. **[Microsoft Teams でのゲスト アクセスを許可]** のスイッチを **[オン]** に設定します。

    ![Teams 設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-set-up-guests-image1.png)

3. この同じページで、必要な他のゲストの設定を構成します。
4. [**保存**] をクリックします。

詳細な手順については、「 [Microsoft Teams へのゲストアクセスを有効または](set-up-guests.md)無効にする」を参照してください。


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


