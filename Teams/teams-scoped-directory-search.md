---
title: Microsoft Teams の範囲指定ディレクトリ検索を使用する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: ディレクトリのカスタマイズされたビューを提供するマイクロソフトのチームのスコープ指定されたディレクトリ検索を使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3b51b56b8cc8a1f08d756cdab245915a2ac6824
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226654"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Microsoft Teams の範囲指定ディレクトリ検索を使用する

マイクロソフト チームのスコープ指定されたディレクトリ検索では、ユーザーが検索し、組織内の他のユーザーとの通信方法を制御する仮想の境界を作成することが可能します。 

マイクロソフトのチームでは、組織のユーザーに、ディレクトリのユーザー設定のビューを提供することができます。 マイクロソフトのチームでは、これらのカスタム ビューをサポートするために[Exchange アドレス帳ポリシー](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)を使用します。 ポリシーを有効にすると、(たとえば、チャットを開始する、またはチームにメンバーを追加するのには) 他のユーザーの検索によって返される結果は構成されているポリシーに従ってスコープします。 ユーザーは検索するか、対象とした検索が有効な場合にチームを検出することができません。 

## <a name="when-should-you-use-scoped-directory-searches"></a>スコープ指定されたディレクトリ検索を使用する場合

スコープ指定されたディレクトリ検索からメリットを得られるシナリオでは、アドレス帳ポリシーのシナリオに似ています。 たとえば、スコープ指定されたディレクトリ検索を使用して、次のような状況でする可能性があります。

- 所属する組織において、テナント内に複数の会社があり、それらを切り離された状態で維持する場合。 
- 所属する学校において、教職員と学生との間のチャットを制限する必要がある場合。 
 
アドレス帳ポリシーを使用する方法については、[アドレス帳ポリシー Exchange オンライン](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)を参照してください。

> [!IMPORTANT]
> アドレス帳のポリシーでは、のみ、仮想の分離のユーザー ディレクトリの観点からを提供します。 ユーザーは、完全な電子メール アドレスを提供することで他のユーザーとの通信を開始することができますも。 重要なことが既にキャッシュされている、新しいまたは更新されたアドレス帳のポリシーの適用前にすべてのユーザー データはユーザーが引き続き利用を 30 日間もできます。

## <a name="enable-scoped-directory-search"></a>スコープ指定されたディレクトリの検索を有効にします。

1.  仮想サブグループに組織を構成するのにには、アドレス帳ポリシーを使用します。 詳細については、[アドレス帳ポリシーの手順](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)を参照してください。

2.  Microsoft 365 の管理センターにサインインするのに、**管理センター**をを選択し、**チームの & Skype**。
 
3.  マイクロソフトのチーム管理センターで、**組織全体の設定**を選択します > **チームの設定**です。

4.  **検索**、**チームが Exchange アドレス帳ポリシー (APB) を使用してディレクトリ検索のスコープ**をで **[** 表示/非表示をオンにします。 

    ![マイクロソフトのチーム管理センターのディレクトリ検索のスコープ](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> ハイブリッド構成 (Exchange、オンプレミスのチーム) は、対象とした検索モードをサポートしていません。 

