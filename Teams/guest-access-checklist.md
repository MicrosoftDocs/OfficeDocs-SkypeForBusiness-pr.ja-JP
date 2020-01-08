---
title: Microsoft Teams のゲスト アクセスのチェックリスト
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: このチェックリストを使用すると、Microsoft Teams の設定が容易になります。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3354f7b503b2f1ea91c050a751b5d7d9ab0537a
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962535"
---
<a name="microsoft-teams-guest-access-checklist"></a>Microsoft Teams のゲスト アクセスのチェックリスト
==========================================

このチェックリストを使用して、Microsoft Teams でゲストアクセスを有効にし、構成することができます。 これらの変更を行うには、グローバル管理者またはチーム管理者である必要があります。

> [!IMPORTANT]
> 変更が有効になるまで最大24時間かかることがあります。 

この短いビデオ (5:31 分) をご覧になり、チームを含む、Microsoft 365 全体でゲストアクセスを有効にする方法を確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a>手順 1: Teams の組織全体レベルでゲストアクセスを有効にする

ゲストアクセスを有効にするには、 **Microsoft Teams 管理センター**に移動します。 

1. Teams 管理センターで、**[組織全体の設定]** > **[ゲスト アクセス]** を選択します。
2. **[Microsoft Teams でのゲスト アクセスを許可]** のスイッチを **[オン]** に設定します。

    ![Teams 設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-set-up-guests-image1.png)

3. この同じページで、ゲストの**通話**、**会議**、**メッセージ**設定をオンまたはオフにします。
4. **[保存]** をクリックします。

> [!TIP]
> Azure Active Directory、SharePoint Online、Office 365 グループで既定の設定を使用している場合、ゲストアクセスの構成が完了している可能性があります。 この場合は、残りの手順をスキップできます。 不明な場合、または AAD、SharePoint Online、または Office 365 グループのカスタム設定を使用している場合は、このチェックリストの残りの手順に進んでください。


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a>手順 2: Azure AD のビジネス対ビジネスの設定を構成する

1. テナント管理者として[Azure ポータル](https://portal.azure.com)にサインインします。
2. **Azure Active Directory** > **ユーザー** > の**ユーザー設定**を選択します。
3. [**外部ユーザー**] で、[**外部グループ作業設定の管理**] を選択します。
   > [!NOTE]
   > **外部コラボレーションの設定**は、[**組織関係**] ページからも利用できます。 Azure Active Directory で、[**管理**] の [**組織の関係** > の**設定**] に移動します。
4. [**外部コラボレーションの設定**] ページで、有効にするポリシーを選択します。

    - **ゲストユーザーのアクセス許可は制限され**ます: このポリシーは、ディレクトリ内のゲストに対するアクセス許可を決定します。 ユーザー、グループ、またはその他のディレクトリリソースを列挙するなど、特定のディレクトリタスクのゲストをブロックするには、[**はい**] を選択します。 [**いいえ**] を選択して、ディレクトリの通常ユーザーと同じアクセス権をゲストに与えます。
     - **ゲスト残っロールの管理者とユーザーは、招待でき**ます。 "ゲスト残っ" ロールの管理者とユーザーがゲストを招待できるようにするには、このポリシーを **[はい]** に設定します。
     - **招待できるメンバー**: ディレクトリの管理者以外のメンバーにゲストの招待を許可するには、このポリシーを **[はい]** に設定します。

         > [!NOTE]
         > [**メンバーが招待可能**] を [**いいえ**] に設定して、Office 365 グループおよび Microsoft Teams でのゲスト アクセスを有効にすると、自分のディレクトリへのゲストの招待を管理者が制御することができます。 ゲストはディレクトリに入った後、管理者ではない、チーム所有者としてのメンバーによってチームに追加されることができます。 詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。
         > [!IMPORTANT]
         > ゲスト アクセスを Teams ですべて機能させるには、[**メンバーが招待できる**] を [**はい**] に設定する必要があります。   
     - **招待できる**ゲスト: ゲストが他のゲストを招待できるようにするには、このポリシーを **[はい]** に設定します。
         > [!IMPORTANT]
         > 現在、Teams はゲスト招待者の役割をサポートしていないため、[**ゲストが招待できる**] を [**はい**] に設定しても、ゲストは Teams 内の他のゲストを招待できません。
     - **ゲストのメールの1回限りのパスコードを有効にする (プレビュー)**: 1 回限りのパスコード機能の詳細については、「[ワンタイムパスコードの認証 (プレビュー)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)」を参照してください。
     - **共同作業の制限**: 特定のドメインへの招待の許可または禁止の詳細については、「[特定の組織からの B2B ユーザーへの招待を許可またはブロック](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)する」を参照してください。
        > [!NOTE]
        > 共同作業の制限については、「 [B2B の外部コラボレーションを有効にする」と「ゲストを招待できるユーザーを管理する](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)」をご覧ください
      
 
    ゲストを招待できるユーザーの管理方法の詳細については、「[Azure Active Directory B2B コラボレーションの招待の委任](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)」を参照してください。


## <a name="step-3-configure-office-365-groups"></a>手順 3: Office 365 グループを構成する

1. Microsoft 365 管理センターで、[**設定** > **サービス & アドイン**] に移動し、[ **Office 365 グループ**] を選択します。

     ![Office 365 グループの切り替えを示すスクリーンショット](media/guest-access-checklist-office365.png)
2. [**組織外のメンバーにグループのコンテンツをグループと**して使用する] チェックボックスがオンになっていることを確認します。 この設定をオフにすると、ゲストはグループのコンテンツにアクセスできなくなります。
3. [**グループの所有者に組織外のユーザーをグループに追加**することを許可する] チェックボックスがオンになっていることを確認します。 この設定をオフにすると、チームの所有者は新しいゲストを追加できなくなります。 少なくとも、ゲストアクセスをサポートするために、この設定をオンにする必要があります。

これらの設定を構成する詳細な手順については、「 [office 365 グループでゲストアクセスを管理](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)する」および「 [office 365 グループのゲストアクセスを制御](Teams-dependencies.md#control-guest-access-in-office-365-groups)する」を参照してください。
 

## <a name="step-4-configure-sharing-in-office-365"></a>手順 4: Office 365 で共有を構成する 

ユーザーがゲストを追加できることを確認します。 次の操作を実行してください。

1. Microsoft 365 管理センターで、[**設定**] > [**セキュリティとプライバシー**] に移動します。

     ![サービスの設定の例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. **[共有]** で **[編集]** を選択します。

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. **[ユーザーがこの組織に新しいゲストを追加できるようにする]** を **[オン]** に設定し、**[保存]** をクリックします。

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
    > [!NOTE]
    > この設定は、Azure AD の [**ユーザー設定** > ] の [**外部ユーザー** ] で [**メンバーと招待でき**ます] 設定と同じです。  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a>手順 5: SharePoint で共有設定を確認する

1. Microsoft 365 管理センターにサインインします。
2. [**管理センター**] で、[ **SharePoint**] を選びます。
3. 新しい SharePoint 管理センターで、[**サイト**] の下にある [**アクティブサイト**] を選びます。

    ![SharePoint 管理センターのアクティブなサイト](media/guest-access-checklist-SPOSettings0.png)

3. サイトを選択し、[**共有**] をクリックします。
4. このオプションが [**すべて**] または **[新規] および [既存のゲスト**] に設定されていることを確認します。
 
     ![SharePoint Online の設定のトグルの例を示すスクリーンショット](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a>手順 6: ゲストユーザーの権限を設定する

Teams アプリケーションの個々のチームレベルで、ゲストがチャネルを作成、更新、または削除できるかどうかを制御するゲストのアクセス許可を構成します。 チーム管理者とチーム所有者は、これらの設定を構成できます。

![チーム/チャネルの設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-TeamsSettings2.png)

ゲストアクセスの詳細については、「 [teams のゲストアクセス](guest-access.md)」を参照して、「 [Microsoft teams へのゲストアクセスを有効または](set-up-guests.md)無効にする」を参照してください。


## <a name="troubleshooting"></a>トラブルシューティング

ゲストアクセスの設定で問題が発生した場合、または Teams でゲストを追加した場合は、次のリソースを参考にしてください。

[Microsoft Teams でのゲストアクセスに関する問題のトラブルシューティング](troubleshoot-guest-access.md)

[チームのトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



