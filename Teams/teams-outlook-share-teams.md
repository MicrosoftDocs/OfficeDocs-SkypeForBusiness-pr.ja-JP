---
title: Teamsに共有する
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: ユーザーがOutlookからTeams内の任意のチャットやチャネルにメールや電子メールの添付ファイルを共有できるようにする、Teamsに共有する機能について説明します。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a768424033ff300a079fc0b505d1e9ce32a970e
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682028"
---
# <a name="share-to-teams-from-outlook"></a>OutlookからTeamsに共有する

OutlookからTeamsに共有 (Teamsに共有) すると、ユーザーは、OutlookからTeams内の任意のチャットやチャネルに、添付ファイルを含むメールを共有できます。

## <a name="outlook-add-in-for-share-to-teams"></a>share to Teams用のアドインをOutlookする 

Teamsへの共有機能には、Outlook用のアドインが必要です。 このアドインは、ユーザーがTeams Web アプリまたはTeams デスクトップ クライアントにログオンするたびに自動的にインストールされます。

> [!NOTE]
> Exchange Onlineの[OutlookのアドインとExchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)[のクライアント アクセス規則](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)を確認して、Outlookのアドインが正しく機能していることを確認してください。 また、接続エクスペリエンスを無効にすると、Outlookのアドインが正常に動作しなくなる可能性があります。 詳細については、「[Officeのコネクテッド エクスペリエンス](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c)」を参照してください。  

共有Teamsでは、ユーザーがチャネルに電子メールを送信する場合と同じトランスポート メカニズムが使用されます。 チャットに共有する場合、電子メール (電子メールの添付ファイルを含む) が送信者のOneDriveにコピーされます。 チャネルに共有する場合、電子メールと添付ファイルはSharePointの **[電子メール メッセージ**] フォルダーにコピーされます。

Share to Teams のOutlook アドインでは、Outlook アドインの詳細、Outlook アドインの環境要件、要件セット 1.7 でサポートされている特定のOutlook クライアントを含む、Outlook アドインの[ドキュメント](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)で詳しく説明されているように、要件セット 1.7 が使用されます。

## <a name="enabling-or-disabling-share-to-teams"></a>Teamsへの共有を有効または無効にする

Share to TeamsのOutlook アドインは、次の PowerShell コマンドレットを使用して、ユーザーごとに選択的に無効または有効にすることができます。

> [!NOTE]
> アドインを無効にできるのは、アドインがインストールされた後のみです。 テナント内のすべてのユーザーに対して無効化を強制する場合は、スクリプトを定期的に実行します。

Share がTeamsに使用するOutlookのアドインを無効にするには、[ここで見つかったコマンドレット](/powershell/module/exchange/disable-app)を実行します。

Share でTeamsに使用されるOutlookのアドインを有効にするには、[ここで見つかったコマンドレット](/powershell/module/exchange/enable-app)を実行します。

## <a name="browsers-and-single-sign-on"></a>ブラウザーとシングル サインオン

Outlook on the webクライアントとOutlookデスクトップ クライアントの両方で、Teamsに共有するには、ブラウザーの WebView に依存します。 どのクライアント[がどの特定のブラウザーを使用](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins)するかの詳細については、「Office アドインで使用されるブラウザー」を参照してください。 

> [!IMPORTANT]
> Teamsに共有するには、ユーザーのブラウザーに対してサード パーティの Cookie とローカル ストレージ アクセスの両方を有効にする必要があります。

Share to Teamsではシングル サインオン (SSO) が使用されます。つまり、ユーザーは Share を使用してアドインを使用してTeamsするときに資格情報を指定する必要はありません。 既定では、Outlook on the webの SSO は URL をサポート<https://outlook.office365.com/owa/extSSO.aspx>し、<https://outlook.office.com/owa/extSSO.aspx>応答します。 バニティ ドメインの場合、管理者は適切なAzure Active Directory応答 URL を追加する必要があります。
