---
title: Microsoft 365 コネクタとカスタム コネクタを管理する
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 01/24/2023
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: コネクタが、コンテンツと更新プログラムを使用するサービスの Teams チャネルに直接頻繁に配信することで、チームの更新を維持する方法について説明します。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf38711da0205e7c674e769942d00d340d51f66e
ms.sourcegitcommit: 1cb5f7129562eb2b228da23497c0e09e53da3872
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2023
ms.locfileid: "69983685"
---
# <a name="manage-microsoft-365-connectors-and-custom-connectors"></a>Microsoft 365 コネクタとカスタム コネクタを管理する

Microsoft Teams のコネクタは、サード パーティのサービスから Teams チャネルにコンテンツとサービスの更新プログラムを直接配信します。 コネクタを使用して、ユーザーは Trello、Wunderlist、GitHub、Azure DevOps Services などの一般的なサービスから更新プログラムを受け取ります。 更新プログラムは、チャット ストリームに直接投稿されます。 これにより、すべてのメンバーが簡単に同期を維持し、関連情報をすばやく受け取ります。

Microsoft 365 コネクタは、Teams と Microsoft 365 の両方のグループで使用されます。 Teams と Microsoft Exchange で同じコネクタを使用できます。 

<!--- However, if you disable any connectors configured for a Microsoft 365 group, it also disables the ability for the Microsoft 365 group to create connectors. --->

チームのアクセス許可で許可されている場合、チームのメンバーはチームにコネクタを追加でき、すべてのチーム メンバーにそのサービスからのアクティビティが通知されます。 追加または削除するアクセス許可を持つチーム メンバーは、他のメンバーによるコネクタの設定を変更できます。

## <a name="enable-or-disable-connectors-in-teams"></a>Teams でコネクタを有効または無効にする

Exchange Online PowerShell v2 モジュールは、最新の認証を使用し、多要素認証 (MFA) と連携して、Microsoft 365 のすべての Exchange 関連の PowerShell 環境に接続します。 管理者は、Exchange Online PowerShell を使用して、テナント全体または特定のグループ メールボックスのコネクタを無効にし、そのテナントまたはメールボックス内のすべてのユーザーに影響を与えることができます。 一部の特定のユーザーに対して無効にすることはできません。

テナント設定は、グループ設定よりも優先されます。 たとえば、管理者がグループのコネクタを有効にし、テナントに対して無効にした場合、グループのコネクタは無効になります。 Teams でコネクタを有効にするには、MFA を利用してもしなくても、先進認証を使用して [Exchange Online PowerShell に接続](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true)します。

コネクタを有効または無効にするには、Exchange Online PowerShell で次のコマンドを実行します。

* テナントに対してコネクタを無効にするには、`Set-OrganizationConfig -ConnectorsEnabled:$false`。
* テナントの操作可能なメッセージを無効にするには、`Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`。
* Teams に対してコネクタを有効にするには、次のコマンドを実行します。
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

PowerShell モジュール交換の詳細については、[Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true) を参照してください。 Outlook コネクタを有効または無効にするには、[Microsoft Outlook 内のグループにアプリを接続します](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)。

## <a name="publish-connectors-for-your-organization"></a>組織のコネクタを公開する

組織のユーザーがカスタム コネクタを使用できるようにするには、カスタム コネクタ アプリを組織のアプリ カタログにアップロードします。 組織内のエンド ユーザーは、チーム内でコネクタをインストール、構成、使用できます。

> [!IMPORTANT]
> カスタム コネクタは、Government Community Cloud (GCC)、Government Community Cloud-High (GCCH)、および米国国防総省 (DOD) 環境では使用できません。

チームまたはチャネルでコネクタを使用するには、チャネルの右上隅にある [その他のオプション] メニューを開きます。 メニューから **[コネクタ]** を選択し、必要なコネクタを探すか検索します。 必要に応じて、選択したコネクタを構成します。

:::image type="content" source="media/connectors-selection-ui.png" alt-text="チャネルの右上隅にあるその他のオプションから Teams のチャネルにコネクタを追加します。":::

## <a name="update-url-of-a-connector"></a>コネクタの URL を更新する

Teams コネクタは、セキュリティを強化するために新しい URL に移行しています。 移行中に、構成済みのコネクタを更新するための通知が表示されます。 コネクタ サービスの中断を防ぐために、コネクタを最も早く更新します。 コネクタを更新するには:

1. [コネクタの構成] ページで、構成済みのコネクタの横にある **[要確認]** メッセージを確認します。

   :::image type="content" source="media/teams-attention-required-message.png" alt-text="[要確認] メッセージのスクリーンショット。":::

1. 受信 Webhook コネクタの接続を再作成するには、**[URL の更新]** を選択し、生成された Webhook URL を使用します。

   :::image type="content" source="media/teams-update-url-option.png" alt-text="[URL の更新] ボタンのスクリーンショット。":::

1. その他のコネクタの種類の場合は、コネクタを削除し、コネクタ構成を再作成します。 「**URL は最新です**」メッセージが表示されます。

   :::image type="content" source="media/teams-url-updated.png" alt-text="「URL は最新です」メッセージのスクリーンショット。":::

## <a name="considerations-when-using-connectors-in-teams"></a>Teams でコネクタを使用するときの考慮事項

* Government Cloud Community (GCC) 環境では、コネクタは既定で無効になっています。 これらを有効にするには、`SetOrganizationConfig` コマンドレットを使用して `ConnectorsEnabled` または `ConnectorsEnabledForTeams` パラメーターを `$true` に設定します。 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true) に接続します。

* チームにコネクタを追加したユーザーがチームを離れた場合、コネクタは引き続き機能します。

* 次のコネクタは、2023 年 1 月以降は使用できません。

  * ほう
  * AIRBRAKE
  * AIRCALL
  * APPLINKS
  * APPSIGNAL
  * 豆
  * BITBUCKET
  * BITBUCKETSERVER
  * バディ
  * BUGSNAG
  * BUILDKITE
  * CATSONE
  * CHATRA
  * CIRCLECI
  * CODESHIP
  * Getresponse
  * GHOSTINSPECTOR
  * 溝
  * HEROKU
  * HONEYBADGER
  * インターホン
  * LOGENTRIES
  * NEWRELIC
  * OPSGENIE
  * PAGERDUTY
  * PAPERTRAIL
  * Pingdom
  * PIVOTALTRACKER
  * RAYGUN
  * ROLLBAR
  * RUNSCOPE
  * SATISMETER
  * セマフォ
  * 歩哨
  * SHAREPOINTNEWS
  * SIMPLEINOUT
  * STATUSPAGEIO
  * Subversion
  * TEAMFOUNDATIONSERVER
  * TESTFAIRY
  * TRAVISCI
  * UPDOWN
  * USERLIKE
  * XPDEV

## <a name="related-articles"></a>関連記事

* [カスタム コネクタと Webhook の概要](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Office 365 コネクタを作成する方法](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
