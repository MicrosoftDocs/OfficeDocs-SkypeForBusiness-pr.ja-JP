---
title: マイクロソフト チームのゲスト アクセスのチェックリスト
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: マイクロソフト チームのゲスト アクセスでゲスト アクセスを設定するのには、このチェックリストを使用します。
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 256ca09b8da5ccaed3ab5797e9d67246cebfee4e
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678142"
---
<a name="teams-guest-access-checklist"></a>チームのゲスト アクセスのチェックリスト
==========================================

有効にして、組織の基本設定に応じて、マイクロソフトのチームでゲスト アクセス機能を構成するためには、このチェックリストを使用します。




## <a name="--enable-guest-access-at-the-tenant-level"></a>テナントのレベルで有効にするゲスト アクセスを □

を通じてチーム & ビジネス管理センターでは、Skype に移動するhttps://admin.teams.microsoft.com。 ここでは、[組織全体にわたる設定 'と' Guest' のアクセス] タブには、最後に、このタブ内で選択 ' ゲスト アクセスを許可では、マイクロソフトのチーム' を有効になっているでを選択します。 

## <Need to display a photo of the new admin center>

## <a name="-enable-specific-settings-for-channels"></a>□ は、チャネル固有の設定を有効にします。 
アプリケーションでは、チーム、個々 のチーム レベルでは、ゲスト アクセス許可を構成来園者が作成、更新、およびチャンネルを削除できるようにします。 管理者、他チームの所有者は、この設定を構成できます。

![スクリーン ショットは、チームとチャネルの設定の表示/非表示の例を示しています。](media/guest-access-checklist-TeamsSettings2.png)


操作方法のビデオを含む詳細については、[マイクロソフトのチームでのゲスト アクセス](guest-access.md)を参照してください。



## <a name="--configure-sharing-in-office-365"></a>□ は、Office 365 の共有を構成します。 

□ は、ユーザーは、来園者を追加できることを確認します。 ここではどのようにします。

1. **設定**に移動し、Office 365 管理センターで、 > **のセキュリティとプライバシー**。
![スクリーン ショットは、サービスの設定の例を示しています。](media/guest-access-checklist-Office365Admin_Services_addins.png)
1. **共有**、**編集**を選択します。![のスクリーン ショットは、共有の設定の編集] ボタンの例を示しています。](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
2. **ユーザーがこの組織に新しいゲストを追加できるように**設定**を**し、[**保存**] をクリックします。![のスクリーン ショットは、共有の設定の表示/非表示の例を示しています。](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 

 > [!NOTE]
> この設定は、同じことに、**メンバーを招待できる**ユーザーの設定で > Azure AD 内の外部のユーザーです。  




## <a name="-configure-office-365-groups"></a>□ は、Office 365 のグループを構成します。

**設定**に移動し、Office 365 管理センターで、 > **サービスおよびアドイン** > **Office 365 のグループ**です。

**グループ コンテンツには、組織のアクセス以外のグループのメンバー**になっている**** を確認します。 この設定をオフにすると、来園者は任意のグループのコンテンツにアクセスできません。

**オン**に設定 **、グループの所有者のグループを組織外のユーザーを追加**することを確認します。 この設定をオフにすると、チームの所有者は新しいゲストを追加するのにはできません。 最低限、この設定は guest アクセスをサポートするために"on"にする必要があります。

これらの設定を構成する方法の詳細については、[マイクロソフトのチームでのゲスト アクセスを許可](Teams-dependencies.md)し、 [Office 365 のグループへのゲスト アクセスの許可/禁止](https://go.microsoft.com/fwlink/?linkid=869658)の「Office 365 グループ」を参照してください。
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a>□ Azure AD の企業間 (B2B) の設定の構成
1. サインインするのにhttps://portal.azure.com。
2. **Azure Active directory**は、左側のウィンドウでクリックします。
3. [**管理**] で、**ユーザー設定**をクリックします。
4. **外部ユーザー**] の下の [**外部管理の共同作業の設定**] をクリックします
5. **外部コラボレーションの設定**] ページで**メンバーを招待できる**、 **Yes**に設定されていることを確認します。![のスクリーン ショットは、AAD の設定の表示/非表示の例を示しています。 ](media/guest-access-checklist-AADSettings1.png)

    

来園者をサポートするために少なくとも ► は、 **[はい]** に設定してください**メンバーを招待できます**。

> > [!NOTE]
> > **メンバーを招待****なし**に設定して Office 365 のグループとマイクロソフトのチームでのゲスト アクセスを有効にする場合、管理者はディレクトリへのゲストの招待状を制御できます。 来園者は、ディレクトリには後に、追加できますチームに管理者以外のメンバー (チーム所有者) によって。


詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。







## <a name="-verify-sharing-setting-in-sharepoint"></a>□ SharePoint での共有設定の確認
1. Office 365 管理センターにサインインします。
2. **管理センター**] をクリックし、 **SharePoint**を選択します。
3. SharePoint 管理センターでは、**共有**を選択します。
4. オプションの確認 **、組織外の共有を許可しない**が選択されて*いない*場合。![のスクリーン ショットは、Sparepoint のオンライン設定の表示/非表示の例を示しています。 ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a>□ 検証アカウントのライセンスと種類

- **チームのアカウントがライセンス**: ルートと他のいくつかの Office 365 テナントに実際のユーザー アカウント"Guest"アカウントの実際のユーザー アカウントがライセンスを保有チームの"Guest"のです。 
- **アカウントする必要があります Office 365 の学校かアカウント、またはアカウントの MSA の作業**: 現時点では、Azure Active Directory、Office 365 の作業時間や学校のアカウント、または Microsoft アカウント (MSA) に対応する電子メール アドレスを持つユーザーをゲスト ユーザーとして追加できます。 
 
## <a name="-configure-environment"></a>□ 構成環境


来園者は、ホストのテナントで必要な場合、多要素認証 (MFA) を使用する必要があります。
詳細については、[識別情報モデルとマイクロソフトのチームでの認証](identify-models-authentication.md)を参照してください。

## <a name="-understand-limitations-for-guests"></a>来園者の □ 理解の制限事項

ゲストの経験では、設計によって制限があります。 問題ではないものを修理しようとしていないために、ゲストの経験を理解することを確認します。
ここでは一部のマイクロソフトのチームでゲストに使用できない機能の一覧です。

- ビジネスの OneDrive
- チーム外の人の検索
- 予定表、スケジュールされたミーティングの場合、またはミーティングの詳細
- PSTN
- 組織図
- 作成またはチームを変更します。
- チームを参照します。
- ユーザー間のチャットにファイルをアップロードします。

詳細については、[ゲストの経験のように](guest-experience.md)、 [Office 365 のグループでのゲスト アクセス](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)を参照してください。




## <a name="troubleshooting"></a>トラブルシューティング

マイクロソフトのチームで、来園者を追加すると問題がある場合は、[ゲスト アクセスのトラブルシューティング ガイド 』](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)を参照してください。


