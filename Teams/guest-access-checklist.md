---
title: Microsoft Teams のゲスト アクセスのチェックリスト
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/18
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: マイクロソフト チームのゲスト アクセスでゲスト アクセスを設定するのには、このチェックリストを使用します。
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: a7fa7e7d7999bd42748e1997a4ec73b37ca14a67
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772770"
---
<a name="teams-guest-access-checklist"></a>チームのゲスト アクセスのチェックリスト
==========================================

有効にして、組織の基本設定に応じて、マイクロソフトのチームでゲスト アクセス機能を構成するためには、このチェックリストを使用します。

## <a name="understand-the-limitations-for-guests"></a>来園者の制限を理解します。

ゲストの経験では、設計によって制限があります。 問題ではないものを修理しようとしていないために、ゲストの経験を理解することを確認します。 ここでは一部のマイクロソフトのチームでゲストに使用できない機能の一覧です。

- ビジネスの OneDrive
- チーム外の人の検索
- 予定表、スケジュールされたミーティングの場合、またはミーティングの詳細
- PSTN
- 組織図
- 作成またはチームを変更します。
- チームを参照します。
- ユーザー間のチャットにファイルをアップロードします。

詳細については、[ゲストの経験のように](guest-experience.md)、 [Office 365 のグループでのゲスト アクセス](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)を参照してください。

## <a name="if-your-guests-are-seeing-license-errors"></a>来園者には、ライセンスのエラーが表示される場合

マイクロソフトのチームでのゲスト アクセスでは、作業中のディレクトリ ビジネス (B2b) に Azure とのライセンス ・ モデルを使用します。 ライセンス エラーを表示している場合は、組織には、ユーザーが組織には、来園者を招待することができるように、ライセンス契約の要件を理解する B2B ライセンス ガイドを参照してくださいください。

いくつかの点に注意してください。

- Azure AD のライセンスをユーザーに割り当てられた各支払い済みの場合に、ユーザーが外部ユーザーの許可] の下には最大 5 つのゲスト ユーザーを招待できます。
- 来園者は、組織外のユーザーです。 従業員、オンサイトの契約社員、オンサイト エージェント、およびようには、来園者として追加できません。 関連会社にも当てはまります。
- ゲストのライセンスは、招待側の組織に対してカウントされます。 必要なライセンスの数を計算するときは、これを検討します。
- 招待されたゲストが別の Office 365 テナントに由来するか、個人用の電子メール アドレスを使用しているかどうかの組織に対するライセンスがカウントされます。

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□ 手順 1: Azure AD ビジネス ツー ビジネスの設定を構成します。

1. サインインするのにhttps://portal.azure.com。
2. **Azure Active directory**は、左側のウィンドウでクリックします。
3. [**管理**] で、**ユーザー設定**をクリックします。
4. [**外部のユーザー**を**外部の管理の共同作業の設定**をクリックします。
5. **外部コラボレーションの設定**] ページで**メンバーを招待できる**、 **Yes**に設定されていることを確認します。

      ![スクリーン ショットでは、AAD の設定の表示/非表示の例を示します。 ](media/guest-access-checklist-AADSettings1.png)

    来園者をサポートするために**メンバーを招待**する必要がありますに設定する **[はい]**。 
   
> [!NOTE] 
> **なし**に**メンバーを招待できます**を設定し、Office 365 のグループとマイクロソフトのチームでのゲスト アクセスを有効にすると、管理者は、ディレクトリにゲストへの招待を制御できます。 来園者は、ディレクトリには後に、追加できますチームにチームの所有者は、管理者以外のメンバーで。

詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。


## <a name="-step-2-configure-office-365-groups"></a>□ 手順 2: Office 365 のグループを構成します。

1. Microsoft 365 管理センターで、[**設定]** > **サービスおよびアドイン** > **Office 365 のグループ**です。
2. **グループ コンテンツには、組織のアクセス以外のグループのメンバー**になっている**** を確認します。 この設定をオフにすると、来園者は任意のグループのコンテンツにアクセスできません。
3. **オン**に設定 **、グループの所有者のグループを組織外のユーザーを追加**することを確認します。 この設定をオフにすると、チームの所有者は新しいゲストを追加するのにはできません。 最低限、この設定は、ゲスト アクセスをサポートするにする必要があります。

     ![スクリーン ショットには Office 365 のグループの表示を切り替えます。](media/guest-access-checklist-office365.png)

これらの設定を構成する方法の詳細については、 [Office 365 のグループでのゲスト アクセスの管理](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)と Office 365 の「グループ」では、[マイクロソフト チームでのゲスト アクセス許可](Teams-dependencies.md)を] セクションを参照してください。
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□ ステップ 3: テナントのレベルでのゲスト アクセスを有効にします。

最低限には、**ゲスト**のライセンスの種類のすべてのユーザーのマイクロソフト チームをオンにする必要があります。 

1. チーム/Skype のビジネス管理センターで、**組織全体の設定**を選択します > **ゲスト アクセス**します。
2. **マイクロソフトのチームでのゲスト アクセスを許可する**スイッチを**On**に設定します。

    ![スクリーン ショットは、チームの設定の表示/非表示の例を示しています。](media/set-up-guests-image1.png)

3. この同じページで、必要なその他のゲスト設定を構成します。
4. [**保存**] をクリックします。

詳細については、[オンまたはオフは、マイクロソフトのチームへのゲスト アクセスを有効にする](set-up-guests.md)を参照してください。


## <a name="--step-4-configure-sharing-in-office-365"></a>□ 手順 4: Office 365 の共有を構成します。 

来園者を追加できることを確認します。 ここではどのようにします。

1. **設定**に移動し、Microsoft 365 管理センターで、 > **のセキュリティとプライバシー**。

     ![スクリーン ショットは、サービスの設定の例を示しています。](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. **共有**、**編集**を選択します。

     ![スクリーン ショットは、共有の設定の表示/非表示の例を示しています。](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. **ユーザーがこの組織に新しいゲストを追加できるように**設定**を**し、[**保存**] をクリックします。

     ![スクリーン ショットは、共有の設定の表示/非表示の例を示しています。](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> この設定は、**メンバーを招待できる****ユーザー設定**の設定と同じ > Azure AD では、**外部のユーザー**です。  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a>□ ステップ 5: SharePoint の共有の設定を確認

1. Office 365 管理センターにサインインします。
2. **管理センター**] をクリックし、 **SharePoint**を選択します。
3. SharePoint 管理センターでは、**共有**を選択します。
4. オプションの確認 **、組織外の共有を許可しない**が選択されて*いない*場合。
 
     ![スクリーン ショットは、Sparepoint のオンライン設定の表示/非表示の例を示します。](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a>□ ステップ 6: チャンネルの特定の設定を有効にします。 

アプリケーションでは、チーム、個々 のチーム レベルでは、ゲスト アクセス許可を構成来園者が作成、更新、およびチャンネルを削除できるようにします。 管理者、他チームの所有者は、この設定を構成できます。

![スクリーン ショットは、チームとチャネルの設定の表示/非表示の例を示しています。](media/guest-access-checklist-TeamsSettings2.png)

操作方法のビデオを含む詳細については、[マイクロソフトのチームでのゲスト アクセス](guest-access.md)を参照してください。


## <a name="troubleshooting"></a>トラブルシューティング

マイクロソフトのチームで、来園者を追加すると問題がある場合は、[ゲスト アクセスのトラブルシューティング ガイド 』](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)を参照してください。


