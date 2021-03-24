---
title: Teams と共有する
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: ユーザーが Outlook から Teams の任意のチャットまたはチャネルにメールやメールの添付ファイルを共有できる Teams への共有機能について学習します。
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
# <a name="share-to-teams-from-outlook"></a>Outlook から Teams と共有する

Outlook から Teams と共有 (Teams に共有) すると、ユーザーは Outlook から Teams 内の任意のチャットまたはチャネルに添付ファイルを含むメールを共有できます。

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook アドインを Teams と共有する 

Teams への共有機能を使用するには、Outlook 用のアドインが必要です。 このアドインは、ユーザーが Teams Web アプリまたは Teams デスクトップ クライアントにログオンするたびに自動的にインストールされます。

> [!NOTE]
> Outlook 用アドインが正しく機能するように [、Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) の Outlook のアドインと [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) のクライアント アクセス ルールを確認してください。 また、接続エクスペリエンスを無効にすると、Outlook のアドインが正常に機能しなく場合があります。 詳細 [については、「接続エクスペリエンス」Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) を参照してください。  

Teams と共有する場合、ユーザーがチャネルをメールで送信する場合と同じトランスポート メカニズムが使用されます。 チャットで共有する場合、メール (メールの添付ファイルを含む) が送信者の OneDrive にコピーされます。 チャネルと共有するために、メールと添付ファイルは SharePoint の **[電子** メール メッセージ] フォルダーにコピーされます。

Teams に共有する Outlook アドインでは、要件セット 1.7 を使用します。詳細については [、Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)アドインのドキュメントを参照してください。これには、Outlook アドインの詳細、Outlook アドインの環境要件、要件セット 1.7 でサポートされている特定の Outlook クライアントが含まれます。

## <a name="enabling-or-disabling-share-to-teams"></a>Teams への共有を有効または無効にする

次の PowerShell コマンドレットを使用して、Teams に共有する Outlook アドインをユーザーごとに選択的に無効または有効にすることができます。

> [!NOTE]
> アドインを無効にできるのは、アドインがインストールされた後のみです。 テナント内のすべてのユーザーに対して無効化を適用する場合は、スクリプトを定期的に実行します。

[Teams に共有] で使用される Outlook のアドインを無効にするには、ここで見つかった [コマンドレットを実行します](/powershell/module/exchange/disable-app?view=exchange-ps)。 

Share to Teams で使用される Outlook のアドインを有効にするには、ここで見つかった [コマンドレットを実行します](/powershell/module/exchange/enable-app?view=exchange-ps)。

## <a name="browsers-and-single-sign-on"></a>ブラウザーとシングル サインオン

Outlook on the web と Outlook デスクトップ クライアントの両方で Teams と共有するには、ブラウザーの WebView に依存します。 特定 [のブラウザーを使用Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) クライアントの詳細については、アドインで使用されるブラウザーを参照してください。 

> [!IMPORTANT]
> Teams と共有するには、サード パーティの Cookie とローカル ストレージ アクセスの両方をユーザーのブラウザーで有効にする必要があります。

Teams との共有ではシングル サインオン (SSO) が使用されます。つまり、ユーザーは Teams への共有を介してアドインを使用するときに資格情報を入力する必要が生じます。 Outlook on the web 向け SSO は、既定 https://outlook.office365.com/owa/extSSO.aspx https://outlook.office.com/owa/extSSO.aspx でサポートされ、URL に返信します。 バニティ ドメインの場合、管理者は適切な Azure Active Directory 応答 URL を追加する必要があります。