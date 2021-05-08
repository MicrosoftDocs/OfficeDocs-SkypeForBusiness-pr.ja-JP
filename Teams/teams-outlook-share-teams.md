---
title: 共有を共有Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: ユーザーが Teams からメールやメールの添付ファイルを Outlook 内の任意のチャットまたはチャネルに共有できる共有機能についてTeams。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098223"
---
# <a name="share-to-teams-from-outlook"></a>共有してTeamsからOutlook

Outlook から Teams への共有( 共有 ) を使用すると、Outlook から Teams 内の任意のチャットまたはチャネルに添付ファイルを含むメールを共有できます。 Teams

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook共有用のアドインのTeams 

[共有] Teams機能を使用するには、アプリのアドインがOutlook。 このアドインは、ユーザーが Teams Web アプリまたはデスクトップ クライアントにログオンするたびにTeamsインストールされます。

> [!NOTE]
> Exchange Online の[Exchange Online Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)とクライアント アクセス規則の Outlook の[](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)アドインを確認して、Outlook のアドインが正しく機能Outlookしてください。 また、接続されたエクスペリエンスを無効にすると、アプリのアドインがOutlook動作しなく場合があります。 詳細については[、「Office 接続](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c)エクスペリエンス」を参照してください。  

[共有Teamsユーザーがチャネルを電子メールで送信する場合と同じトランスポート メカニズムを使用します。 チャットと共有するために、メール (メールの添付ファイルを含む) は送信者のメール アドレスにOneDrive。 チャネルと共有するために、メールと添付ファイルは、SharePoint の[電子メール メッセージ] フォルダーにコピーされます。

Teams への共有用 Outlook アドインでは[、Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)アドインのドキュメントで詳しく説明されている要件セット 1.7 を使用します。このドキュメントには、Outlook アドイン、Outlook アドインの環境要件、要件セット 1.7 でサポートされている特定の Outlook クライアントの詳細が含まれます。

## <a name="enabling-or-disabling-share-to-teams"></a>共有を有効または無効にするTeams

次Outlook PowerShell コマンドレットを使用して、Teams共有アドインをユーザーごとに選択的に無効にしたり、有効にしたりすることができます。

> [!NOTE]
> アドインを無効にできるのは、アドインがインストールされた後のみです。 テナント内のすべてのユーザーに対して無効化を強制する場合は、スクリプトを定期的に実行します。

Share で使用されるアドインのアドインOutlookを無効にするには、Teams にある[コマンドレットを実行します](/powershell/module/exchange/disable-app?view=exchange-ps)。 

Share が使用するアドインのアドインOutlookを有効にするには、Teams コマンドレット[を実行します](/powershell/module/exchange/enable-app?view=exchange-ps)。

## <a name="browsers-and-single-sign-on"></a>ブラウザーとシングル サインオン

Web 上Teamsクライアントとデスクトップ Outlookの両方で、ブラウザーの WebView に依存Outlook共有します。 どの[クライアントが特定のブラウザー Office使用](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins)しているかの詳細については、アドインで使用されるブラウザーに関するページを参照してください。 

> [!IMPORTANT]
> [共有Teams、サード パーティの Cookie とローカル ストレージアクセスの両方をユーザーのブラウザーで有効にする必要があります。

[共有Teams シングル サインオン (SSO) を使用します。つまり、ユーザーは Share から Teams 経由でアドインを使用するときに資格情報を指定する必要があります。 Web 上Outlookの SSO では、既定 https://outlook.office365.com/owa/extSSO.aspx https://outlook.office.com/owa/extSSO.aspx でサポートおよび応答 URL がサポートされます。 バニティ ドメインの場合、管理者は適切な応答 URL をAzure Active Directoryする必要があります。