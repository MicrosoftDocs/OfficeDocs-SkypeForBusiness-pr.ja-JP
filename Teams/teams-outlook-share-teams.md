---
title: 共有を共有Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Teams のチャットやチャネルにメールやメールの添付ファイルを共有できる共有機能についてOutlook Teams。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9367a865c1eb3a8b71c60f492a8b222431c98d73
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832941"
---
# <a name="share-to-teams-from-outlook"></a>共有してTeamsからOutlook

Outlook から Teams への共有 ( 共有から Teams) を使用すると、Outlook から Teams 内の任意のチャットまたはチャネルに添付ファイルを含むメールを共有できます。 Teams

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook共有用のアドインのTeams 

[共有Teams機能を使用するには、アプリのアドインがOutlook。 このアドインは、ユーザーが Teams Web アプリまたはデスクトップ クライアントにログオンするたびにTeamsインストールされます。

> [!NOTE]
> Exchange Online のアドインが正しく機能するように、Outlook の Outlook [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)と[Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)のクライアント アクセス規則のアドイン Outlookを確認してください。 また、接続エクスペリエンスを無効にすると、アプリのアドインがOutlook動作しなく場合があります。 詳細については[、「Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) in Office」を参照してください。  

[共有Teamsユーザーがチャネルを電子メールで送信する場合と同じトランスポート メカニズムを使用します。 チャットと共有するには、メール (メールの添付ファイルを含む) が送信者のメール アドレスにOneDrive。 チャネルと共有するために、メールと添付ファイルは、SharePoint の[電子メール メッセージ] フォルダーにコピーされます。

Teams への共有用 Outlook アドインでは[、Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)アドインのドキュメントで詳しく説明されている要件セット 1.7 を使用します。このドキュメントには、Outlook アドインの詳細、Outlook アドインの環境要件、要件セット 1.7 でサポートされている特定の Outlook クライアントが含まれます。

## <a name="enabling-or-disabling-share-to-teams"></a>共有を有効または無効にするTeams

次Outlook PowerShell コマンドレットを使用して、Teams 共有アドインをユーザーごとに選択的に無効にしたり、有効にしたりすることができます。

> [!NOTE]
> アドインを無効にできるのは、アドインがインストールされた後のみです。 テナント内のすべてのユーザーに対して無効化を強制する場合は、スクリプトを定期的に実行します。

共有によって使用されるアドインのアドインOutlookを無効にするには、Teams にある[コマンドレットを実行します](/powershell/module/exchange/disable-app?view=exchange-ps)。 

Share によって使用されるアドインのアドインを有効Outlook共有に使用Teams、 にある[コマンドレットを実行します](/powershell/module/exchange/enable-app?view=exchange-ps)。

## <a name="browsers-and-single-sign-on"></a>ブラウザーとシングル サインオン

共有はTeamsデスクトップ クライアントOutlook on the web Outlookブラウザー WebView に依存します。 特定[のブラウザーを使用Officeクライアント](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins)の詳細については、アドインで使用されるブラウザーに関するページを参照してください。 

> [!IMPORTANT]
> [共有Teams、サード パーティの Cookie とローカル ストレージアクセスの両方をユーザーのブラウザーで有効にする必要があります。

[共有Teams シングル サインオン (SSO) を使用します。つまり、ユーザーは Share to Teams 経由でアドインを使用するときに資格情報を指定する必要があります。 SSO for Outlook on the web https://outlook.office365.com/owa/extSSO.aspx サポートされ https://outlook.office.com/owa/extSSO.aspx 、応答 URL が既定でサポートされます。 バニティ ドメインの場合、管理者は適切な応答 URL をAzure Active Directoryする必要があります。