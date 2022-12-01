---
title: Teams に共有する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Teams への共有機能について説明します。これにより、ユーザーは Outlook から Teams の任意のチャットまたはチャネルにメールや電子メールの添付ファイルを共有できます。
ms.collection:
- M365-collaboration
ms.custom: chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f8334f8dbdbebce17dea4a8a4ebc8ebf798b79
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198489"
---
# <a name="share-to-teams-from-outlook"></a>Outlook から Teams に共有する

Outlook から Teams に共有 (Teams に共有) を使用すると、ユーザーは Outlook から Teams 内の任意のチャットまたはチャネルに、添付ファイルを含むメールを共有できます。

## <a name="outlook-add-in-for-share-to-teams"></a>Teams への共有用 Outlook アドイン 

Teams への共有機能には、Outlook 用のアドインが必要です。 このアドインは、ユーザーが Teams Web アプリまたは Teams デスクトップ クライアントにログオンするたびに自動的にインストールされます。

> [!NOTE]
> [Exchange Onlineの Outlook 用アドインと Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) [のクライアント アクセス規則](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)を確認して、Outlook 用アドインが正しく機能することを確認してください。 また、接続されたエクスペリエンスを無効にすると、Outlook のアドインが正常に動作しなくなる可能性があります。 詳細については、「 [Office での接続済みエクスペリエンス](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) 」を参照してください。 共有メールボックスはアドインではサポートされていません。 

Teams への共有では、ユーザーがチャネルに電子メールを送信する場合と同じトランスポート メカニズムが使用されます。 チャットに共有するために、メール (電子メールの添付ファイルを含む) が送信者の OneDrive にコピーされます。 チャネルと共有するために、メールと添付ファイルは SharePoint の **Email メッセージ** フォルダーにコピーされます。

Outlook アドインの詳細、Outlook アドインの環境要件、要件セット 1.7 でサポートされている特定の [Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) クライアントなど、Outlook アドインのドキュメントで詳しく説明されているように、Teams への Outlook アドインでは要件セット 1.7 が使用されます。

## <a name="enabling-or-disabling-share-to-teams"></a>Teams への共有を有効または無効にする

Teams への共有用 Outlook アドインは、次の PowerShell コマンドレットを使用して、ユーザーごとに選択的に無効または有効にすることができます。

> [!NOTE]
> アドインの無効化は、アドインがインストールされた後にのみ可能です。 テナント内のすべてのユーザーに対して無効化を強制する場合は、スクリプトを定期的に実行します。

Teams への共有で使用される Outlook のアドインを無効にするには、 [ここで見つかったコマンドレット](/powershell/module/exchange/disable-app)を実行します。

Teams への共有で使用される Outlook のアドインを有効にするには、 [ここで見つかったコマンドレット](/powershell/module/exchange/enable-app)を実行します。

## <a name="browsers-and-single-sign-on"></a>ブラウザーとシングル サインオン

Outlook on the webと Outlook の両方のデスクトップ クライアントで Teams に共有するには、ブラウザー WebView に依存します。 特定 [のブラウザーを使用](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) するクライアントの詳細については、「Office アドインで使用されるブラウザー」を参照してください。 

> [!IMPORTANT]
> Teams への共有では、ユーザーのブラウザーでサード パーティの Cookie とローカル ストレージ アクセスの両方を有効にする必要があります。

Teams への共有では、シングル サインオン (SSO) が使用されます。つまり、Teams への共有を介してアドインを使用する場合、ユーザーは資格情報を指定する必要はありません。 Outlook on the webの SSO では、<https://outlook.office365.com/owa/extSSO.aspx>既定で URL と<https://outlook.office.com/owa/extSSO.aspx>応答 URL がサポートされます。 バニティ ドメインの場合、管理者は適切な Azure Active Directory 応答 URL を追加する必要があります。
