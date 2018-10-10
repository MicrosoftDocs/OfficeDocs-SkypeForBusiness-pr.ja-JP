---
title: マイクロソフトのチームを使用してディレクトリ検索のスコープ
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/09/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
description: ディレクトリのカスタマイズされたビューを提供するマイクロソフトのチームのスコープ指定されたディレクトリ検索を使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e9cddc12a5ef4de6dfb42a714b83e29b6fb4f5f
ms.sourcegitcommit: dba62f1cb6058e73a1a4c75f3473119a04a1b9e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2018
ms.locfileid: "25456892"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>マイクロソフトのチームを使用してディレクトリ検索のスコープ

マイクロソフト チームのスコープ指定されたディレクトリ検索では、ユーザーが検索し、組織内の他のユーザーとの通信方法を制御する仮想の境界を作成することが可能します。 

マイクロソフトのチームでは、組織のユーザーに、ディレクトリのユーザー設定のビューを提供することができます。 マイクロソフトのチームでは、これらのカスタム ビューをサポートするために[Exchange アドレス帳ポリシー](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019)を使用します。 ポリシーを有効にすると、(たとえば、チャットを開始する、またはチームにメンバーを追加するのには) 他のユーザーの検索によって返される結果は構成されているポリシーに従ってスコープします。 ユーザーは検索し、検出またはこれらのポリシー以外で新しいチームに参加することができません。 

## <a name="when-should-you-use-scoped-directory-searches"></a>スコープ指定されたディレクトリ検索を使用する場合

スコープ指定されたディレクトリ検索からメリットを得られるシナリオでは、アドレス帳ポリシーのシナリオに似ています。 たとえば、スコープ指定されたディレクトリ検索を使用して、次のような状況でする可能性があります。

- 組織には、別に保持する、テナント内の複数の企業がいます。 
- 学校は、教職員と学生の間でチャットを制限する必要があります。 
 
アドレス帳ポリシーの使用方法の詳細については、[ここで](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019)。

> [!IMPORTANT]
> アドレス帳のポリシーでは、のみ、仮想の分離のユーザー ディレクトリの観点からを提供します。 ユーザーは、完全な電子メール アドレスを提供することで他のユーザーとの通信を開始することができますも。 

## <a name="enable-scoped-directory-search"></a>スコープ指定されたディレクトリの検索を有効にします。

1.  仮想サブグループに組織を構成するのにには、アドレス帳ポリシーを使用します。 詳細については、[アドレス帳ポリシーの手順](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019)を参照してください。

2.  Microsoft 365 の管理センターにサインインするのに、**管理センター**をを選択し、**チームと Skype**。
 
3.  マイクロソフトのチームと Skype ビジネス管理センターは、**組織全体の設定**を選択します > **チームの設定**です。

4.  **検索**、**チームが Exchange アドレス帳ポリシー (APB) を使用してディレクトリ検索のスコープ**をで **[** 表示/非表示をオンにします。 

    ![ビジネス管理センターについては、チームと Skype のディレクトリ検索のスコープ](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> ハイブリッド構成 (Exchange、オンプレミスのチーム) は、対象とした検索モードをサポートしていません。 

