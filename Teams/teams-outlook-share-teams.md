---
title: 共有して共有Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Teams のチャットまたはチャネルにメールやメールの添付ファイルを共有できる共有Outlook機能についてTeams。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb13db7a7ebb5728913b58fb712ad86d851d469a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62409830"
---
# <a name="share-to-teams-from-outlook"></a>共有してTeamsからOutlook

[Outlook から Teams に共有] を使用すると、Outlook から Teams 内の任意のチャットまたはチャネルに添付ファイルを含むメールを共有できます。 Teams

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook共有用のアドインのTeams 

[共有Teams機能を使用するには、アプリのアドインがOutlook。 このアドインは、ユーザーが Teams Web アプリまたはデスクトップ クライアントにログオンするたびにTeamsインストールされます。

> [!NOTE]
> Exchange Online の Outlook と [](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) Exchange Online のクライアント アクセス規則のアドインを確認して、Outlook のアドイン[](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)が正しく機能Outlookしてください。 また、接続されたエクスペリエンスを無効にすると、アプリのアドインがOutlook動作しなく場合があります。 詳細については[、「Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) in Office」を参照してください。  

[共有Teamsユーザーがチャネルを電子メールで送信する場合と同じトランスポート メカニズムを使用します。 チャットと共有する場合、メール (メールの添付ファイルを含む) は送信者のアカウントにOneDrive。 チャネルと共有するために、メールと添付ファイルは、SharePoint の [電子メール メッセージ] フォルダーにコピーされます。

Teams への共有用 Outlook アドインでは、Outlook アドインのドキュメントで詳しく説明されている要件セット 1.7 を使用します。この[](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)ドキュメントには、Outlook アドイン、Outlook アドインの環境要件、要件セット 1.7 でサポートされている特定の Outlook クライアントの詳細が含まれています。

## <a name="enabling-or-disabling-share-to-teams"></a>共有を有効または無効にするTeams

次Outlook PowerShell コマンドレットを使用して、Teams 共有用の新しいアドインをユーザーごとに選択的に無効にしたり、有効にしたりすることができます。

> [!NOTE]
> アドインを無効にできるのは、アドインがインストールされた後のみです。 テナント内のすべてのユーザーに対して無効化を強制する場合は、スクリプトを定期的に実行します。

共有によって使用されるアドインのアドインOutlookを無効にするには、Teamsコマンドレット[を実行します](/powershell/module/exchange/disable-app?view=exchange-ps)。 

Share によって使用されるアドインのアドインをOutlookを有効にするには、Teamsコマンドレット[を実行します](/powershell/module/exchange/enable-app?view=exchange-ps)。

## <a name="browsers-and-single-sign-on"></a>ブラウザーとシングル サインオン

共有はTeamsデスクトップ クライアントOutlook on the web Outlook、ブラウザーの WebView に依存します。 特定[のブラウザーを使用Officeクライアント](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins)の詳細については、アドインで使用されるブラウザーに関するページを参照してください。 

> [!IMPORTANT]
> [共有Teams、サード パーティの Cookie とローカル ストレージアクセスの両方をユーザーのブラウザーで有効にする必要があります。

[共有Teams シングル サインオン (SSO) を使用します。つまり、ユーザーは Share から Teams でアドインを使用するときに資格情報を指定する必要が生じます。 SSO for Outlook on the webサポートされhttps://outlook.office365.com/owa/extSSO.aspx、応答 https://outlook.office.com/owa/extSSO.aspx URL が既定でサポートされます。 バニティ ドメインの場合、管理者は適切な応答 URL をAzure Active Directory必要があります。