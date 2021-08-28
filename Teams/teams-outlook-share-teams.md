---
title: 共有を共有Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: ユーザーがメールやメールの添付ファイルを Teams から Outlook 内の任意のチャットまたはチャネルに共有できる共有機能についてTeams。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ebbfeecf72be2d042e3686d11be98d3343a3d5f4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633981"
---
# <a name="share-to-teams-from-outlook"></a>共有してTeamsからOutlook

Outlook から Teams に共有すると、Outlook から Teams 内の任意のチャットまたはチャネルに添付ファイルを含むメールを共有できます。 Teams

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook共有用のアドインを追加Teams 

[共有] Teams機能を使用するには、アプリのアドインがOutlook。 このアドインは、ユーザーが Teams Web アプリまたはデスクトップ クライアントにログオンするたびにTeamsインストールされます。

> [!NOTE]
> Exchange Online の Outlook とクライアント アクセス規則の Outlook [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)のアドイン[](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)を必ず確認し、Outlook のアドインが正しく機能Outlookしてください。 また、接続エクスペリエンスを無効にすると、アプリのアドインがOutlook動作しなく場合があります。 詳細については[、「Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) in Office」を参照してください。  

[共有Teamsユーザーがチャネルを電子メールで送信する場合と同じトランスポート メカニズムを使用します。 チャットと共有する場合、メール (メールの添付ファイルを含む) は送信者のアカウントにOneDrive。 チャネルと共有するために、メールと添付ファイルは、SharePoint の[電子メール メッセージ] フォルダーにコピーされます。

Teams への共有用 Outlook アドインでは[、Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)アドインのドキュメントで詳しく説明されている要件セット 1.7 を使用します。このドキュメントには、Outlook アドインの詳細、Outlook アドインの環境要件、要件セット 1.7 でサポートされている特定の Outlook クライアントが含まれます。

## <a name="enabling-or-disabling-share-to-teams"></a>共有を有効または無効にするTeams

次Outlook PowerShell コマンドレットを使用して、Teams共有用の新しいアドインをユーザーごとに選択的に無効にしたり、有効にしたりすることができます。

> [!NOTE]
> アドインを無効にできるのは、アドインがインストールされた後のみです。 テナント内のすべてのユーザーに対して無効化を強制する場合は、スクリプトを定期的に実行します。

共有で使用されるアドインのアドインOutlookを無効にするには、Teams にある[コマンドレットを実行します](/powershell/module/exchange/disable-app?view=exchange-ps)。 

Share によって使用されるアドインのアドインを有効Outlook、次のコマンドレットをTeamsを[実行します](/powershell/module/exchange/enable-app?view=exchange-ps)。

## <a name="browsers-and-single-sign-on"></a>ブラウザーとシングル サインオン

共有をTeams、デスクトップ クライアントOutlook on the webとOutlookの両方で、ブラウザーの WebView に依存します。 特定[のブラウザーを使用Officeクライアント](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins)の詳細については、「アドインで使用されるブラウザー」を参照してください。 

> [!IMPORTANT]
> [共有Teams、サード パーティの Cookie とローカル ストレージアクセスの両方をユーザーのブラウザーで有効にする必要があります。

[共有Teams シングル サインオン (SSO) を使用します。つまり、ユーザーは Share 経由でアドインを使用して Teams にサインインするときに資格情報を指定する必要がTeams。 SSO for Outlook on the webサポート https://outlook.office365.com/owa/extSSO.aspx され https://outlook.office.com/owa/extSSO.aspx 、既定で応答 URL が返されます。 バニティ ドメインの場合、管理者は適切な応答 URL をAzure Active Directoryする必要があります。