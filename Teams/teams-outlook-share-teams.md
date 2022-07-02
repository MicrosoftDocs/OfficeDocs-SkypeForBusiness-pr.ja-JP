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
description: ユーザーが Outlook から Teams 内の任意のチャットまたはチャネルに電子メールやメールの添付ファイルを共有できるようにする、Teams に共有する機能について説明します。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: db4b3adabecf147f5adf9cadb9891892b5a82e5a
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606226"
---
# <a name="share-to-teams-from-outlook"></a>Outlook から Teams に共有する

Outlook から Teams に共有 (Teams に共有) すると、ユーザーは Outlook から Teams 内の任意のチャットやチャネルに、添付ファイルを含む電子メールを共有できます。

## <a name="outlook-add-in-for-share-to-teams"></a>Teams に共有するための Outlook アドイン 

Teams への共有機能には、Outlook 用のアドインが必要です。 このアドインは、ユーザーが Teams Web アプリまたは Teams デスクトップ クライアントにログオンするたびに自動的にインストールされます。

> [!NOTE]
> [Outlook 用アドイン](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)が正しく機能していることを確認するには、Exchange Onlineの Outlook 用アドインと[Exchange Onlineのクライアント アクセス規則](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)を確認してください。 また、接続エクスペリエンスを無効にすると、Outlook のアドインが正常に動作しなくなる可能性があります。 詳細については、「 [Office のコネクテッド エクスペリエンス](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) 」を参照してください。  

Teams への共有では、ユーザーがチャネルに電子メールを送信したときと同じトランスポート メカニズムが使用されます。 チャットに共有する場合は、電子メール (電子メールの添付ファイルを含む) が送信者の OneDrive にコピーされます。 チャネルに共有する場合、メールと添付ファイルは SharePoint の **[電子メール メッセージ** ] フォルダーにコピーされます。

Outlook アドインの Share to Teams では、Outlook アドインの [詳細、Outlook アドイン](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)の環境要件、および要件セット 1.7 でサポートされている特定の Outlook クライアントを含む、要件セット 1.7 が使用されます。

## <a name="enabling-or-disabling-share-to-teams"></a>Teams への共有を有効または無効にする

Teams への共有用 Outlook アドインは、次の PowerShell コマンドレットを使用して、ユーザーごとに選択的に無効または有効にすることができます。

> [!NOTE]
> アドインを無効にできるのは、アドインがインストールされた後のみです。 テナント内のすべてのユーザーに対して無効化を強制する場合は、スクリプトを定期的に実行します。

Share to Teams で使用される Outlook のアドインを無効にするには、 [ここで見つかったコマンドレット](/powershell/module/exchange/disable-app)を実行します。

Share to Teams で使用される Outlook のアドインを有効にするには、 [ここで見つかったコマンドレット](/powershell/module/exchange/enable-app)を実行します。

## <a name="browsers-and-single-sign-on"></a>ブラウザーとシングル サインオン

Outlook on the webデスクトップ クライアントと Outlook デスクトップ クライアントの両方で Teams と共有するには、ブラウザーの WebView に依存します。 特定のブラウザーを使用するクライアントの詳細については、 [Office アドインで使用](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) されるブラウザーに関するページを参照してください。 

> [!IMPORTANT]
> Teams に共有するには、ユーザーのブラウザーに対してサード パーティの Cookie とローカル ストレージ アクセスの両方を有効にする必要があります。

Teams への共有ではシングル サインオン (SSO) が使用されます。つまり、ユーザーは Teams への共有を介してアドインを使用するときに資格情報を提供する必要はありません。 既定では、Outlook on the webの SSO は URL をサポート<https://outlook.office365.com/owa/extSSO.aspx>し、<https://outlook.office.com/owa/extSSO.aspx>応答します。 バニティ ドメインの場合、管理者は適切な Azure Active Directory 応答 URL を追加する必要があります。
