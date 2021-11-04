---
title: 共有して共有Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: ユーザーがメールやメールの添付ファイルを Teams Outlook から他のチャットやチャネルに共有できる共有機能についてTeams。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fd8e31f83927c459f4a188f7316d000c13e5ef91
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774267"
---
# <a name="share-to-teams-from-outlook"></a>共有してTeams共有Outlook

Outlook から Teams への共有 ( 共有 ) を使用すると、Outlook から Teams 内の任意のチャットまたはチャネルに添付ファイルを含むメールを共有できます。 Teams

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook共有用のアドインを追加Teams 

[共有] Teams機能を使用するには、アプリのアドインがOutlook。 このアドインは、ユーザーが Web アプリまたはデスクトップ クライアントTeamsログオンするたびにTeamsインストールされます。

> [!NOTE]
> Exchange Online の Outlook と[Exchange Onlineクライアント](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)アクセス規則の Outlook の[](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)アドインを確認し、Outlook 正しく機能Outlookしてください。 また、接続されたエクスペリエンスを無効にすると、アプリのアドインがOutlook動作しなく場合があります。 詳細については[、「Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) in Office」を参照してください。  

[共有Teamsユーザーがチャネルを電子メールで送信する場合と同じトランスポート メカニズムを使用します。 チャットと共有する場合、メール (メールの添付ファイルを含む) は送信者のアカウントにOneDrive。 チャネルと共有するために、メールと添付ファイルは、SharePoint の[メール メッセージ] フォルダーにコピーされます。

Teams への共有用 Outlook アドインでは、Outlook アドインのドキュメントで詳しく説明されている要件セット 1.7 を使用します。このドキュメントには、Outlook アドイン、Outlook アドインの環境要件、要件セット 1.7 でサポートされている特定の Outlook クライアントの詳細が含まれます。 [](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)

## <a name="enabling-or-disabling-share-to-teams"></a>共有を有効または無効にするTeams

次Outlook PowerShell コマンドレットを使用して、Teams 共有アドインをユーザーごとに選択的に無効にしたり、有効にしたりすることができます。

> [!NOTE]
> アドインを無効にできるのは、アドインがインストールされた後のみです。 テナント内のすべてのユーザーに対して無効化を強制する場合は、スクリプトを定期的に実行します。

Share によって使用されるアドインのアドインをOutlook共有に使用するには、Teams コマンドレット[を実行します](/powershell/module/exchange/disable-app?view=exchange-ps)。 

Share によって使用されるアドインのアドインをOutlook共有に使用するには、Teams コマンドレット[を実行します](/powershell/module/exchange/enable-app?view=exchange-ps)。

## <a name="browsers-and-single-sign-on"></a>ブラウザーとシングル サインオン

共有はTeams、Outlook on the webクライアントOutlook WebView に依存します。 特定[のブラウザーを使用するクライアントOfficeアドイン](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins)で使用されるブラウザーに関するページを参照してください。 

> [!IMPORTANT]
> [共有Teams、サード パーティの Cookie とローカル ストレージアクセスの両方をユーザーのブラウザーで有効にする必要があります。

[共有Teamsシングル サインオン (SSO) を使用します。つまり、ユーザーは Share から Teams でアドインを使用するときに資格情報を指定する必要が生じます。 SSO for Outlook on the webサポート https://outlook.office365.com/owa/extSSO.aspx され https://outlook.office.com/owa/extSSO.aspx 、応答 URL が既定でサポートされます。 バニティ ドメインの場合、管理者は適切な応答 URL をAzure Active Directoryする必要があります。