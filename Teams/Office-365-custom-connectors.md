---
title: Microsoft 365コネクタとカスタム コネクタを管理する
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: 使用するサービスのTeams チャネルにコンテンツや更新プログラムを頻繁に配信することで、コネクタがチームを更新し続ける方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: de0c0398d511aca05a69220e0e35a28268535c59
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190447"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>Microsoft 365コネクタとカスタム コネクタを管理する

チームを更新し続けるために、コネクタは頻繁に使用されるコンテンツとサービスの更新をTeams チャネルに直接配信します。 コネクタを使用すると、Teams ユーザーは Trello、Wunderlist、GitHub、Azure DevOps Servicesなどの一般的なサービスから更新プログラムを受け取ることができます。 更新プログラムは、チーム内のチャット ストリームに直接投稿されます。

Microsoft 365 コネクタは、Microsoft Teams グループとMicrosoft 365 グループの両方で使用されるため、すべてのメンバーが同期を維持し、関連情報を迅速に受信しやすくなります。 Microsoft TeamsとExchangeの両方で同じコネクタ モデルを使用するため、両方のプラットフォーム内で同じコネクタを使用できます。 ただし、Microsoft 365 グループ用に構成されたコネクタを無効にすると、Microsoft 365 グループがコネクタを作成する機能も無効になります。

チームのアクセス許可が許可されている場合、チームのメンバーはチームをコネクタを使用して一般的なクラウド サービスに接続でき、すべてのチーム メンバーにそのサービスからのアクティビティが通知されます。 コネクタは、最初にコネクタを設定したメンバーが離れた後も引き続き機能します。 追加または削除するアクセス許可を持つチーム メンバーは、他のメンバーによるコネクタの設定を変更できます。

## <a name="enable-or-disable-connectors-in-teams"></a>Teamsでコネクタを有効または無効にする

Exchange Online PowerShell V2 モジュールは、最新の認証を使用し、MFA と呼ばれる多要素認証を使用して、Microsoft 365のすべてのExchange関連する PowerShell 環境に接続します。 管理者は、Exchange Online PowerShell を使用して、テナント全体または特定のグループ メールボックスのコネクタを無効にし、そのテナントまたはメールボックス内のすべてのユーザーに影響を与えることができます。 少数の特定のユーザーに対して無効にすることはできません。 また、GCC テナントと呼ばれるGovernment Community Cloudのコネクタは既定で無効になっています。

テナント設定は、グループ設定よりも優先されます。 たとえば、管理者がグループのコネクタを有効にし、テナントで無効にした場合、グループのコネクタは無効になります。 Teamsでコネクタを有効にするには、MFA の有無にかかわらず先進認証を使用して [powerShell Exchange Onlineに接続](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true)します。

コネクタを有効または無効にするには、powerShell で次のコマンドExchange Online実行します。

* テナントのコネクタを無効にするには: `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* テナントの実行可能なメッセージを無効にするには: `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Teamsのコネクタを有効にするには、次のコマンドを実行します。
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

PowerShell モジュール交換の詳細については、「 [Set-OrganizationConfig」を参照してください](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true)。 Outlook コネクタを有効または無効にするには、[Outlook内のグループにアプリを接続](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)します。

<!--- TBD: Find out how can we get to know about completion of customer migration.
Delete this section after customer migration to new Webhook URL is complete.
--->

## <a name="publish-connectors-for-your-organization"></a>組織のコネクタを発行する

カスタム コネクタを組織内のユーザーのみが使用できるようにする場合は、カスタム コネクタ アプリを組織のアプリ カタログにアップロードできます。 アプリ パッケージをアップロードした後、エンド ユーザーは組織のアプリ カタログからコネクタをインストールし、チームでコネクタを構成して使用できます。

<!---TBD: Check if these instructions are for admins or end-users. I cannot find these options either in Teams or in TAC.

To set up a connector:

1. Select **Apps** from the left navigation bar.
1. In the **Apps** section, select **Connectors**.
1. Select the connector that you want to add.
1. From the pop-up menu, select **Add to a team**.
1. In the search box, type a team or channel name.
1. Select **Set up a Connector** from the pop-up menu in the bottom right corner of the dialog window.
--->

> [!IMPORTANT]
> カスタム コネクタは、Government Community Cloud (GCC)、GCC-High、および国防総省 (DOD) では使用できません。

チームまたはチャネルでコネクタを使用するには、チャネルの右上隅にある [その他のオプション] メニューを開きます。 メニューから [ **コネクタ** ] を選択し、必要なコネクタ アプリを探すか検索します。 必要に応じて、選択したコネクタを構成します。

:::image type="content" source="media/connectors-selection-ui.png" alt-text="チャネルの右上隅にある [その他のオプション] からTeamsチャネルにコネクタを追加します。":::

## <a name="update-url-of-a-connector"></a>コネクタの URL を更新する

Teams コネクタは、セキュリティを強化するために新しい URL に移行しています。 移行中に、構成済みのコネクタを更新するための通知が表示されます。 コネクタ サービスの中断を防ぐために、コネクタを最も早く更新します。 コネクタを更新するには:

1. コネクタの構成ページで、構成されたコネクタの横にある **[注意が必要]** メッセージを確認します。

   :::image type="content" source="media/Teams_Attention_Required_message.png" alt-text="[注意が必要] メッセージのスクリーンショット。":::

1. 受信 Webhook コネクタの接続を再作成するには、[URL の **更新** ] を選択し、生成された Webhook URL を使用します。

   :::image type="content" source="media/Teams_update_URL_button.png" alt-text="[URL の更新] ボタンのスクリーンショット。":::

1. その他のコネクタの種類については、コネクタを削除し、コネクタ構成を再作成します。 **URL が最新の** メッセージが表示されます。

   :::image type="content" source="media/Teams_URL_up_to_date.png" alt-text="URL のスクリーンショットは最新のメッセージです。":::

## <a name="see-also"></a>関連項目

* [カスタム コネクタと Webhook の概要](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Office 365 コネクタを作成する](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
